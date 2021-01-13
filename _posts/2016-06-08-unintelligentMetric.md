I was taking an interview when I noticed in the resume of the interviewee that he had developed 70% of the code in a particular project.
Out of sheer curiosity, I asked him how did he reckon this percentage. But to my disappointment, that number was not any intelligent calculation but a wild guess.

That lead me to a trivial idea of calculating such metric... And here it is **unintelligentMetric**. 

**Why this metric is unintelligent ?**

It returns you the number of lines written by each developer contributed in given **git** repository.
It uses **[git blame](http://mannumalhotra.in/git-basic-commands/)** to decide the committer. Which means, irrespective of who wrote the code originally, it will only consider the one who has modified it last time.
Hence even if you have just entered a space in a line of code, you are the owner of this line now.


**Script:**

    # All the directories and files you want to skip will go here...
    files=`find . -type f \
        -not -path "./node_modules/*" \
        -not -path "./.git/*" \
        -not -path "*.log" \
        -not -path "*.html"`
    
    for file in $files; do
        git blame --show-name $file >> code
    done
    tr -s ' ' < code | cut -d' ' -f3 | sort | uniq -c
    
    rm code



**Some of the learning:**

* --show-name with **git blame** command gives the name of the file being subjected to.

* Your project may contain many binary files. **awk** does not works on binary files, however cut does.


* Sometimes git blame adds mulitple white spaces after committer name, such as:

    `ff7409fd bin/deploy (Dileep          2014-01-08 13:27:21 +0530  2)`

 And unlike awk, cut -d' ' considers group of white spaces as multiple delimiter. Hence the use of tr to trim multiple white spaces into one.
