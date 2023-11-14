# Lab Report 3
**Part1:**
The prgram is ArrayExamples.java.  
>A failure-inducing input is {1,2,3}.
```
#Test file
public class ArrayTests
{
  @Test
  public void testReverseInPlace()
  {
    int[] input1 = { 1,2,3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3,2,1 }, input1);
  }
}
```

>An input that does not induce a failue is {1}.
```
#Test file
public class ArrayTests_org
{
  @Test
  public void testReverseInPlace()
  {
    int[] input1 = { 1 };
    ArrayExamples_org.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 1 }, input1);
  }
}
```

Symptom:
>Input: { 1 }, expected output: { 1 }, real output: { 1 }.  
![Screenshot 2023-10-31 at 2 35 53 PM](https://github.com/BTTT21/cse15l-lab-reports/assets/146874113/653bf9fe-9634-4c63-8e0e-bfcaedd2e1ec)

>Input: { 1,2,3 }, expected output: { 3,2,1 }, real output: {3,2,3}.  
![Screenshot 2023-10-31 at 2 37 25 PM](https://github.com/BTTT21/cse15l-lab-reports/assets/146874113/d3525823-2f18-4daf-b6b3-521d665afcea)

>Input: { 1,2,3,4,5 }, expected output: { 5,4,3,2,1 }, real output: { 5,4,3,4,5 }.  
![Screenshot 2023-10-31 at 2 38 30 PM](https://github.com/BTTT21/cse15l-lab-reports/assets/146874113/b2847a5e-7e10-406b-8a53-a8fcb7e9f115)

>The symptom is that the real output does not match with the expected output when we have input that has length greater than one.

Bug: arr[i] = arr[arr.length - i - 1];
```
#Before
static void reverseInPlace(int[] arr)
{
  for(int i = 0; i < arr.length; i += 1)
  {
    arr[i] = arr[arr.length - i - 1];
  }
}
```
```
#After
static void reverseInPlace(int[] arr)
{
  for(int i = 0; i < (arr.length)/2; i += 1)
  {
    int temp = arr[i];
    arr[i] = arr[arr.length - i - 1];
    arr[arr.length - i - 1] = temp;
  }
}
```
>The issue is that the method does not have a third variable to store the temporary value to ensure the exchange success.  
>When we are exchange the value of the first half of the array, we simply put the value of the second half to the first half.  
>This leads to a symmtric array with only the value of the second half of the array.  
>Thus, we need to store the value of the item we need to exchange first to a third variable first, and then we change the value between arr[i] and arr[arr.length - i - 1].  
>After the exchange, we assign arr[arr.length - i - 1] with the value we stored and complete the exchange process.  
>We also need to stop the iteration when we finshed exchanging the first half the array as we already reassign the value for the second half of the array.


**Part2:**

Recourse: https://www.geeksforgeeks.org/find-command-in-linux-with-examples/

Command: find

>-name option:  Search for a file with a specific name.  
>It is useful when we know a file's name but forget where it stores.
```
find ./technical -name chapter-1.txt 
./technical/911report/chapter-1.txt
find ./technical -name 1468-6708-3-1.txt 
./technical/biomed/1468-6708-3-1.txt
```

>-exec rm -i {} \;  option: delete a file with a specific name and ask for confirmation.  
>It is useful when we know a file's name and want to delete it.
```
find ./technical -name chapter-1.txt -exec rm -i {} \;
remove ./technical/911report/chapter-1.txt? n
find ./technical -name bill.txt -exec rm -i {} \;
remove ./technical/government/Env_Prot_Agen/bill.txt? n
```

>-empty option: finds all empty folders and files in the entered directory or sub-directories.  
>It is useful when we accidentally created unwanted folders or files and forgot where it stored.
```
find ./technical -empty
#nothing here because no empty folder or file.
find ./technical -empty #created a test empty folder and a test empty file.
./technical/test_empty_folder
./technical/911report/test_empty.txt
```

>-type option: find specific type of files or folders.  
>It is useful when we only want to see a certain type of files or folders.  
>I use -type d in the examples and it only shows the folders.
```
find ./technical -type d
./technical
./technical/government
./technical/government/About_LSC
./technical/government/Env_Prot_Agen
./technical/government/Alcohol_Problems
./technical/government/Gen_Account_Office
./technical/government/Post_Rate_Comm
./technical/government/Media
./technical/plos
./technical/biomed
./technical/911report
find ./technical/government -type d
./technical/government
./technical/government/About_LSC
./technical/government/Env_Prot_Agen
./technical/government/Alcohol_Problems
./technical/government/Gen_Account_Office
./technical/government/Post_Rate_Comm
./technical/government/Media
```
