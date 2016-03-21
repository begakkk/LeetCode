##LeetCode 2.1.1##

###问题描述：
Given a sorted array, remove the duplicates in place such that each element appear only once
and return the new length.
Do not allocate extra space for another array, you must do this in place with constant memory.
For example, Given input array A = [1,1,2],
Your function should return length = 2, and A is now [1,2].


###算法：

    public class RebulidArr<T> where T:struct 
    {
        public static int ResizeArr(T[] arr)
        {
            int offset = 0;
            int indexCount = arr.Length - 1;
            int offsetsp = 0;
            for(int i = 0; i < indexCount; i++)
            {
                if(arr[i].Equals(arr[i + 1+offset]))
                {
                    i -= 1;
                    offset += 1;
                }
                else
                {
                    arr[offsetsp + 1] = arr[i + 1 + offset];
                    i = i + offset;
                    offset = 0;
                    offsetsp += 1;
                }
            }
            return offsetsp+1;
        }

###调用以及测试结果：
		static void Main(string[] args)
        {
            int[] a=new int[]{1,1,2,2,2,3,3,4,5,6};
            int length=RebulidArr<int>.ResizeArr(a);

            RebulidArr<int>.PrintArr(a);
            Console.WriteLine("lengthA:{0}",length);


            int[] b=new int[]{1,2,3,3,4,6,7,7,9,9,34};
            int lengthb = RebulidArr<int>.ResizeArr(b);
            RebulidArr<int>.PrintArr(b);
            Console.WriteLine("lengthB:{0}",lengthb);

            double[] c=new double[]{0.1,0.2,0.2,0.6,0.8,0.9};
            int lengthC = RebulidArr<double>.ResizeArr(c);
            RebulidArr<double>.PrintArr(c);
            Console.WriteLine("lenthC:{0}",lengthC);

            Console.ReadKey();
        }
![](C:\Users\王飓烜\Desktop\捕获1.JPG)

###感想
长时间没有过专注于算法的思考了，平时遇见算法方面的问题都尽可能的用的消耗更多的内存和复杂度的方式来解决问题，逻辑思维变的很糟糕了，这个算法写了2个小时，希望在后续的练习中快速恢复状态。


**PS:由于.net平台不允许也不提倡直接使用指针，在上述结果中，数组的长度无法改变，即能够得到排序后的数据，但是多余的重复数字无法去掉，以后相类似的问题也一样。**

**后记：看了leetCode的答案，感觉自己就是个low逼**