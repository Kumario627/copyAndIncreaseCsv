# これは何？
入力csvファイルを全行コピーして、新たなcsvファイルにコピーした入力csvファイルを任意の行数を出力するスクリプトです。  
入力csvファイルの行数より出力する行数が多い場合、入力csvファイルの最終行を出力した次の行は入力csvファイルの先頭行から出力を開始します。  

仕様上入力ファイルよりも少ない行数を出力すると、新たなcsvファイルには指定した行数までの入力csvファイルのデータ行が出力されます。  
一応そう言う使い方もできるという補足です。

# 使用方法
引数を4つ指定できます。  
各引数は以下の通りです。

|  引数  |  概要  | 必須/任意  |  デフォルト値  |
| ---- | ---- | ---- | ---- |
|  1  |  入力csvファイル  |  必須  |  -  |
|  2  |  出力したい行数 ※1  |  任意  |  100  |
|  3  |  出力したいファイル名  |  任意  |  ./output.csv  |
|  4  |  ヘッダーを含むか  |  任意  |  False  |

必須なのは入力csvファイル（第一引数のみ）です。  
※1: 出力したい行数はヘッダーを含まない純粋なデータ行です。（ヘッダーがあれば出力結果は+1行されます）

> **Note**.   
> 第４引数はpythonの`bool()`でキャストされます。  
> キャストされればなんでも良いですが、分かりやすいので下記を推奨します。
> - True: 1
> - False: 0

## 必要なライブラリ
依存関係があるライブラリは下記の３つです。
- csv
- sys
- chardet

installが必要なライブラリは恐らく`chardet`のみのはずです。

## 使用例
```
$ python3 copyAndIncreaseCsv.py ./input.csv 100000 ./result.csv 0
```
pythonは各自の環境で適宜読み替えてください。  
