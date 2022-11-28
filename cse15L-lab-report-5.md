Ricky Li
Joe Politz
27 November 2022

### CSE 15L Lab Report 5

```

set -e

rm -rf student-submission
git clone $1 student-submission

cd student-submission

if [[ ! -f ListExamples.java ]]
then
  echo "You are missing ListExamples.java"
  echo "Fail"
  exit

fi


cp ../TestListExamples.java .


javac -cp ".;../lib/hamcrest-core-1.3.jar;../lib/junit-4.13.2.jar" *.java
java -cp ".;../lib/junit-4.13.2.jar;../lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore TestListExamples

```

When I tried to run the GradeServer file on my computer and go to the url, it would give me this error message saying that it could not find bash
![My Image](sc-lab-report5.JPG)



But it ran on VS Code




https://github.com/ucsd-cse15l-f22/list-methods-lab3


![My Image](sc-lab-report5.2.JPG)



https://github.com/ucsd-cse15l-f22/list-methods-corrected


![My Image](sc-lab-report5.1.JPG)



https://github.com/ucsd-cse15l-f22/list-methods-filename


![My Image](sc-lab-report5.3.JPG)



For https://github.com/ucsd-cse15l-f22/list-methods-filename, the code is implemented well however the file is saved with the wrong name

This line of code in my grade.sh bash file checks if there is an existing student-submission directory from previous grading and if there is it will delete that directory

`rm -rf student-submission`

This line will grab the url inputted from the terminal and then copy the repository

`git clone $1 student-submission`

Then I cd into the student-submission folder and run an If command to find out if the ListExamples.java file is in the directory or not

```

if [[ ! -f ListExamples.java ]]
then
  echo "You are missing ListExamples.java"
  echo "Fail"
  exit

fi


```

In the example above, the file was not in the directory so it outputs ""You are missing ListExamples.java Fail"

Because the bash script ended, the rest of the lines didn't run however, 

```

cp ../TestListExamples.java .


javac -cp ".;../lib/hamcrest-core-1.3.jar;../lib/junit-4.13.2.jar" *.java
java -cp ".;../lib/junit-4.13.2.jar;../lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore TestListExamples | grep -e OK -e Failures: > results

cat results

```

The rest of the code will copy my TestListExamples.java file which contains all the tests I created in order to test out the student submitted code. It will then run the tests and create a results file that contains the results of the tests. I then print out the test results for the student to see.
