## Basic work with files

- Create directory test1  
 ```console
 mkdir test1
```

- Create file test1.txt inside the test1 directory.  
 ```console 
touch test1.txt
```

- Create copy of folder test1 with name test2.  
 ```console 
cp -r test1 test2
```

- Delete file test1.txt inside test2 directory.  
 ```console 
rm -rf test1.txt
```

- Rename test2 folder into directory_without_file  
 ```console 
mv test2 directory_without_file
```

- Insert 'test1' text into test1/test1.txt file.  
 ```console 
echo "text1" > test1/test1.txt
```

- print the text from the test1/test1.txt file.  
 ```console 
cat test1.txt
```

- Insert 'test2' into the end of test1/test1.txt file.  
 ```console 
echo "test2" >> test1.txt
```

- print the text from the test1/test1.txt file.  
 ```console 
cat test1.txt
```

- check the size of test1 directory  
 ```console 
du -sh test1
```

## Permissions

- Create test directory and block access for all to it.  
 ```console
 chmod ugo-rwx test
```

- Try to remove that directory.  
 ```console 
rm -rf test
```

- Create simple script which prints current date. Try to execute it.  
 ```console
  mkdir script.sh
```  
 ```
console chmod +x script.sh
```  
 ```
console ./script.sh
```  
 ```console
date
```  

## Log checking

- Count lines in the file test.txt.  
 ```console
 ac -l test.txt
```

- Show last 3 lines from the test.txt file.   
 ```console  
tail -3 test.txt
```

- Hom many uniq IP addresses accessed the website ?   
 ```console 
 awk '{print $1}' test.txt | sort | uniq | wc -l
```

- IP address with most requests.  
 ```console
 awk '{print $1}' test.txt | sort | uniq -c | sort -nr | head -n 10
```

- Top 3 IP addresses by amount of POST requests.  
 ```console
 grep 'POST' test.txt | awk '{print $1}' | sort | uniq -c | sort -nr | head -n 3
```

- Which IP addresses received 403 error ?   
 ```console
 grep '403' test.txt | awk '{print $1}' | sort | uniq | sort -nr
```

- Task with * . Write script to show which pages Google checked from the website   
 ```console
 grep "Google" test.txt | wc -l
```

## Replace

- Replace IP address with most requests on 127.0.0.1 in test.txt file   
 ```console
 awk '{print $1}' test.txt | sort | uniq -c | sort -nr | head -n 1
```  
 ```console
  sed -i 's/114.119.140.234/127.0.0.1/g' test.txt
```
