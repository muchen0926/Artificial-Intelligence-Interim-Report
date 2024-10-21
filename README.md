# Google Colab 部署自己的機器學習項目

## 目錄

1. 介紹
 
2. 準備工作
   
3. 步驟
   
   - 3.1 進入 google driver: https://drive.google.com
     
   - 3.2 右鍵上傳項目所在的文件夾
     
   - 3.3 進入 colab: 點擊左上角 `新建` --> `更多` --> `Colaboratory`
     
   - 3.4 `Edit` --> `Notebook settings` -->

   - 3.5 代碼段裡面輸入
     
   - 3.6 代碼段裡面輸入
     
   - 3.7 代碼段裡面輸入
     
4. 注意事項

## 1. 介紹

Google Colab 提供的是免費 Tesla K80 GPU，可以玩 Keras、Tensorflow、PyTorch 或者 Mxnet 等。Tesla K80 還是一塊比較高性能的 GPU。主要是免費，免費，免費！！！好像這次真的薅資本主義羊毛了，個人試了幾天，感覺還不錯。剛入手的時候稍微有點麻煩，大部分的網上教程都是在 Colab 上手動寫代碼玩玩兒，但是我是自己在本地寫好了一個小的項目，然後相互之間 import 有點麻煩，最後自己摸索總結出了一套最簡單的上傳自己項目，用 Colab 跑出結果的方法。

## 2. 準備工作

- 註冊一個谷歌賬號
- 用自己的谷歌賬號使用 Google Driver
- 自己的項目在本地調試通過，放在一個文件夾裡面（包含數據集，最好是英文名字）

## 3. 步驟

### 3.1 進入 google driver: https://drive.google.com

### 3.2 右鍵上傳項目所在的文件夾

![image](https://github.com/muchen0926/Artificial-Intelligence-Interim-Report/blob/main/3.2.1.png)
![image](https://github.com/muchen0926/Artificial-Intelligence-Interim-Report/blob/main/3.2.2.png)
![image](https://github.com/muchen0926/Artificial-Intelligence-Interim-Report/blob/main/3.2.3.png)

我這裡簡單地上傳了一個名為 `test` 的文件夾，裡面只有一個 `main.py` 的文件，代碼也很簡單，但是可以簡單測試 PyTorch 的使用。
![image](https://github.com/muchen0926/Artificial-Intelligence-Interim-Report/blob/main/3.2.4.png)

### 3.3 進入 colab: 點擊左上角 `新建` --> `更多` --> `Colaboratory`

![image](https://github.com/muchen0926/Artificial-Intelligence-Interim-Report/blob/main/3.3.1.png)
![image](https://github.com/muchen0926/Artificial-Intelligence-Interim-Report/blob/main/3.3.2.png)

### 3.4 `Edit` --> `Notebook settings` -->

![image](https://github.com/muchen0926/Artificial-Intelligence-Interim-Report/blob/main/3.4.png)

這裡我選擇的是 Python3 （根據自己代碼依賴的環境） 和 GPU。如果要用 GPU 這一步必須調整好。每次調整這裡的設置，後面的步驟都要再次進行。所以推薦這裡設置好。

![image](https://github.com/muchen0926/Artificial-Intelligence-Interim-Report/blob/main/3.4.2.png)

### 3.5 代碼段裡面輸入


    from google.colab import drive
    drive.mount('/content/drive/')
   
然後點擊左側的運行圖標，或者 Ctrl + Enter 運行。這時候會出現：

![image](https://github.com/muchen0926/Artificial-Intelligence-Interim-Report/blob/main/3.5.png)

點擊 URL 進入，授權 Google 用戶，然後複製授權碼粘貼到輸入框，Enter。這個時候會顯示掛載成功。

![image](https://github.com/muchen0926/Artificial-Intelligence-Interim-Report/blob/main/3.5.2.png)

這裡可以輸入：

    !ls

![image](https://github.com/muchen0926/Artificial-Intelligence-Interim-Report/blob/main/3.5.3.png)

可以看到此目錄下的文件。

### 3.6 代碼段裡面輸入

    import os
    os.chdir(“drive/My Drive/test”)

最後一個 test 是自己的項目名。這個時候沒有任何提示信息，因為是 Linux 內核，所以按照 Linux 的思想：沒有消息就是最好的消息。說明一切順利。 
這裡可以輸入：

    !ls
   
![image](https://github.com/muchen0926/Artificial-Intelligence-Interim-Report/blob/main/3.6.png)

可以看到我們寫的 main.py 文件。

###　3.7 代碼段裡面輸入

    !python main.py

![image](https://github.com/muchen0926/Artificial-Intelligence-Interim-Report/blob/main/3.7.png)

成功搞定~
  
## 4. 注意事項

1. 雖然是 Linux 內核，但是每次類似於 Linux 的語句之前要多一個 !。比如步驟 3.6 和 3.7。
  
2. 步驟 3.6 第二個語句最後一個路徑名稱根據自己上傳到 Google Driver 的文件夾的名字而定，我上傳的是 test，所以最後一個路徑是 test。

## 5. 實作測試影片
https://youtu.be/Fb83KF6glTQ
