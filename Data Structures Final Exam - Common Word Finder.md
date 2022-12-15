---
title: Data Structures Final Exam - Common Word Finder
---

* やりましょう
* 注意点、後で確認する
  * [ ] You may not use any of the Java Collections including ArrayList, LinkedList, HashMap, TreeMap, etc.
  * [ ] Be sure to cite the source in an inline comment above the lines of code you reference.
  * [ ] wordの定義rule
  * [ ] args\[1\] invalid capitalizationならinvalid
  * [ ] args\[2\] positiveかつinteger
  * 個人的に気になったこと
    * error exit codeは1でOK?
    * 関数とか分けた方が良い?
    * 余計なものimportしていない?
    * 文字列処理、色々つらそう
      * まあ楽に捉えれば良いんだろうけど
      * isAlphabetic かつ LOWERCASE_LETTERでも、a-zとは違いそう
      * https://www.compart.com/en/unicode/category/Ll
    * 最後のwordの処理の仕方、問題ありそう
* 考えた事
  * AVLMap, BSTMap、なんだっけ
    * keyでBSTとAVLを作っているということか
      * nodeのvalueがvalue
  * やりかた
    * Bucketsort?
      * でもcount = 1とかで大量にあるのを結局sortしなきゃ?
        * avl/bstだと不要だな
        * heapの場合のみquicksort
      * Θ(N) + Θ(N * M log M)
        * N = number of values
        * M = word count of one value
        * N\times M = total word amount
    * Array
      * arrayに全部突っ込んでsort
      * NlogN

 > 
 > Your goal is to use three of the data structures you developed this semester to create a 
 > program that finds the 𝑛𝑛 most common words in a document. BSTMap, AVLTreeMap, and 
 > MyHashMap implement the MyMap interface. So, with proper object-oriented 
 > programming technique, specifically the use of polymorphism, you can create any one of 
 > these data structures and refer to it from a MyMap reference. Though all three classes 
 > implement the same interface, their methods are implemented very differently, leading to 
 > different execution times on the computer. You will time your program’s execution to see 
 > how each of the data structures performs. 
 > 
 > You will develop a command line Java application to find the 𝑛𝑛 most common words in a 
 > document. The name of the public class must be CommonWordFinder, and it must reside in 
 > a file named CommonWordFinder.java. 
 > 
 > Parsing Command Line Arguments 
 > The program will take in either two or three command line arguments. If the number of 
 > arguments supplied is incorrect, the program will print the usage message "Usage: java CommonWordFinder \<filename \<bst|avl|hash \[limit\]" 
 > to stderr and exit in failure. 
 > 
 > The program will first verify that the input file exists. If it does not, the program will print 
 > the message "Error: Cannot open file '" + args\[0\] + "' for input." 
 > to stderr, where args\[0\] contains the name of the file the user is attempting to process, and 
 > exit in failure. 
 > 
 > The program will then try to parse the command line for which data structure the user 
 > wishes to use. Valid strings are “bst”, “avl”, and “hash”. Any other string including those 
 > with different capitalization is considered invalid, causing the program to print the message "Error: Invalid data structure '" + args\[1\] + "' received." 
 > to stderr, where args\[1\] contains the data structure string name, and exit in failure. 
 > 
 > At this point, the program will now attempt to process the limit command line argument, if 
 > it exists. The limit must be a positive integer. If the command line argument is invalid, the 
 > program will print the message "Error: Invalid limit '" + args\[2\] + "' received." 
 > to stderr, where args\[2\] contains the string form of limit, and exit in failure. Since limit is an 
 > optional command line argument, it may not be supplied. When the limit is not specified on 
 > the command line, the limit will be set to 10. 
 > 
 > Capstone - 2 
 > 
 > Parsing the Input File 
 > After validating all command line arguments, you’ll need to instantiate either a BSTMap, 
 > AVLTreeMap, or MyHashMap. You must create a reference to the interface rather than the 
 > class itself, as in: MyMap\<String, Integer> map = new BSTMap\<\>(); 
 > No credit will be given if your map variable is not of type MyMap. The key-value pairs are 
 > String-to-Integer, where String is the word and Integer is the number of times the word is 
 > found in the document. 
 > 
 > When parsing the input file, follow these simple rules for breaking up the text into words. 
 > Lowercase letters (a-z) and single quotes (') are legal characters for words. Hyphens (-) are 
 > legal too, as long as they are not the first character in a word. Uppercase letters (A-Z) are 
 > converted to lowercase letters before putting them into a word. Words are separated by 
 > end-of-line characters and spaces. Every time your program parses a word for the first time, 
 > it is inserted into the map with a count of 1. If it has been seen before, the count associated 
 > with it is incremented by 1. 
 > If an I/O error occurs as the reading takes place, the program will print the message "Error: An I/O error occurred reading '" + args\[0\] + "'." 
 > to stderr, where args\[0\] contains the name of the file the user is attempting to process, and 
 > exit in failure. 
 > 
 > Displaying the Output 
 > The first line of output will display the following: Total unique words: some positive integer 
 > Then up to limit words and their counts will be displayed. If the limit exceeds the total 
 > number of unique words in the file, then all the words in the file should be displayed. The 
 > output must be printed meticulously. Starting with 1, each line begins with the number of 
 > the word and a period. The number must be right-aligned to the width of the largest 
 > number. For example, if 1000 words are do be displayed, the first line will have 3 spaces, 
 > the number 1, and then a period. Line 10 will have two, line 100 will have one, and line 1000 
 > will have no leading spaces. 
 > The word in all lowercase letters appears after the period, left-aligned with one space 
 > between the period and the word. If two lowercase words have the same count, the words 
 > should be alphabetized in the output. Finally, the count of the words appears at the end of 
 > each line, with one space between the longest word and the count. Use 
 > System.lineSeparator() to properly get the system-dependent String for new line characters. 
 > Every line of output ends with a visible character, not whitespace. 

* [Capstone-CommonWordFinder.pdf](Capstone-CommonWordFinder.pdf)
