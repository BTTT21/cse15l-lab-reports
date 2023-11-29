# Lab Report 5
**Part1:**

Student:
>Hi, my code has some bugs and returns wrong output. The output returned in my test result missed an element in the expected output. I attached the screenshot of my test result below. I guess the bug exists during the process of adding the elements from the two lists. I also attached the screenshot of my test code so you can know what the failure-inducing input is. Thank you.
>
>Here's my code:
>```
>import java.util.ArrayList;
>import java.util.List;
>
>  static List<String> merge(List<String> list1, List<String> list2) {
>    List<String> result = new ArrayList<>();
>    int index1 = 0, index2 = 0;
>    while(index1 < list1.size() && index2 < list2.size()) {
>      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
>        result.add(list1.get(index1));
>        index1 += 1;
>      }
>      else {
>        result.add(list2.get(index2));
>        index2 += 1;
>      }
>    }
>    while(index1 < list1.size()-1) {
>      result.add(list1.get(index1));
>      index1 += 1;
>    }
>    while(index2 < list2.size()-1) {
>      result.add(list2.get(index2));
>      index2 += 1;
>    }
>    return result;
>  }
>
>}
>
>```
>Here is my testing file:
>```
>import static org.junit.Assert.*;
>import org.junit.*;
>import java.util.Arrays;
>import java.util.List;
>
>
>public class TestListExamples {
>
>  @Test(timeout = 500)
>  public void testMergeRightEnd() {
>    List<String> left = Arrays.asList("a", "b", "c");
>    List<String> right = Arrays.asList("a", "d");
>    List<String> merged = ListExamples.merge(left, right);
>    List<String> expected = Arrays.asList("a", "a", "b", "c", "d");
>    assertEquals(expected, merged);
>  }
>
>}
>```
>Here's my bash script:
>```
>javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
>java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples
>```
>Here's my test result:
>
>![Screenshot 2023-11-28 at 8 24 07 PM](https://github.com/BTTT21/cse15l-lab-reports/assets/146874113/08e66f7e-bc64-4cdb-aa78-c1a8b9181ee4)

TA: 
>You want to double check your condition for your while loops, make sure they are the conditions you want.

Student:
>Thank you! I just checked my conditions for my while loops. I found my second and third while loops end before my expectation. I changed the conditions from 'index1 < list1.size()-1' to 'index1 < list1.size()' and from 'index2 < list2.size()-1' to 'index2 < list2.size()'. The bug is that the while loops do not reach the end of the lists and stop right before the last element.
>
>Here is my new test result:
>
>![Screenshot 2023-11-28 at 8 23 34 PM](https://github.com/BTTT21/cse15l-lab-reports/assets/146874113/a0e6fc27-6631-4dc1-8f9a-4fe640909b54)


**Part2:**
>I think something new I learned are the autograder and JDB. These skills are very cool and useful and I believe there would be a time that I can utilize these skills. Specially, I found the JDB could really help me a lot. Before I know this technique, I always try to print out everything. Now I find a quicker way to see what's going on in my code.
