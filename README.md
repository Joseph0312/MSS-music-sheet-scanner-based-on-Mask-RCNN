# MSS-music-sheet-scanner-based-on-Mask-RCNN
本作品為樂譜數位典藏的程式，開發平台為 Google-Colab，將樂譜圖片傳入程式，以正交投影從圖片切割出小節，對切割完的小節圖片用 Mask R-CNN 做物件分析，再同樣以正交投影法，以找出音符音高與符號間的關聯性，最終還原成便於保存、編輯的 LilyPond語法格式樂譜，且可以用.midi 檔播放。

![image](https://github.com/Joseph0312/MSS-music-sheet-scanner-based-on-Mask-RCNN/blob/master/Picture%20for%20readme/note_detect_result.png)

<H1>進行步驟</H1>
<hr />
(1)輸入樂譜圖檔: 使用者輸入一份欲辨識的圖片檔(JPG、PNG)，為了提高辨識的正確性，該圖片的五線譜須為水平線段。
