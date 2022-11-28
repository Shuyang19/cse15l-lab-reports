# Lab Report 5
```
# Create your grading script here
# set -e

rm -rf student-submission
git clone $1 student-submission
CPATH=".:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar "

cd student-submission


if  [ -e "ListExamples.java" ] 
then
    echo "You submit the correct file, [1/1]BasicPoint"
    
else
    echo "Wrong file, please check your submission, [0/1]BasicPoint"
    exit 1
fi

cd ..
cp TestListExamples.java student-submission/
cd student-submission

javac -cp $CPATH *.java 2> stderr.txt 
if [ $? -ne 0 ] 
then
    echo "You have compile error show below: "
    cat stderr.txt
    echo "You can not get scores from this part, [0/0]CompliePoint"
    exit 1
else
    echo "good job, [1/1]CompliePoint"
    java -cp $CPATH  org.junit.runner.JUnitCore TestListExamples > stdout.txt
    cat stdout.txt
fi
```
-screenshots:
![Image](5.1.png)
![Image](5.2.png)
![Image](5.3.png)
- I choose the first one to describe:
- `rm -rf student-submission` will remove the whole ddirectory student-submission from my previous tries, after command has been performed, the LIST-EXAMPLE-GRADER will not have the student-submission directory





