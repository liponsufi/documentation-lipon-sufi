# Linux
```cmd
alias ls='ls --color=never'
```
## Command Name + Option + Arguments
```cmd
cd / (go to root directory)
less mehedi.txt (কমান্ডটি লিনাক্সে কোনো বড় ফাইল পড়ার বা দেখার (viewing) জন্য ব্যবহার করা হয়।)
```
### Copy and move
```cmd
1. cp source_folder destination (for file)
2. mv source_folder destination (for file)

for folder
1. cp -r source_folder destination_folder
2. mv -r source_folder destination_folder
```
### Cat

```cmd
show what actually in the file

1. cat file name 
2. cat -n file name (show line number)
3. cat a.txt b.txt > c.txt (concatanation to c from a+b)
4. cat a.txt > b.txt (override)
5. cat a.txt >> b.txt (append)
```
### ncal (Current Month Show)
### Ls (list)
```cmd
show list

1. ls 
2. ls -a (for hidden file)
3. ls -l (for long format)
```
### Mkdir
```cmd
create folder

1. mkdir folder_1 folder_2
2. mkdir -p folder/under_the_folder/also_under
```
### Remove folder
```cmd
1. rmdir folder_name (only empty file)
2. rm -rf forlder_name (for not empty) forced to delete
```
### Rename the file name
```cmd
mv purono_nam.txt notun_nam.txt
```
### nano
```cmd
alt + u (for undo)
ctrl + shift + c (for copy)
ctrl + shift + v (for paste)
ctrl + k (for cut)
ctrl + u (for paste)
```
### head and tail
```cmd
1. head file.txt (show first 5 sentence)
2. head -4 mehedi.txt (only show first 4 line)
3. tail file.txt (show last 5 sentence)
4. tail -4 mehedi.txt (show only last 4 line)
5. tail -f mehedi.txt (কমান্ডটি লিনাক্সে রিয়েল-টাইম বা লাইভ ফাইল মনিটরিং করার জন্য অত্যন্ত জনপ্রিয় একটি কমান্ড।)
```