# 透過深度學習生成MP3音樂

近年在深度學習領域蓬勃發展，透過多變的算法以及深度學習的日新月異衍伸出許多種不同解決問題的方案，更是在「藝術」領域有突破的發展，Open AI在前些日子提出了DALLE2透過文字生成圖片，結合了自然語言(NLP)及Transformer的方法讓使用者只要能輸入文字即能讓AI去生成所對應的圖片，更有人透過AI生成圖片的方式贏得電腦繪圖比賽，都凸顯了AI在藝術領域已經有非常驚人的成績，甚至能贏過人類的成績。
    音樂乃藝術之範疇，將透過深度學習的方式結合現有的技術討論透過量子深度學習的方式與原本的深度學習所生成音樂的比較。
# 問題討論

在探討本次題目前要先討論為何AI生成音樂的難處，現今大眾常聽的串流音樂為壓縮過後的MP3檔，其中必有失真且資料為數位音訊，常見的取樣為44100Hz及22050Hz，拿22050舉例那麼我們投入訓練的資料就是每秒22050個點，一首歌長度少則三分鐘多至十分鐘的皆有，讓深度學習去分析22505個點每秒鐘且要讓其還原同樣的點，無非是一件非常大的工程，也是一件非常難的任務，所以提出了透過量子深度學習(QNN)，投入深度學習訓練，並且討論與經典電腦上的深學習之差別。
本組成員曾經有做過使用LSTM生成音樂，但是不難發現其實深度學習所生成的音樂缺乏「藝術美感」，只是透過LSTM的架構受限於架構的限制，所生成的音樂時常收斂到同一個音階，導致所生成的音樂重複的音階許多，與我們所認知到的「好聽」有偌大的差別，所以本次也參考AI圖片生成的前例嘗試投入NLP的架構來解決此問題。

# 資料處理

挑選出四位不同的古典樂家，莫札特、巴赫、柴可夫斯基、貝多芬，各選取五格不同的樂章，每個樂章隨機挑選並擷取20秒作為訓練資料。

# WHY QML
## 為甚麼要使用QML
在了解QML之後認識到，QML的架構在整體架構上的優化，及透過量子計算的方法是有機會提升準確率，也翻閱過幾篇QML相關的paper發現在影像辨識上QML的準確率相較之下是有提高的，也因此想藏是使用QML在音訊的資料分析上做嘗試

![image](https://user-images.githubusercontent.com/75330475/206336853-6c7f210c-ecd9-46f6-948d-0317cd11b1a2.png)
![image](https://user-images.githubusercontent.com/75330475/206361468-4d8ee5cd-89da-46d7-8824-f6975a2ecff7.png)

# 模型訓練
## 模型架構分三類
### 1.使用AutoEncoder的方式加入LSTM，CNN1D在其中生成MP3音樂。(已完成)(模型調參中) 
- [x] MP3資料整理
- [x] 模型架設
- [x] 調整參數(目前最好模型)
- [x] 音樂輸出
*   [生成音樂連結](https://drive.google.com/drive/folders/185Vhm6fO4SWUI3Z4D_VEUX-vFGxXSJ0a?usp=sharing)，挑選目前最好的模型生成10首音樂
### 2.模型內加入Midi檔再用Attention將其生成MP3檔。(正在進行)
- [x] midi資料整理
- [x] 模型架設
- [ ] 最好的模型
### 3.把AE模型中的Latent Space改用QML生成MP3檔。(量子電路設計中)
- [ ] 量子電路設計中(透過IBMQ跑模擬，並且使用PennLane套件)
- [ ] 架設模型
- [ ] 跑訓練超久:(  
