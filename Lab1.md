# Lab 1

Command cd:
1. With no arguments, command cd would return to user's folder.
   ```
   # cd: no arguments
   bryantzhu@Bryants-MacBook Documents % ls
   BOOK			League of Legends	MATLAB			UCSD
   Daily			MAC			NYU			Zoom
   bryantzhu@Bryants-MacBook Documents % cd
   bryantzhu@Bryants-MacBook ~ % ls
   Applications	Documents	Library		Music		Public
   Desktop		Downloads	Movies		Pictures
   bryantzhu@Bryants-MacBook ~ %
   ```
   >The working directory was 'Documents'.  
   >Command cd makes me back to 'bryantzhu', so the ouput is expected.  
   >The output is not an error.

2. With a path to a directory, command cd would jump to your path's destination.
   ```
   # cd: a path to a directory
   bryantzhu@Bryants-MacBook ~ %
   bryantzhu@Bryants-MacBook ~ % cd /Users/bryantzhu/Documents
   bryantzhu@Bryants-MacBook Documents % 
   ```
   >The working directory was 'bryantzhu'.  
   >Command cd makes me jump to the target directory. In this case, since my path leads to 'Documents', I get to 'Documents'.  
   >The output is not an error.
   
3. With a path to a file, command cd would raise an error or warning.
   ```
   # cd: a path to a file
   bryantzhu@Bryants-MacBook ~ %
   bryantzhu@Bryants-MacBook ~ % cd /Users/bryantzhu/Documents/NYU/JAVA/Avg/Avg.java
   cd: not a directory: /Users/bryantzhu/Documents/NYU/JAVA/Avg/Avg.java
   bryantzhu@Bryants-MacBook ~ %
   ```
   >The working directory was 'bryantzhu'.  
   >Since command cd's arguments can not be files, the output says 'not a directory'.  
   >I think the output is not an error, since it does not print out anything unexpected.

Command ls:
1. With no arguments, command ls shows the files and folders in your current location.
   ```
   #ls: no arguments
   bryantzhu@Bryants-MacBook ~ %
   bryantzhu@Bryants-MacBook ~ % ls
   Applications	Documents	Library		Music		Public
   Desktop		Downloads	Movies		Pictures
   bryantzhu@Bryants-MacBook ~ % 
   ```
   >The working directory was 'bryantzhu'.  
   >Command ls showed the files and folders in my current location which was 'bryantzhu'.  
   >The ouput is not an error.
   
2. With a path to a directory, command ls would show the files and folders in your target dicrectory.
   ```
   #ls: a path to a directory
   bryantzhu@Bryants-MacBook ~ %
   bryantzhu@Bryants-MacBook ~ % ls /Users/bryantzhu/Documents
   BOOK			League of Legends	MATLAB			UCSD
   Daily			MAC			NYU			Zoom
   bryantzhu@Bryants-MacBook ~ %
   ```
   >The working directory was 'bryantzhu'.  
   >With the path provided, command ls shows the files and folders inside the destination.
   >In this case, since the path is to Documents, command ls print out the files and folders inside.  
   >The output is not an error.
   
3. With a path to a file, command ls would show the path.
   ```
   #ls: a path to a file
   bryantzhu@Bryants-MacBook ~ %
   bryantzhu@Bryants-MacBook ~ % ls /Users/bryantzhu/Documents/NYU/JAVA/Avg/Avg.java
   /Users/bryantzhu/Documents/NYU/JAVA/Avg/Avg.java
   bryantzhu@Bryants-MacBook ~ %
   ```
   >The working directory was 'bryantzhu'.  
   >In this case, command ls basically does nothing since what command ls can do is to list file.  
   >The output is not an error.


Command cat:
1. With no arguments, command cat would show nothing and you have to kill the command process manually.
   ```
   #cat: with no arguments
   bryantzhu@Bryants-MacBook ~ %
   bryantzhu@Bryants-MacBook ~ % cat


   ^C
   bryantzhu@Bryants-MacBook ~ %
   ```
   >The working directory was 'bryantzhu'.  
   >With no arguments provided, command cat doesn't have anything to print out, thus the result is nothing.  
   >Since I need to kill the process manually, I think this counts as an error, and the result is unexpected.
   
2. With a path to a directory, the command cat would say your argument 'Is a directory'.
   ```
   #cat: with a path to a directory
   bryantzhu@Bryants-MacBook ~ %
   bryantzhu@Bryants-MacBook ~ % cat /Users/bryantzhu/Documents
   cat: /Users/bryantzhu/Documents: Is a directory
   bryantzhu@Bryants-MacBook ~ % 
   ```
   >The working directory was 'bryantzhu'.  
   >Since we are proving a path to a directory as the argument and command cat is used to print out what is in the file,
   >command cat would not function well this time.
   >Thankfully, this time it raises a warning or an error to tell me what is wrong instead of making me to kill it.  
   >Since it properly raises the error itself, I do not think the output is an error.
   
3. With a path to a file, command cat would print out what is in your file.
   ```
   #cat: with a path to a file
   bryantzhu@Bryants-MacBook ~ %
   bryantzhu@Bryants-MacBook ~ % cat /Users/bryantzhu/Documents/NYU/JAVA/Avg/Avg.java

   /*average program: compute the average

   Name: Bryant Zhu

   Date: Sep 15 2021*/

   public class Avg
   {
     public static void main(String[] arg)
     {
       double grade1 = 99.9;
       double grade2 = 87.4;
       //compute avg
       double avg = (grade1 + grade2)/2;
       System.out.println ("The average: " + avg);
     }
   }%
   bryantzhu@Bryants-MacBook ~ %
   ```
   >The working directory was 'bryantzhu'.  
   >The provided argument is a path to a java file, which is a fine object for command cat to handle.
   >As expected, command cat prints out the code in the java file.  
   >The output is not an error
   
