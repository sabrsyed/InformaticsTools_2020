Problem Set Answers from Mike
=============================

1. **Log into your machine.** 
This is easy on a mac. For a remote server you would have to use ssh. On a mac you open a terminal window and you are ready to go
     ```sh
     jabberwocky:scratch mcampbel$
     ```

2. **What is the full path to your home directory?**
Use pwd for this
	```sh
	jabberwocky:scratch mcampbel$ pwd
	/Users/mcampbel/foo/scratch
	```
3. **Go up one directory and How many directories?**
 * **Go up one directory?**
       	  Use cd and ls for this
	```sh
	jabberwocky:scratch mcampbel$ cd ..
	jabberwocky:foo mcampbel$
	```
 * **How many directories?**
   
	```sh
	jabberwocky:foo mcampbel$ ls -1 -F
	all_betas_no_missing_data.txt
	cns_p_ctg_uc.fasta.gz
	get_10000_exons.py*
	gff3_stuff.py*
	head_hexamer_counts.txt
	internal-exons.fasta
	multiple_trans_example.gff
	pn_chr.fa.gz
	quickmerge/
	repeat_notes_from_george.txt
	scratch/
	smaller_genes_only.gff
	subset_fasta.py*
	tail_hexamer_counts.txt
	tids.txt
	tig00000022.gff
	v4_pc_genes_longest_cds.gff
	```
looks like I have 2 directories and 15 files

Another way to count the items in a directory

	
	[ss45w@ghpcc06 home]$ cd ~
	[ss45w@ghpcc06 ~]$ pwd
	/home/ss45w
	[ss45w@ghpcc06 ~]$ cd ..
	[ss45w@ghpcc06 home]$ pwd
	/home
	[ss45w@ghpcc06 home]$ ls -1 | wc -l 
	2833
	[ss45w@ghpcc06 home]$ ls | wc -l
	2833
	

4. **Make a directory called problemsets.**
Use mkdir for this one
	```sh
	jabberwocky:foo mcampbel$ mkdir problemsets
	```
5. **Navigate into this new directory called problemsets. Verify that you are in the correct directory by using pwd.** 
	```sh
	jabberwocky:foo mcampbel$ cd problemsets
	jabberwocky:problemsets mcampbel$ pwd
	/Users/mcampbel/foo/problemsets
	```
6. **Use wget to copy https://raw.githubusercontent.com/srobb1/pfb2017/master/files/sequences.nt.fa from the web into your problemsets directory. If wget is not available on your system, use curl -O as an alternative.**
we didn't have wget on the macs in class so we had to use curl
	```sh
	jabberwocky:problemsets mcampbel$ curl -O https://raw.githubusercontent.com/srobb1/pfb2017/master/files/sequences.nt.fa
	  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
	                                 Dload  Upload   Total   Spent    Left  Speed
	100 10267  100 10267    0     0  21711      0 --:--:-- --:--:-- --:--:--  113k
	```
but wget would work too
	```sh
	wget https://raw.githubusercontent.com/srobb1/pfb2017/master/files/sequences.nt.fa
	--2017-10-16 19:30:36--  https://raw.githubusercontent.com/srobb1/pfb2017/master/files/sequences.nt.fa
	Resolving raw.githubusercontent.com... 151.101.20.133
	Connecting to raw.githubusercontent.com|151.101.20.133|:443... connected.
	HTTP request sent, awaiting response... 200 OK
	Length: 10267 (10K) [text/plain]
	Saving to: 'sequences.nt.fa.1'
	
	sequences.nt.fa.1     100%[==========================>]  10.03K  --.-KB/s   in 0s     
	
	2017-10-16 19:30:37 (59.0 MB/s) - 'sequences.nt.fa.1' saved [10267/10267]
	```
7. **This is a 5 part question** 
 * **How many lines does this file contain?**
	```sh
	jabberwocky:problemsets mcampbel$ wc -l sequences.nt.fa 
	     148 sequences.nt.fa
	```
 * **How many characters? (Hint: check out the options of wc)**
	```sh
	jabberwocky:problemsets mcampbel$ wc -c sequences.nt.fa 
	   10267 sequences.nt.fa
	```

 * **What is the first line of this file? (Hint: read the man page of head)**
	```sh
	jabberwocky:problemsets mcampbel$ head -n 1 sequences.nt.fa 
	>NM_001126114.2 Homo sapiens tumor protein p53 (TP53), transcript variant 3, mRNA
	```
 * **What are the last 3 lines? (Hint: read the man page of tail)***
	```sh
	jabberwocky:problemsets mcampbel$ tail -n 3 sequences.nt.fa 
	TTTATAGCTGTTGGAAGGACTAGGTCTTCCCTAGCCCCCCCAGTGTGCAAGGGCAGTGAAGACTTGATTG
	TACAAAATACGTTTTGTAAATGTTGTGCTGTTAACACTGCAAATAAACTTGGTAGCAAACACTTCCAAAA
	AAAAAAAAAAAAAA
	```

 * **How many sequences are in the file? (Hint: use grep) (Note: The start of a sequence is indicated by a > character.)**
	```sh
	jabberwocky:problemsets mcampbel$ grep '>' sequences.nt.fa | wc -l
	       2
	```
Note: you can also do the counting with the grep option -c
	```sh
	jabberwocky:problemsets mcampbel$ grep -c '>' sequences.nt.fa 
	2
	```


