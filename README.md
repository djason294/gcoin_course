# 設定教學

## 安裝 Python 2.7
 進入 [python 官方網站](https://www.python.org/downloads/release/python-2710/)
 
 點選 `Windows x86 MSI installer` 並安裝

 下載位置採用預設的`C:\Python27` 即可
 

## 安裝 gcoin

下載 gcoin 指令集：[pygcointools](https://pypi.python.org/pypi/gcoin/1.1.44)
。並把檔案移到`C:\Python27\Scripts`

在桌面介面，快捷鍵 `windows+R`

輸入 `cmd` 開啟 cmd 介面，接著輸入以下兩行

>
>cd C:\Python27\Scripts
>
>pip install gcoin-1.1.44-py2-none-any.whl
 
//其實只要輸入 `pip install gcoin` 再按 `tab` 即可
 
## Api教學

進入網站：[request maker](http://requestmaker.com/)

####一般寫法

格式
>http://52.198.247.0:8000/<指令>/<變數>

example
>http://52.198.247.0:8000/base/v1/balance/13zYswW4SV31SynXXM8dwEkyMnu5A2XUmJ

###GET 參數寫法寫法

格式
>http://52.198.247.0:8000/<指令>?<變數>=<數值>&<變數>=<數值>&<變數>=<數值>

example
>http://52.198.247.0:8000/base/v1/license/prepare?color_id=249166&address=13zYswW4SV31SynXXM8dwEkyMnu5A2XUmJ&name=戴睿頡&description=TA

###POST 寫法

格式
>http://52.198.247.0:8000/<指令>/
>
>然後在Request Data填入 : <變數>=<數值>

example
>http://52.198.247.0:8000/base/v1/transaction/send
>
>Request data:
>
>raw_tx=0100000001000000000000000000000000000000000000000000000000


https://www.hurl.it/

>http://52.198.247.0:8000/base/v1/balance/13zYswW4SV31SynXXM8dwEkyMnu5A2XUmJ
>
>http://52.198.247.0:8000/base/v1/license/prepare
>
>



