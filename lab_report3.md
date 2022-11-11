# Lab Report 3 
## grep
1) -c
- example 1
```
yehanniao@yehanniaodeMacBook-Pro docsearch-main % grep -c ".txt" find-results.txt
1391
```
- It will shows the total number of lines that contains ".txt" (the string we want to find), so that we don't need to create a new file and use `wc`to find the total line number.

2) -v
```
yehanniao@yehanniaodeMacBook-Pro docsearch-main % grep -v ".txt" find-results.txt
```
```
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
```
yehanniao@yehanniaodeMacBook-Pro docsearch-main % grep -n "plos" find-results.txt
```
```
295:technical//plos
296:technical//plos/pmed.0020273.txt
297:technical//plos/journal.pbio.0030032.txt
298:technical//plos/pmed.0020065.txt
299:technical//plos/pmed.0020071.txt
300:technical//plos/pmed.0020059.txt
301:technical//plos/pmed.0010039.txt

...
542:technical//plos/journal.pbio.0020172.txt
543:technical//plos/pmed.0020040.txt
544:technical//plos/pmed.0020068.txt
545:technical//plos/journal.pbio.0020012.txt
546:technical//plos/pmed.0020281.txt
547:technical//plos/pmed.0020242.txt
```
- It will shows the line number that conatins "plos" (the string we want to find), so that it will be easier for us to locate the lines that contains what we want to find.

