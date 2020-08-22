# MSS-music-sheet-scanner-based-on-Mask-RCNN
本作品為樂譜數位典藏的程式，開發平台為 Google-Colab，將樂譜圖片傳入程式，以正交投影從圖片切割出小節，對切割完的小節圖片用 Mask R-CNN 做物件分析，再同樣以正交投影法，以找出音符音高與符號間的關聯性，最終還原成便於保存、編輯的 LilyPond語法格式樂譜，且可以用.midi 檔播放。

![image](https://github.com/Joseph0312/MSS-music-sheet-scanner-based-on-Mask-RCNN/blob/master/Picture%20for%20readme/note_detect_result.png)

<H1>進行步驟</H1>
<H2>(1)輸入樂譜圖檔</H2>
使用者輸入一份欲辨識的圖片檔(JPG、PNG)，為了提高辨識的正確性，該圖片的五線譜須為水平線段。

<H2>(2)切割段落</H2>
首先將輸入的圖片二值化，並使用正交投影法，將二值化後的數值投影到 Y 軸加總，如圖(二)；數值較大的範圍即為五線的所在區域(座標)，取得兩個相鄰段落的中點座標，切割出各個段落。

<H2>(3)切割小節</H2>
只保留段落圖片中，位於五線內的資訊，其餘刪除，如圖(三 b)所示。並將該圖做正交投影至 X 軸，而小節線所在的 X 座標位置會有最大值，以最大值所在之 X 座標切割，即可切出各個小節，如圖(三 c)所示。
