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
- example 2
- 
```
yehanniao@yehanniaodeMacBook-Pro docsearch-main % grep -v "e" technical/plos/journal.pbio.0020001.txt

  
    
      
        
        
          
          
        
      
      
        2002).
        
          
            Canada?
          
        
      
      
        programs.
      
      
        journals (
        In 
      
      
        world.
        
          
          
        
        built.
      
    
  
```
- example 3
```
yehanniao@yehanniaodeMacBook-Pro docsearch-main % grep -v "a" technical/biomed/1468-6708-3-1.txt          

  
    
      
        Introduction/
        elderly [ 9 ] .
      
      
        
          Study
        
        
        
        
          ] .
          (for persons who were never in excellent, very good, or
          report results using only the simpler definition.
          findings.
        
        
        
        
        
      
      
        Results
        likely.
        from 25 to 29.9. The second column, which shows results
        under 20.
        groups.
        YOL or YHL.
      
      
        Discussion
        
        
        
          YHL.
        
        
        
      
      
        Conclusion
        'overweight' by the NHLBI guidelines. This suggests using
      
      
        Competing interests
      
      
        CESD Center for Epidemiologic Studies Depression
        poor?
      
```
- It will list the lines that does not contains ".txt" (the string we input), so that when we find lines, it will be convenient to exclude the lines we do not need.

3) -n
- example 1
```
yehanniao@yehanniaodeMacBook-Pro docsearch-main % grep -n "plos" find-results.txt
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
- example 2
```
yehanniao@yehanniaodeMacBook-Pro docsearch-main % grep -n "911report" find-results.txt
1386:technical//911report
1387:technical//911report/chapter-13.4.txt
1388:technical//911report/chapter-13.5.txt
1389:technical//911report/chapter-13.1.txt
1390:technical//911report/chapter-13.2.txt
1391:technical//911report/chapter-13.3.txt
1392:technical//911report/chapter-3.txt
1393:technical//911report/chapter-2.txt
1394:technical//911report/chapter-1.txt
1395:technical//911report/chapter-5.txt
1396:technical//911report/chapter-6.txt
1397:technical//911report/chapter-7.txt
1398:technical//911report/chapter-9.txt
1399:technical//911report/chapter-8.txt
1400:technical//911report/preface.txt
1401:technical//911report/chapter-12.txt
1402:technical//911report/chapter-10.txt
1403:technical//911report/chapter-11.txt
```
- example 3
```
yehanniao@yehanniaodeMacBook-Pro docsearch-main % grep -n "government" find-results.txt
2:technical//government
3:technical//government/About_LSC
4:technical//government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
5:technical//government/About_LSC/Progress_report.txt
6:technical//government/About_LSC/Strategic_report.txt
7:technical//government/About_LSC/Comments_on_semiannual.txt
8:technical//government/About_LSC/Special_report_to_congress.txt
9:technical//government/About_LSC/CONFIG_STANDARDS.txt
10:technical//government/About_LSC/commission_report.txt
11:technical//government/About_LSC/LegalServCorp_v_VelazquezDissent.txt
12:technical//government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt
13:technical//government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt
14:technical//government/About_LSC/diversity_priorities.txt
...
284:technical//government/Media/A_helping_hand.txt
285:technical//government/Media/pro_bono_efforts.txt
286:technical//government/Media/5_Legal_Groups.txt
287:technical//government/Media/Greedy_Generous.txt
288:technical//government/Media/Retirement_Has_Its_Appeal.txt
289:technical//government/Media/RoanokeTimes.txt
290:technical//government/Media/NJ_Legal_Services.txt
291:technical//government/Media/Bridging_legal_aid_gap.txt
292:technical//government/Media/Legal_Aid_campaign.txt
293:technical//government/Media/Aid_Gets_7_Million.txt
```
- It will shows the line number that conatins "plos" (the string we want to find), so that it will be easier for us to locate the lines that contains what we want to find.

