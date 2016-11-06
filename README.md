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


>
>http://52.198.247.0:8000/base/v1/balance/13zYswW4SV31SynXXM8dwEkyMnu5A2XUmJ
>
>http://52.198.247.0:8000/base/v1/license/249168
>
>http://52.198.247.0:8000/base/v1/license/prepare
>
>color_id
>
>address
>
>name	
>
>description=TA

http://52.198.247.0:8000/base/v1/mint/prepare


'01000000010000000000000000000000000000000000000000000000000000000000000000ffffffff8a4730440220277270bb9193d43b955d1e0517c8881e371e8acd7959be197d86227a6feb8afb022065c29b8cc7dade3249f686fa0d1aade302d7e6111dd722b855d1b50a8834c3e7014104f498744ea4b5602ff25115c7932d7ca980240448cc40f0468c63a05d586dfd487739254bc56fc94c96bb6cfccd7fa7a99815549d4a064a07071e319818b2a7b5ffffffff010088526a740000001976a91420d29270852940705c6bb43b40c19fbfe2f0b73288ac50cd03000000000001000000'


http://52.198.247.0:8000/base/v1/transaction/send


