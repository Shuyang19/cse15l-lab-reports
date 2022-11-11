# Lab Report 3 
## grep
1) -c
- example 1
```
yehanniao@yehanniaodeMacBook-Pro docsearch-main % grep -c ".txt" find-results.txt
1391
```
- example 2
```
yehanniao@yehanniaodeMacBook-Pro docsearch-main % grep -c "like" technical/911report/chapter-1.txt
18
```
- example 3
```
yehanniao@yehanniaodeMacBook-Pro docsearch-main % grep -c "chapter" find-results.txt  
16
```
- It will shows the total number of lines that contains ".txt" (the string we want to find), so that we don't need to create a new file and use `wc`to find the total line number.

2) -v
- example 1
```
yehanniao@yehanniaodeMacBook-Pro docsearch-main % grep -v ".txt" find-results.txt
technical/
technical//government
technical//government/About_LSC
technical//government/Env_Prot_Agen
technical//government/Alcohol_Problems
technical//government/Gen_Account_Office
technical//government/Post_Rate_Comm
technical//government/Media
technical//.DS_Store
technical//plos
technical//biomed
technical//911report
```
- It will list the lines that does not contains ".txt" (the string we input), so that when we find lines, it will be convenient to exclude the lines we do not need.

3) -n

- It will shows the line number that conatins "plos" (the string we want to find), so that it will be easier for us to locate the lines that contains what we want to find.
