# Lab Report 3 - Researching Commands
## find - s
### Example 1
```
find -s written_2/ > find_sort_results.txt
grep ".txt" find_sort_results.txt > grep-results-sort.txt
```

First 30 lines of find_sort_results.txt
```
written_2/
written_2//non-fiction
written_2//non-fiction/OUP
written_2//non-fiction/OUP/Berk
written_2//non-fiction/OUP/Berk/ch2.txt
written_2//non-fiction/OUP/Berk/ch1.txt
written_2//non-fiction/OUP/Berk/CH4.txt
written_2//non-fiction/OUP/Berk/ch7.txt
written_2//non-fiction/OUP/Abernathy
written_2//non-fiction/OUP/Abernathy/ch2.txt
written_2//non-fiction/OUP/Abernathy/ch3.txt
written_2//non-fiction/OUP/Abernathy/ch1.txt
written_2//non-fiction/OUP/Abernathy/ch7.txt
written_2//non-fiction/OUP/Abernathy/ch6.txt
written_2//non-fiction/OUP/Abernathy/ch8.txt
written_2//non-fiction/OUP/Abernathy/ch9.txt
written_2//non-fiction/OUP/Abernathy/ch15.txt
written_2//non-fiction/OUP/Abernathy/ch14.txt
written_2//non-fiction/OUP/Rybczynski
written_2//non-fiction/OUP/Rybczynski/ch2.txt
written_2//non-fiction/OUP/Rybczynski/ch3.txt
written_2//non-fiction/OUP/Rybczynski/ch1.txt
written_2//non-fiction/OUP/Kauffman
written_2//non-fiction/OUP/Kauffman/ch3.txt
written_2//non-fiction/OUP/Kauffman/ch1.txt
written_2//non-fiction/OUP/Kauffman/ch4.txt
written_2//non-fiction/OUP/Kauffman/ch5.txt
written_2//non-fiction/OUP/Kauffman/ch7.txt
written_2//non-fiction/OUP/Kauffman/ch6.txt
written_2//non-fiction/OUP/Kauffman/ch8.txt
```

First 30 lines of grep-results-sort.txt
```
written_2//non-fiction/OUP/Berk/ch2.txt
written_2//non-fiction/OUP/Berk/ch1.txt
written_2//non-fiction/OUP/Berk/CH4.txt
written_2//non-fiction/OUP/Berk/ch7.txt
written_2//non-fiction/OUP/Abernathy/ch2.txt
written_2//non-fiction/OUP/Abernathy/ch3.txt
written_2//non-fiction/OUP/Abernathy/ch1.txt
written_2//non-fiction/OUP/Abernathy/ch7.txt
written_2//non-fiction/OUP/Abernathy/ch6.txt
written_2//non-fiction/OUP/Abernathy/ch8.txt
written_2//non-fiction/OUP/Abernathy/ch9.txt
written_2//non-fiction/OUP/Abernathy/ch15.txt
written_2//non-fiction/OUP/Abernathy/ch14.txt
written_2//non-fiction/OUP/Rybczynski/ch2.txt
written_2//non-fiction/OUP/Rybczynski/ch3.txt
written_2//non-fiction/OUP/Rybczynski/ch1.txt
written_2//non-fiction/OUP/Kauffman/ch3.txt
written_2//non-fiction/OUP/Kauffman/ch1.txt
written_2//non-fiction/OUP/Kauffman/ch4.txt
written_2//non-fiction/OUP/Kauffman/ch5.txt
written_2//non-fiction/OUP/Kauffman/ch7.txt
written_2//non-fiction/OUP/Kauffman/ch6.txt
written_2//non-fiction/OUP/Kauffman/ch8.txt
written_2//non-fiction/OUP/Kauffman/ch9.txt
written_2//non-fiction/OUP/Kauffman/ch10.txt
written_2//non-fiction/OUP/Fletcher/ch2.txt
written_2//non-fiction/OUP/Fletcher/ch1.txt
written_2//non-fiction/OUP/Fletcher/ch5.txt
written_2//non-fiction/OUP/Fletcher/ch6.txt
written_2//non-fiction/OUP/Fletcher/ch9.txt
```

The find -s command lists all the files and directories inside written_2, but also traverses the file hierarchies in lexicographical order. We also use the grep ".txt" command to check if the text files will also be in alphabetical order.

As we can see from both text files, they are both sorted in alphabetical order. The usefulness is shown in this example, as each file is sorted first by genre, then author, then by chapter.


### Example 2
```
find written_2/*/*/*.txt > find_specific_sort.txt
```

First 30 lines of find_specific_sort.txt
```
written_2/travel_guides/berlitz1/HandRHawaii.txt
written_2/travel_guides/berlitz1/HandRHongKong.txt
written_2/travel_guides/berlitz1/HandRIbiza.txt
written_2/travel_guides/berlitz1/HandRIsrael.txt
written_2/travel_guides/berlitz1/HandRIstanbul.txt
written_2/travel_guides/berlitz1/HandRJamaica.txt
written_2/travel_guides/berlitz1/HandRJerusalem.txt
written_2/travel_guides/berlitz1/HandRLakeDistrict.txt
written_2/travel_guides/berlitz1/HandRLasVegas.txt
written_2/travel_guides/berlitz1/HandRLisbon.txt
written_2/travel_guides/berlitz1/HandRLosAngeles.txt
written_2/travel_guides/berlitz1/HandRMadeira.txt
written_2/travel_guides/berlitz1/HandRMadrid.txt
written_2/travel_guides/berlitz1/HandRMallorca.txt
written_2/travel_guides/berlitz1/HistoryDublin.txt
written_2/travel_guides/berlitz1/HistoryEdinburgh.txt
written_2/travel_guides/berlitz1/HistoryEgypt.txt
written_2/travel_guides/berlitz1/HistoryFWI.txt
written_2/travel_guides/berlitz1/HistoryFrance.txt
written_2/travel_guides/berlitz1/HistoryGreek.txt
written_2/travel_guides/berlitz1/HistoryHawaii.txt
written_2/travel_guides/berlitz1/HistoryHongKong.txt
written_2/travel_guides/berlitz1/HistoryIbiza.txt
written_2/travel_guides/berlitz1/HistoryIndia.txt
written_2/travel_guides/berlitz1/HistoryIsrael.txt
written_2/travel_guides/berlitz1/HistoryIstanbul.txt
written_2/travel_guides/berlitz1/HistoryItaly.txt
written_2/travel_guides/berlitz1/HistoryJamaica.txt
written_2/travel_guides/berlitz1/HistoryJapan.txt
written_2/travel_guides/berlitz1/HistoryJerusalem.txt
```

As we can see, the sort command works even when we specify a path. This can be useful when we simply want to sort a portion of our files without cluttering it with other unnecessary files.

I found this option by using the command 'man find', which gave a description about the -s command.

<img width="549" alt="image" src="https://user-images.githubusercontent.com/98483167/221757514-e8dab7b8-7fba-4401-b5f5-11a4ed4bfab0.png">

## Find - d
### Example 1 
```
find -d written_2/ > find_d_results.txt
```

First 30 lines of find_d_results.txt
```
written_2//non-fiction/OUP/Berk/ch2.txt
written_2//non-fiction/OUP/Berk/ch1.txt
written_2//non-fiction/OUP/Berk/CH4.txt
written_2//non-fiction/OUP/Berk/ch7.txt
written_2//non-fiction/OUP/Berk
written_2//non-fiction/OUP/Abernathy/ch2.txt
written_2//non-fiction/OUP/Abernathy/ch3.txt
written_2//non-fiction/OUP/Abernathy/ch1.txt
written_2//non-fiction/OUP/Abernathy/ch7.txt
written_2//non-fiction/OUP/Abernathy/ch6.txt
written_2//non-fiction/OUP/Abernathy/ch8.txt
written_2//non-fiction/OUP/Abernathy/ch9.txt
written_2//non-fiction/OUP/Abernathy/ch15.txt
written_2//non-fiction/OUP/Abernathy/ch14.txt
written_2//non-fiction/OUP/Abernathy
written_2//non-fiction/OUP/Rybczynski/ch2.txt
written_2//non-fiction/OUP/Rybczynski/ch3.txt
written_2//non-fiction/OUP/Rybczynski/ch1.txt
written_2//non-fiction/OUP/Rybczynski
written_2//non-fiction/OUP/Kauffman/ch3.txt
written_2//non-fiction/OUP/Kauffman/ch1.txt
written_2//non-fiction/OUP/Kauffman/ch4.txt
written_2//non-fiction/OUP/Kauffman/ch5.txt
written_2//non-fiction/OUP/Kauffman/ch7.txt
written_2//non-fiction/OUP/Kauffman/ch6.txt
written_2//non-fiction/OUP/Kauffman/ch8.txt
written_2//non-fiction/OUP/Kauffman/ch9.txt
written_2//non-fiction/OUP/Kauffman/ch10.txt
written_2//non-fiction/OUP/Kauffman
written_2//non-fiction/OUP/Fletcher/ch2.txt
```

The find -d command preforms a depth-first traversal, which lists the .txt files first, and then lists the directory it is in. This may be useful when working with specific inputs where the order of the files and its paths matter.

### Example 2

```
find -d written_2/*/*/* > find_d_results_specific
```

Last 10 lines of find_d_results_specific.txt
```
written_2/travel_guides/berlitz2/Poland-WhatToDo.txt
written_2/travel_guides/berlitz2/Portugal-History.txt
written_2/travel_guides/berlitz2/Portugal-WhatToDo.txt
written_2/travel_guides/berlitz2/Portugal-WhereToGo.txt
written_2/travel_guides/berlitz2/PuertoRico-History.txt
written_2/travel_guides/berlitz2/PuertoRico-WhatToDo.txt
written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt
written_2/travel_guides/berlitz2/Vallarta-History.txt
written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
```

When we run the -d command with a specified path, it displays the files themselves but does not display the directory of certain files with the depth indicated by the command. This may be useful when addressing the question in week 4, in which we were asked to find how many text files there were. If all the txt files were in the same depth, then calling wc on the output file would provide the correct answer.

I found this option by using the command 'man find', which gave a description about the -d command.

<img width="512" alt="image" src="https://user-images.githubusercontent.com/98483167/221761280-f230106d-96c2-4fbb-87f0-56e2823c44be.png">

## Find -size
### Example 1
```
find written_2/ -size -30k > find_size_results.txt
```

First 30 lines of find_size_results.txt
```
written_2/
written_2//non-fiction
written_2//non-fiction/OUP
written_2//non-fiction/OUP/Berk
written_2//non-fiction/OUP/Abernathy
written_2//non-fiction/OUP/Rybczynski
written_2//non-fiction/OUP/Kauffman
written_2//non-fiction/OUP/Kauffman/ch5.txt
written_2//non-fiction/OUP/Fletcher
written_2//non-fiction/OUP/Castro
written_2//non-fiction/OUP/Castro/chQ.txt
written_2//non-fiction/OUP/Castro/chC.txt
written_2//non-fiction/OUP/Castro/chV.txt
written_2//non-fiction/OUP/Castro/chW.txt
written_2//non-fiction/OUP/Castro/chZ.txt
written_2//non-fiction/OUP/Castro/chL.txt
written_2//non-fiction/OUP/Castro/chN.txt
written_2//non-fiction/OUP/Castro/chY.txt
written_2//non-fiction/OUP/Castro/chO.txt
written_2//.DS_Store
written_2//travel_guides
written_2//travel_guides/berlitz1
written_2//travel_guides/berlitz1/HandRLasVegas.txt
written_2//travel_guides/berlitz1/IntroMalaysia.txt
written_2//travel_guides/berlitz1/HandRIstanbul.txt
written_2//travel_guides/berlitz1/HistoryJamaica.txt
written_2//travel_guides/berlitz1/HandRJamaica.txt
written_2//travel_guides/berlitz1/HandRHongKong.txt
written_2//travel_guides/berlitz1/HistoryEgypt.txt
written_2//travel_guides/berlitz1/IntroEdinburgh.txt
```

The find -size command used here lists all the files and directories smaller than 30KBs. As we can see, many files from non-fiction are missing due to being bigger than 30KBs. One instance in which this can be useful is when wanting to sort input files that are too big to be used in a program.

### Example 2
```
find written_2/ -size +40k >find_size_big_results.txt 
```

Last 30 lines of find_size_big_results.txt
```
written_2//travel_guides/berlitz1/WhereToHongKong.txt
written_2//travel_guides/berlitz1/WhereToFWI.txt
written_2//travel_guides/berlitz1/WhereToIstanbul.txt
written_2//travel_guides/berlitz1/WhatToLasVegas.txt
written_2//travel_guides/berlitz2/Berlin-WhereToGo.txt
written_2//travel_guides/berlitz2/Amsterdam-WhereToGo.txt
written_2//travel_guides/berlitz2/Costa-WhereToGo.txt
written_2//travel_guides/berlitz2/Portugal-WhereToGo.txt
written_2//travel_guides/berlitz2/Boston-WhereToGo.txt
written_2//travel_guides/berlitz2/California-WhereToGo.txt
written_2//travel_guides/berlitz2/Bahamas-WhereToGo.txt
written_2//travel_guides/berlitz2/Crete-WhereToGo.txt
written_2//travel_guides/berlitz2/Canada-WhereToGo.txt
written_2//travel_guides/berlitz2/Bali-WhereToGo.txt
written_2//travel_guides/berlitz2/Budapest-WhereoGo.txt
written_2//travel_guides/berlitz2/Barcelona-WhereToGo.txt
written_2//travel_guides/berlitz2/Athens-WhereToGo.txt
written_2//travel_guides/berlitz2/Paris-WhereToGo.txt
written_2//travel_guides/berlitz2/China-WhereToGo.txt
written_2//travel_guides/berlitz2/CstaBlanca-WhereToGo.txt
written_2//travel_guides/berlitz2/Canada-History.txt
written_2//travel_guides/berlitz2/PuertoRico-WhereToGo.txt
written_2//travel_guides/berlitz2/Cuba-WhereToGo.txt
written_2//travel_guides/berlitz2/Nepal-WhereToGo.txt
written_2//travel_guides/berlitz2/CanaryIslands-WhereToGo.txt
written_2//travel_guides/berlitz2/Algarve-WhereToGo.txt
written_2//travel_guides/berlitz2/Beijing-WhereToGo.txt
written_2//travel_guides/berlitz2/Bermuda-WhereToGo.txt
written_2//travel_guides/berlitz2/Vallarta-WhereToGo.txt
written_2//travel_guides/berlitz2/Cancun-WhereToGo.txt
```

This find -size command does the opposite of the first, finding files only bigger than 40Kbs. As we can see, many files from berlitz2 are missing from this command due to being smaller than 40Kbs. This can be useful when sorting faulty input files that are either empty or extremely small.

I found this command by using ChatGpt asking this following question.
> what are some cool things I can do with the bash command -find

ChatGpt responded with the following
> The find command in Bash is a very powerful tool that can help you search for files and directories in a given directory tree. Here are some cool things you can do with the find command:

> Find files based on their name: You can use the -name option to find files that match a specific pattern. For example, the command find . -name "*.txt" will find all files with the extension .txt in the current directory and its subdirectories.

> Find files based on their size: You can use the -size option to find files that match a specific size. For example, the command find . -size +10M will find all files that are larger than 10 megabytes in the current directory and its subdirectories.


## Find -type d
### Example 1
```
find written_2/ -type d 
written_2/
written_2//non-fiction
written_2//non-fiction/OUP
written_2//non-fiction/OUP/Berk
written_2//non-fiction/OUP/Abernathy
written_2//non-fiction/OUP/Rybczynski
written_2//non-fiction/OUP/Kauffman
written_2//non-fiction/OUP/Fletcher
written_2//non-fiction/OUP/Castro
written_2//travel_guides
written_2//travel_guides/berlitz1
written_2//travel_guides/berlitz2
```

This find -type d command looks for all subdirectories in written_2. This can be helpful when we simply want to print the subdirectories in a directory instead of getting all the files as well.

### Example 2
```
find written_2/ -maxdepth 1 -type d
written_2/
written_2//non-fiction
written_2//travel_guides
```

This find -maxdepth -type d command specifies the maximum depth of the subdirectories it will find for. As we can see, the only subdirectories in the output have a maximum depth of 1, and all other subdirectories were not printed.

This can be useful when we want to specify the scope of the subdirectories that we want to look for, restricting the output to a specific depth.

I found this command by using ChatGpt following the same conversation of the previous command.

> Find files based on their type: You can use the -type option to find files of a specific type. For example, the command find . -type d will find all directories in the current directory and its subdirectories.

I replied:
>how can I use -d to only find subdirectories of a specific depth?


ChatGpt Replied:
> If you want to restrict the search to only the current directory and not its subdirectories, you can use the -maxdepth option as follows:

> ``` find . -maxdepth 1 -type d ```

>Here, the -maxdepth option with a value of 1 specifies that only the current directory should be considered and not its subdirectories. The -type d option specifies that only directories should be considered. This will find all subdirectories in the current directory only.


