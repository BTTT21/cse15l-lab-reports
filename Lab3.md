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


The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
