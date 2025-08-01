# **Searching and Filtering**

## **Grep**

## **Syntax**
- grep [options] pattern [file…] 

### **Options**
-i.           Case-insensitive search
-r or -R. Recursive search through directories
-v.           Invert match ( show lines not matching)
-n.          Show lines number 
-l.           Show filenames with matches only
-c.          Count matching lines
—color.  Highlight matches

#### **Examples**
- grep -i "password" /etc/passwd


## **egrep**
- extended grep (supports extended regex( regular expression))

## **Syntax**
- egrep [OPTIONS] PATTERN [FILE...]

### **Options**
-i	Ignore case.
-v	Invert match (show non-matching).
-r	Recursive search.
-c	Count matches.

#### **Wxamples**
Find lines with “error” or “fail”:
egrep "error|fail" logfile.txt

Case-insensitive search:

egrep -i "warning" logfile.txt

Recursive search for .conf files:

egrep -r "Listen" /etc/apache2/


## **fgrep**
- Literal grep (searches fixed strings, no regex)

## **Suntax**
- fgrep [OPTIONS] PATTERN [FILE...]

### **Options**
-i	Ignore case.
-v	Invert match.
-r	Recursive search.
-c	Count matches.

#### **Examples**
Find exact string:
fgrep "if [ $USER == root ]" script.sh

Recursive literal search:
fgrep -r "127.0.0.1" /etc/

## **cut**
- extract sections from lines of text

## **Syntax**
- cut [OPTIONS] [FILE...]

### **Options**
-b LIST	Extract specific bytes.
-c LIST	Extract specific characters.
-d DELIM	Specify field delimiter (default is tab).
-f LIST	Specify fields (with -d).

#### **Examples**
Get first 10 characters of each line:
cut -c 1-10 file.txt

Extract first column (fields delimited by :):
cut -d ":" -f 1 /etc/passwd

Combine with sort:
cut -d ":" -f 1 /etc/passwd | sort



## **sed** 
- Stream editor for text manipulation

## **Syntax**
-sed [OPTIONS] 'SCRIPT' [FILE...]

### **Options**
i	Edit files in place (overwrite).
-n	Suppress automatic printing.
-e	Add script commands.

#### **Examples**
sed 's/foo/bar/g' file.txt	Replace “foo” with “bar” globally.
sed -n '5,10p' file.txt	Print lines 5–10.
sed '/^#/d' file.txt	Delete comment lines starting with #.



## **awk**
- Text processing and reporting

## **Syntax*
- awk [OPTIONS] 'PATTERN { ACTION }' [FILE...]

### **Options**
-F	Set field separator (default: space).

#### **Examples**
awk '{print $1}' file.txt	Print first column.
awk -F: '{print $1}' /etc/passwd	Print usernames from passwd.
awk '$3 > 1000' /etc/passwd	Print lines where field 3 > 1000.



## **sort**
-Sort text lines

## **Syntax**
- sort [OPTIONS] [FILE]

### **Options**
-r	Reverse sort order.
-n	Numeric sort.
-u	Unique lines only (like uniq).
-k	Sort by specific field/column.

### **Examples**
sort -n -k2 file.txt
Sort numerically on the second column.



## **uniq**
- Filter out repeated lines

## **Syntax**
- uniq [OPTIONS] [INPUT [OUTPUT]]

## **Options**
-c	Prefix lines with counts.
-d	Show only duplicate lines.
-u	Show only unique lines.

### **Examples**
sort file.txt | uniq -c
Counts unique sorted lines.

