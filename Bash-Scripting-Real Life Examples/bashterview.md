## Creating Directory to Work

```bash
mkdir bashmore
cd bashmore
```

## 01. What is bash script?

* Bash komut dosyası bir shell programlama dilidir.Genel olarak, her bir komutu ayrı olarak zaman ve çaba gerektiren her bir komutu yazarak terminalden birçok shell komutu çalıştırıyoruz.Aynı komutları tekrar çalıştırmamız gerekiyorsa, tüm komutları tekrar terminalden yürütmek zorundayız.Ancak bir Bash shell`i kullanarak, birçok shell komutu ifadesini tek bir bash dosyasında saklayabilir ve dosyayı tek bir komutla istediğiniz zaman çalıştırabiliriz.Birçok sistem yönetimi ile ilgili görevler, program kurulumu, disk yedekleme, günlükleri değerlendirme, vb. Uygun Bash komut dosyası kullanılarak yapılabilir.


## 02. What are the advantages of using bash scripts?

* Bash Script, aşağıda açıklanan birçok avantaja sahiptir:
  * Kullanımı ve öğrenmesi kolaydır.
  * Bir bash script`i yazarak sık sık çalışması gereken birçok manuel görev yapılabilir.
  * Çoklu shell komutlarının sırası tek bir komutla yapılabilir.
  * Bir Linux işletim sisteminde yazılmış bash script, diğer Linux işletim sisteminde kolayca yürütülebilir.Yani, taşınabilir.
  * Bash'te hata ayıklama, diğer programlama dillerinden daha kolaydır.
  * Komut satırı sözdizimi ve terminalde kullanılan komutlar, bash komut dosyasında kullanılan komutlara ve sözdizimine benzerdir.
  * Bash komut dosyası, diğer komut dosyaları ile bağlantı kurmak için kullanılabilir.


## 03. Mention the disadvantages of bash scripts

* Bash komut dosyasının bazı dezavantajları aşağıda belirtilmiştir:

    * Diğer dillerden daha yavaş çalışır.
    * Uygun olmayan komut dosyası tüm işleme zarar verebilir ve karmaşık bir hata oluşturabilir.
    * Büyük ve karmaşık bir uygulama geliştirmek için uygun değildir.
    * Diğer standart programlama dilleriyle karşılaştırıldığında daha az veri yapısı içerir.
 

## 04. What types of variables are used in bash?

* Bash betiğinde iki çeşit değişken kullanılabilir.Bunlar:
 
### Sistem değişkenleri

* Linux işletim sisteminin önceden tanımlanmış ve bakımı olan değişkenler sistem değişkenleri olarak adlandırılır. Bu değişkenlerin varsayılan değerleri gereksinimlere göre değiştirilebilir. Sistem degiskenleriyle calisirken buyuk harf kullanmak best practice`dir.
 
`set`, `env` and `printenv` komutları, sistem değişkenlerinin listesini yazdırmak için kullanılabilir.
Example:
```bash
#!/bin/bash
# Printing System Variables
 
#Print Bash shell name
echo $BASH
 
# Print Bash shell Version
echo $BASH_VERSION
 
# Print Home directory name
echo $HOME

```
 
### Kullanıcı tanımlı değişkenler
*  Kullanıcılar tarafından oluşturulan ve korunan değişkenler denir. Ayrıca yerel değişkenler olarak adlandırılırlar.Bu tür değişkenler küçük harf veya büyük harf veya hem büyük hem de küçük harfler kullanılarak ilan edilebilir.Ancak değişkenleri sistem değişkenlerinden ayırt etmek için tüm büyük harfleri kullanmaktan kaçınmak daha iyidir.

* Example:

```bash
#!/bin/bash
 
num=100
echo $num
```

## 05. How to declare and delete variables in bash?

* Değişken, BASH'de veri türü olmadan ilan edilebilir. Bash değişkeni, zaman bildirimindeki değişkenin veri türünü tanımlamak için declare komutuyla ilan edilir.

* `–r, -i, -a, -A, -l, -u, -t` and `–x` options can be used with declare command to declare a variable with different data types.

Example:

```bash
#!/bin/bash
 
#Declare variable without any type
num=10
 
#Values will be combined but not added
result=$num+20
echo $result
 
#Declare variable with integer type
declare -i num=10
 
#Values will be added
declare -i result=num+20
echo $result

```

## 06. How to add comments in a bash script?

* Single line and multi-line comments can be used in bash script. ‘#‘ symbol is used for single-line comment. `<<` symbol with a delimiter and ‘:’ with single (‘) are used for adding multi-line comment.

Example:

```bash
#!/bin/bash
#Print the text [Single line comment]
echo "Bash Programming"
<<addcomment
Calculate the sum
Of two numbers [multiline comment]
addcomment
num=25+35
echo $num
: '
Combine two
String data [multiline comment]
'
```

## 07. How can you combine strings in a bash script?

* String values can be combined in bash in different ways. Normally, the string values are combined by placing together but there are other ways in bash to combine string data.

Example:

```bash
#!/bin/bash
#Initialize the variables
str1="PHP"
str2="Bash"
str3="Perl"
 
# Print string together with space
echo $str1 $str2 $str3
 
#Combine all variables and store in another variable
str="$str1, $str2 and $str3"
 
#Combine other string data with the existing value of the string
str+=" are scripting languages"
 
#Print the string
echo $str
``` 

## 08. Which commands are used to print output in bash?

* `echo` and `printf` commands can be used to print output in bash. `echo` command is used to print the simple output and `printf` command is used to print the formatted output.

Example:

```bash
#!/bin/bash
 
#Print the text
echo "Welcome to LinuxHint"
site="linuxhint.com"

#Print the formatted text
printf "%s is a popular blog site\n" $site
# %s stands for string variable we just defined
 
```

## 09. How to take input from the terminal in bash?

* `read` command is used in a bash script to take input from the terminal.

Example:

```bash
cat > name.sh
#!/bin/bash
#Print message
echo "Enter your name"
#Take input from the user
read name
# Print the value of $name with other string
echo "Your name is $name"

./name.sh
``` 

## 10. Is bash a weakly typed language? Why?

* Evet, bash, zayıf veya yazılmış bir dil olarak kabul edilir, çünkü değişken bildirimi sırasında verilerin türünü beyan etmemesi gerekmez.Tüm Bash değişkenleri varsayılan olarak bir dize olarak değerlendirilir ve değişkenin türü geçerli değere göre ayarlanacaktır.Veri türlerine sahip bash değişkenleri, belirli bir seçeneğe sahip Decare komutunu kullanarak tanımlanabilir.Ancak veri türlerini tanımlamak için seçenekler sınırlıdır ve her tür veri türünü desteklemez.Örneğin, float veri türü declare komutu kullanılarak bildirilemez.

Example:

```bash
#!/bin/bash

#The data type of $myVar is string by default
myVar=29

# Print the variable
echo $myVar

# Declare integer variable $number with the value 67
declare -i number=67

#Print the variable
echo $number

# Assign string data into the numeric variable. The following line will generate
# syntax error and the value of $number will not change
number="I like bash"
echo $number
``` 


## 11. How to declare and access an array variable in bash?

* Hem numeric hem de birleştirici diziler, bir bash script tarafından desteklenir.Bir dizi değişkeni declared veya undeclared ilan edilebilir.

Example:

```bash
#!/bin/bash                                                                
                                                                           
# Declare a simple numeric array
arr1=( CodeIgniter Laravel ReactJS )

# Print the first element value of $arr1                                        
echo ${arr1[0]}      
                 
# Declare a numeric array using declare command                                    
declare -a arr2=( HTML CSS JavaScript )  
     
# Print the second element value of $arr2                            
echo ${arr2[1]}              
           
# Declare an associative array using declare statement                                  
declare -A arr3=( [framework]=Laravel [CMS]=Wordpress [Library]=JQuery )

# Print the third element value of $arr3    
echo ${arr3[Library]}
All elements of an array can be accessed by using any loop or ‘*’ symbol as an array index.

# To reach values
$ echo ${arr3[*]}

# To reach keys
echo ${!arr3[@]}
``` 

## 12. How can conditional statements be used in bash?

* Programlama dilinde en yaygın conditional statement, IF/ELIF-ELSE ifadesidir.BASH'deki IF/ELIF-ELSE ifadesinin indenti, diğer programlama dillerinden biraz farklıdır.IF/ELIF-ELSE ifadesi, bir bash komut dosyasında uc şekilde ilan edilebilir ve her türde 'if' bloğu 'fi' ile kapatılmalıdır.


* First Use(w/o ;)

```bash
if [ $n -gt 100 ]
  then
    echo "$n is less than 100"
elif [ $n -gt 50 ]
  then
    echo "$n is less than 50"
fi
```

* Second use(with ;)

```bash
$ if [ $n -gt 100 ];   then     echo "$n is less than 100"; elif [ $n -gt 50 ];   then     echo "$n is less than 50"; fi
```

* Final use(mixed)

```bash
#!/bin/bash
# Assign a value to $n
n=30
# Check $n is greater than 100 or not
if [ $n -gt 100 ]; then
    echo "$n is less than 100"
# Check $n id greater than 50 or not
elif [ $n -gt 50 ]; then
    echo "$n is less than 50"
else
    echo "$n is less than 50"
fi
``` 

## 13. How to compare values in bash?

* Six types of comparison operators can be used in bash to compare values. There are two ways to use these operators in bash depending on the data type.  These are mentioned below.


* **==**	`-eq`	It is used to check equality
* **!=**	`-ne`	It is used to check inequality
* **<**	`-lt`	It is used check the first value is less than the second value or not
* **>**	`-gt`	It is used check the first value is greater than the second value or not
* **<=**	`-le`	It is used check the first value is less than or equal to the second value or not
* **>=**	`-ge`	It is used check the first value is greater than or equal to the second value or not


Example:

```bash
#!/bin/bash
# Initialize $n
n=130
o="even"
# Check $n is greater than or equal to 100 or not using ‘–ge’.
if [ $n -ge 100 ]; then
     echo "$n is greater than or equal to 100"
else
     echo "$n is less than 100"
fi
# Check $n is even or odd using ‘==’ operator
if (( $o == "even" )); then
     echo "The number is even"
else
     echo "The number is odd"
fi
``` 

## 14. Which conditional statement can be used as an alternative to if-elseif-else statements in bash?

* `case` İfade, alternatif bir IF ifadesi olarak kullanılabilir.Bash komut dosyalarındaki 'Case' ifadesi için sözdizimi, diğer programlama dillerinden farklıdır.'Case' bloğu, Bash'teki 'Esac' ifadesiyle kapatıldı.'Break' ifadesi 'case' bloğu içinde bloktan sonlandırmak için kullanılmaz.

Syntax:

```bash
case  in
Match pattern 1) commands;;
Match pattern 2) commands;;
……
Match pattern n) commands;;
esac
Example:

#!/bin/bash
#Initialize the variable $ticket
ticket=101
# Compare the value of $ticket with 23, 101 and 503
case $ticket in
23)
# Print message if the value is 23  
echo "You got the first prize";;
101)
# Print message if the value is 101
echo  "You got the second prize";;
503)
# Print message if the value is 503
echo  "You got the third prize";;
*)
# Print message if the value does not match with 23, 101 and 503
echo "Sorry, try for the next time"
exit 0;;
esac
```

## 15. What different types of loops can be used in bash?

* Three types of loops are supported by a bash script. These are `while`, `for` and `until` loops. Loops in bash check the condition at the start of the loop. 
    * While loop works until the condition remains true. Sart saglanmadigi zaman loop sonlanir.
    * until loop works until the condition remains false. Sart saglandigi zaman loop sonlanir.
    * For loop works until we want it to work.
*  The uses of these three loops are shown in the following example.

Example:

```bash
#!/bin/bash
# Initialize $n
n=5
# Calculate the square of 5-1 using while loop
while [ $n -gt 0 ]
do
   sqr=$((n*n))
   echo "The square of $n is $sqr"
   ((n--))
done

# Calculate the square of 5-1 using for loop
for (( i=5; i>0; i-- ))
do
   sqr=$((i*i))
   echo "The square of $i is $sqr"
done

# Initialize $x
x=5
# Calculate the square of 5-1 using until loop
until [ $x -le 0 ]
do
   sqr=$((x*x))
   echo "The square of $x is $sqr"
   ((x--))
done
```

## 16. How to cut and print some part of a string data in bash?

* Bash'in string verilerin bir kısmını kesmek için diğer diller gibi yerleşik bir işlevi yoktur.Ancak parametre genişletmesini kullanarak herhangi bir string değeri bash cinsinden kesilebilir.String verilerinin herhangi bir bölümünü kesmek için bir kolonla ayrılarak parametre genişletmesinde üç bölüm tanımlanabilir.Burada, ilk iki parça zorunludur ve son bölüm isteğe bağlıdır.İlk bölüm, kesmek için kullanılacak ana string değişkenini içerir, ikinci bölüm, string'in kesileceği ve üçüncü bölümün kesme dizesinin uzunluğu olduğu için başlangıç konumudur.Başlangıç pozisyonu 0'dan sayılmalıdır ve uzunluk, kesme değerini almak için ana string 1'den sayılmalıdır.

Example:

```bash
#!/bin/bash
# Initialize a string value into $string
string="Python Scripting Language"
# Cut the string value from the position 7 to the end of the string
echo ${string:7} # Index 7 ve sonrasini kes
# Cut the string value of 9 characters from the position 7
echo ${string:7:9} # Index 7 den sonraki 9 degeri kes
```

## 17. Mention some ways to perform arithmetic operations in bash?
Arithmetic operations can be done in multiple ways in bash. ‘let’, ‘expr’, ‘bc’ and double brackets are the most common ways to perform arithmetic operations in bash. The uses of these commands are shown in the following example.

Example:
```bash
#!/bin/bash                                                                      
# Calculating the subtraction by using expr and parameter expansion
var1=$( expr 120 - 100 )
# print the result
echo $var1
# Calculate the addition by using let command
let var2=200+300
# Print the rsult
echo $var2
# Calculate and print the value of division using ‘bc’ to get the result
# with fractional value
echo "scale=2; 44/7" | bc
# Calculate the value of multiplication using double brackets
var3=$(( 5*3 ))
# Print the result
echo $var3
```

## 18. How to check a directory exists or not using bash?

* Bash has many test commands to check if a file or directory exists or not and the type of the file. ‘-d’ option is used with a directory path as a conditional statement to check if the directory exists or not in bash. If the directory exists, then it will return true otherwise it will return false. Before that, let's use the simplified version of it:

```bash
# Simplified Version
$ [[ -d /c/Users/talfi ]] && echo "This directory exists!"
```

Example:
```bash
#!/bin/bash                                                                  
# Assign the directory with path in the variable, $path
path="/c/Users/talfi"
# Check the directory exists or not
if [ -d "$path" ]; then
   # Print message if the directory exists
   echo "Directory exists"
else
   # Print message if the directory doesn’t exist
   echo "Directory not exists"
fi
```

## 19. How can a bash script be terminated without executing all statements?

* Using ‘exit’ command, a bash script can be terminated without executing all statements. The following script will check if a particular file exists or not. If the file exists, then it will print the total characters of the file and if the file does not exist then it will terminate the script by showing a message.

* To know more about exit codes, visit [here](https://www.cyberciti.biz/faq/linux-bash-exit-status-set-exit-statusin-bash/)

Example:

```bash
#!/bin/bash

# Initialize the filename to the variable, $filename
filename="course.txt"

# Check the file exists or not by using -f option
if [ -f "$filename" ]; then
    # Print message if the file exists
    echo "$filename exists"
else
    # Print message if the file doesn't exist
    echo "$filename not exists"
    # Terminate the script
    exit 1
    # exit 1 means exit code 1. Exit code 1 means operation not permitted
fi

# Count the length of the file if the file exists
length=`wc -c $filename`

# Print the length of the file
echo "Total characters - $length"
```

## 20. What are the uses of break and continue statements in bash?

* **break** statement is used to terminate from a loop without completing the full iteration based on a condition and 
* **continue** statement is used in a loop to omit some statements based on a condition. The uses of break and continue statements are explained in the following example.

Example:

```bash
#!/bin/bash
# Initialize the variable $i to 0 to start the loop
i=0
# the loop will iterate fot 10 times
while [ $i -le 10 ]
do
    # Increment the value $i by 1
    (( i++ ))
    # If the value of $i equal to 8 then terminate the loop by using 'break' statement
    if [ $i -eq 8 ]; then
         break;
    fi
    # If the value of $i is greater than 6 then omit the last statement of the loop
    #  by using continue statement
    if [ $i -ge 6 ]; then
         continue;
    fi
    echo "the current value of i = $i"
done

# Print the value of $i after terminating from the loop
echo "Now the value of i = $i"
```


## 21. Mention some options that are used to test files

* Many options are available in bash to test file. Some options are mentioned below.

```bash
Option	Description
-f	It is used to test the file exists and it is a regular file.
-e	It is used to test the file exists only.
-r	It is used to test the file exists and it has read permission.
-w	It is used to test the file exists and it has to write permission.
-x	It is used to test the file exists and it has execution permission.
-d	It is used to test the directory exists.
-L	It is used to test the file exists and It is a symbolic link.
-S	It is used to test the file exists and It is a socket.
-b	It is used to test the file is a block device.
-s	It is used to check the file is not zero sizes.
-nt	It used to check the content of the first file is newer than the second file. For example, file1 -nt file2 indicates that file1 is newer than file2.
-ot	It used to check the content of the first file is older than the second file. For example, file1 -ot file2 indicates that file1 is older than file2.
-ef	It is used to check that two hard links refer to the same file. For example, flink1 -ef flink2 indicates that flink1 and flink2 are hard links and both refer to the same file.

# create yirmibir.sh and inject the following code in it.

cat > yirmibir.sh

file="/c/Users/talfi/bashmore/test.sh"

if [ -r $file ]
then
   echo "File has read access"
else
   echo "File does not have read access"
fi

if [ -w $file ]
then
   echo "File has write permission"
else
   echo "File does not have write permission"
fi

if [ -x $file ]
then
   echo "File has execute permission"
else
   echo "File does not have execute permission"
fi

if [ -f $file ]
then
   echo "File is an ordinary file"
else
   echo "This is sepcial file"
fi

if [ -d $file ]
then
   echo "File is a directory"
else
   echo "This is not a directory"
fi

if [ -s $file ]
then
   echo "File size is not zero"
else
   echo "File size is zero"
fi

if [ -e $file ]
then
   echo "File exists"
else
   echo "File does not exist"
fi
```

## 22. How to find out the length of a string data? 

* ‘expr’, ‘wc’ and ‘awk’ commands can be used to find out the length of a string data in bash. ‘expr’ and ‘awk’ commands use length option, ‘wc’ command uses ‘–c’ option to count the length of the string.

Example:

```bash
The uses of the above commands are shown in the following script.

#!/bin/bash                      
# Count length using `expr` length option
echo `expr length "I like PHP"`
# Count length using `wc` command
echo "I like Bash" | wc -c
# Count length using `awk` command
echo "I like Python" | awk '{print length}'
```