# シェルスクリプトを書くことができる

## 1. Hello

シェルスクリプトのファイルを作成し、「Hello!」と出力してください。

なお、シェルスクリプトを実行する際にはファイルに実行権限が付与されている必要があることに気を付けてください。
```shell
$ touch hello.sh  
$ ls -l  
-> -rw-r--r-- 1 root root 0  9月 30 04:41 hello.sh  
$ chmod u+x hello.sh  
$ ls -l  
-> -rwxr--r-- 1 root root 0  9月 30 04:41 hello.sh  

$ vi hello.sh  

i （挿入モード）  
```
```bash
#/bin/bash  
echo "Hello!"
```  
```
esc（挿入モード終了）  
:wq（変更を保存して終了）  
```

```
$ ./hello.sh
```

## 2. 標準入力から値を受け取る

シェルスクリプトのファイルに「What's your name?」と出力し、ユーザーに名前の入力を求めます。その後ユーザーが入力した名前に対して、「Welcome, $name!」（$name は入力された名前）と出力する処理を追加してください。

```shell
$ touch name.sh  
$ chmod u+x name.sh
```
---
```bash
#!bin/bash
read -p "What's your name?"
echo "Welcome, ${name}!"
```
---
```shell
$ ./name.sh（実行）
```

## 3. 条件分岐

四則演算を行う電卓を作成してください。実行すると以下の挙動になります。

```bash
Enter two numbers:
10 # ユーザーが入力
11 # ユーザーが入力
Choose an arithmetic operation (+, -, *, /):
+ # ユーザーが入力
The result:21
```

なお、割り算の時の割る数が 0 であるケースや、演算子の記号 +, -, *, / が合致しないケースを考慮するかは任意とします。

→
---
```bash
#!/bin/bash
echo "Enter two numbers:"
read num1
read num2
read -p "Choose an arithmetic operation（+, -, *, /):" sign
case "$sign" in
        "+")
                echo $((num1 + num2));;
        "-")
                echo $((num1 - num2));;
        "*")
                echo $((num1 * num2));;
        "/")
                if [ ${num2} = 0 ]; then
                        echo "0 is not valid for the number to divide by."
                else
                        echo $((num1 / num2))
                fi;;
        *)
                echo "undefined";;
esac
```
---


## 4. 繰り返し処理

for 文 または while 文を利用して、1~100までのうち、偶数の数字を表示する処理を書いてください。以下の結果が出力されます。

```bash
2 4 8 ... 100
```

→
---

```bash
#!/bin/bash
i=1
while [ $i -lt 100 ]
do
        if [ $((i % 2)) = 0 ]; then
                echo -n "${i} "

        fi
        i=`expr $i + 1`
done
```
---
