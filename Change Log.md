# V0.1 Build 25 Change log
## 微小更新Catch Note的打擊方式。
之前，Catch Note無法被提早打擊，一定得要在他的打擊節拍後，才有辦法被打擊。現在，它可以被提前0.05秒打擊。

例：若是玩家在0.05秒內「按下」了軌道，會判斷打擊。但是，如果玩家在「0.05秒前就按著軌道」，那麼，在正確拍數的那一幀，會判斷完美打擊。

做出這個決定，是為了讓像Mai Mai風車那樣的譜面，更容易被打擊到。

## Windows換行Unicode無法被正確執行的問題。
修正了這個問題。現在在Windows寫的譜，可以正常在iOS裝置上運行了。

## 新增裝飾性的舞台行動
詳情之後會在譜面格式更新。但是這個更新是相當不關「譜面」本身的事的舞台行動，新進譜師目前還不需要知道這個功能。

## 增加了Demo
我將之前譜師所寫的譜，整理之後增加到了一個Demo章節中。各位如果有時間的話，可以多多玩玩看，感受一下這個遊戲大概是什麼樣的感覺。如果有意見或問題的話，也都歡迎禮貌性地提出喔。

# V0.1 Build 26 Change log
## 一次可測試不同譜面
之前，一次只能測試一面譜，現在可以在TestChart檔案夾裡，加入很多譜面，並且在開發者介面裡選擇要測試哪一個譜面。（譜面格式跟之前一模一樣，只是現在還多了一層新的檔案夾，來讓人選擇要測試哪一個譜面。<br>
如果在Build 25之前已經有寫過譜面了，在TestChart的檔案夾裡，新增一個檔案夾（只要是英文，名稱皆可），然後把之前的檔案（chart.txt，level.json，audio.ogg）丟進新的檔案夾裡。
詳細的使用影片：https://www.youtube.com/watch?v=2OVLGHEycWI

# V0.1 Build 27 Change log
## Catch Note再更新
現在Catch Note可以被提早0.07秒打擊。以及，就算他被「提早打擊」，他的「打擊特效」跟「音效」還是會在「正確的時機」播放出來。

## 打擊線大小更新
稍微讓打擊線變細一點，希望能比較容易判斷音符打擊點。

（順道一提，短音符的「正確打擊點」是「音符的中間」跟「打擊線的中間」切齊時。長音符的正確打擊點則是「長音符的頭」跟「打擊器的中間」切齊時。

## 熱更新嘗試
將所有測試中的譜面整合到了一個測試章節中。之後每個星期會自動更新。

## Parallax Effect
在Night Blossoms曲包內試做了Parallax Effect。

# Dev按鈕
在iOS時，要雙擊才會打開開發者介面。但是開啟之後，只要點一下就能離開。（這是為了避免誤觸）

在Windows上，只要點一次就可以了開啟關閉了（Windows不會誤觸）

# Dev介面
稍微更新了一下開發者介面的畫面。把功能分開顯示了。

# UI更新
稍微更新了UI。

# V0.1 Build 28 Change log
## 測試中的譜面移到Dev Menu之中
之前所有的譜面都在一個測試章節內，很佔容量也很難管理。現在直接全部移到Dev Menu的Test Charts分類裡了。

（現在，寫譜的功能也可以直接套用在測試譜面裡了。意思是，在Charting分類裡的數值會被套進Test Charts裡）

## 增加Offset功能
在設定裡，可以設定延遲了。

## 減少延遲
在iOS跟Android上用了原生音源的插件，應該可以減少很多延遲。

## 長型音符出現時閃爍問題
解決了長型音符出現時，會閃爍的問題。

## 大型瘦身
減少了很多檔案的大小，少了快20%的容量。（測試譜面少了整整70％）

## Parallax
把Parallax的效果做的更好了。其他章節的圖片也都植入了。

## 打擊音改良
Swipe現在是鈴鐺的聲音。


# V0.1 Build 30
## 1. 打擊音效音量改良
鈴鐺聲太大了。

## 2. 改良測試譜面列表介面
照名稱排序，然後直接做到Charting介面裡。

## 3. 改善舞台（玩家體驗）
### 3.1 改良Swipe樣式
要讓玩家更能馬上知道要往哪滑。

### 3.2 改良長音樣式
直接改成普通的格式，把長音的圖讓給連打音用。

#### 3.2.1 改良長音打擊體驗（長音尾應該要發出聲音嗎？）
投票結論是要。所以不用改。

### 3.3 改良連打音樣式
### 3.4.1 決定連打音的功能（一直打vs顯示上限）
決定是顯示上限的那個。

## 3.4 同拍音發光
同上。

## 3.5 判定動畫改良（要比現在明顯）
### 3.5.1 大方向考慮幾何形狀特效
玩家可以通過幾何形狀的複雜度來知道自己打擊的判定。

## 4. 拿掉舞台降畫質的省效能功能（看來不是所有裝置的render pipeline都認同這個效果，那也只能捨棄了）
實際上看起來應該也不需要這個功能就是了。

## 5. 加上鏡頭調整絕對位置的舞台行動
`a chagnecamera abs_position ...`
`a chagnecamera abs_angle ...`

## 6. 加上鏡頭分開單項目（x, y, z）調整絕對位置的舞台行動
`a s_changecamera (x, y, z)`

## 7. 音符跟判定線做出區別
短音符加上了藍色的第二色。

## 8. 修正如果有新下載的資料，並且下載後，再回到Title Screen時，會再提示一次要下載新資料的錯誤。
同上

# V.0.1 Build 31
- 可以隨時調整拍子了！

# V.0.1 Build 32
- View Stage修復
- 尾判
- 移除主畫面，現在進去直接會是歌單選擇畫面
- 修正Easing.Bounce跟Easing.Elastic

# V.0.1 Build 33

## 1. 準備封測
- 增加了一個封測章節，裡面有`Journey's End`，`Umami`，`Melt In Night`，跟`Reflected`
- 更新玩家設定的UI
- 改了暫停畫面。而且暫停結束後會倒數`3, 2, 1`了

## 2. 測試譜面更新
兩個大改變：
1. `TestChart`裡現在除了不同的歌的檔案夾，每個檔案夾裡還可以放不同的譜面。只要是`chart.名字.txt`的檔案都會被認定是譜面，並且被列出來（包括以前的`chart.txt`

比如說，現在可以變成像

```
TestChart - |
            | Journey's End - | level.json
                              | audio.ogg
                              | chart.easy.txt
                              | chart.medium.txt
                              | chart.hard.txt
```

2. 把「製作中的譜面」的下載方式改變了。之前會在進入遊戲前統一下載，現在要去開發者介面裡，並且按下`Reload`按鍵，遊戲就會自動下載那些測試中的譜面到一個叫做`DevSong`的檔案夾（跟`TestChart`同層）。

這是全自動的，請不要動DevSong裡頭的檔案！

```
TestChart (你想要「製作的譜面」擺在這裡)
DevSong（其他人正在製作中的譜面會在這裏。不要動這個檔案夾裡的檔案！）
Save（玩家的存檔）
```
## 3. 其他
- iOS：上滑一次變兩次了

# V.0.1 Build 34

## 0. 重要！
存檔方式改變了！之前的存檔已經報廢了，必須刪除後才行進行遊戲！
iOS：進入Files/我的裝置/Hexa Hysteria/。刪除Save檔案夾
Android：進入 Internal Storage/Android/data/com.WiseyeStudio.HexaHysteria/files。刪除Save檔案夾

或者可以直接將程式刪除重新下載。

## 1. 準備封測
- `Journey's End`去除了不存在的Hard。
- 玩家現在可以從譜面選單調整音量以及音符速度。
- 譜面選單顯示了之前的最佳成績，最佳Combo，譜師⋯⋯等等的資訊
- 進入舞台後，如果曲繪過黑，遊戲會自動計算一層白色的Mask來遮過黑的部分，但是亮色的地方則是保留（總之就是曲繪會變亮）

## 2. 新增譜面格式
- `ChangeCamera`更名為`MoveCamera`。所有功能照舊，只是名字變了。
- 新增了`MoveStage`。作用等同於`MoveCamera`，但是作用在舞台上。

## 3. 一些錯誤修正
- 之前如果使用了`ChangeStage`的行動，然後使用測試譜面迅速調節開始拍的功能，不會顯示正確的結果。現在會顯示正確的結果了！
- 之前如果使用了`/*`跟`*/`，譜面錯誤顯示畫面會顯示錯誤的行數。現在會顯示正確的行數了！
- 解決了短音殘影有時會出現在螢幕正中央的問題。現在他們會顯示在正確的位置上！

# V.0.1 Build 35
總之就是準備好封測。

## UI基本完成
UI骨幹基本上已經完成。下面列出我還想得起來的更新事項：

1. 在選擇歌曲的畫面的左下角，可以快速選擇譜面。
2. 在進入開始畫面時，如果你還沒有設定過，遊戲會請你進行很酷的設定（語言，隱私權⋯⋯等等）。
3. 記憶物品選擇畫面植入完成。
4. 歌曲跟譜面鎖定畫面改良。
5. 開始畫面動畫改良。
6. 舞台上，Combo後面會有一個背景。在全Perfect的時候，會是青藍色，如果打到Great以下，會變成青色，如果斷Combo，則會消失。
7. 可以在譜面選擇畫面快速調整音符速度跟打擊音量。
8. 舞台裡，過暗的曲繪的對比度會降低，亮度會提高，讓讀譜比較不被背景影響。

⋯⋯應該還有其他的，不過我想不太起來了。還有很多bug修正。

基本上就是UI改良，對譜師基本上沒有很大影響。

## 新手教學
加入了新手教學。目前先用了Journey's End當Place Holder，但是之後會是其他的歌。

## 載入速度優化。
我學到了新的異步處理技巧 ////////

# Build V 0.1 Build 38
## 舞台大型更新
### 譜面格式移除
移除了`changecolor text`, `changecolor trial_pattern`, `changecolor note`。

1. text的原因：除非是特殊的故事譜面，否則用不到。
2. trial_pattern的原因：現在trial_pattern的透明度連著`trial`。
3. note：除非是特殊的故事譜面，否則用不到（又不是Mush Dash）

### 譜面格式新增
新增了`a movetrial`，也就是單軌調整。

### 移除Great以及Bad判定
現在的判定區間如下：

判定 | 秒數
------------ | -------------
打擊差 < 0.07秒 | Perfect
0.07秒 < 打擊差 < 0.14秒 | Good
0.14秒 < 打擊差 < 0.2秒 | Miss
0.2秒 < 打擊差 | 如果是提早，無視（不會判定）。<br>如果是晚，則會自動判定Miss

### 音符速度調整
之前是 1 ~ 9.5，從4 ~ 0.45秒，現在是1 ~ 10，從3 ~ 0.3秒。

### 舞台UI更新。
如題。首先，舞台的UI簡化了。然後，黑色變為死區，所有的UI跟著裝置的螢幕比例縮減到黑色區塊內。

現在，真的每個裝置看上去都一樣了。

### 更新打擊方式
舞台總共有兩種狀態：`點擊`以及`開啟`。`short`，`long`，`Compound`偵測的是`點擊`，`Catch`跟`Swipe`則是偵測`開啟`。

舊版的打擊方法：不管玩家手指是否有無離開畫面，只要軌道暗掉後，又亮了起來，那一幀就算`點擊`（即使手指是貼著螢幕滑進軌道也一樣），之後直到暗之前，維持`開啟`狀態。

新版的打擊方反：玩家手指必須要確實離開螢幕後`點擊`軌道，才算`點擊`。但是如果是貼著螢幕滑進軌道，還是會將舞台`開啟`，但是不會觸發`點擊`

## Bug修正
1. 修正了Windows版本無法調整玩家設定的問題。
2. 修正了Windows版本開發者畫面裡顯示的選項有時會跟實際狀況不相符的問題。
3. 修正iOS預設不是擴音的問題。

# V 0.1 Build 39
重點：舞台特效再更新。

## 舞台 - 打擊特效
玩家測試的結果，普遍認為打擊特效過弱。我想要重新整理一次打擊特效。

### 判定的粒子特效
問題點：
1. 粒子特效過小
2. 粒子特效在判定上的差別只有顏色

#### 粒子特效調大
我不想要粒子特效過於干擾遊玩，但是現在這個特效的確是過小了。

我打算將每個粒子的大小調大，並且將數量減少。

2021/07/04/02:31：決定將粒子特調成：大，小，無，並且讓玩家選擇。

2021/07/04/15:19：在調整完粒子特效後，決定還是改完有，無。

#### 顏色調整
現在總共只剩下三個判定：`Perfect`，`Good`，`Miss`。顏色分別是：`青藍`，`淡紅`，`紅`。

新的判定顏色為：`青藍`，`白`，`紅`。

#### 粒子特效與判定
不知道各位有沒有看出來，但是粒子特效的粒子是細小的六角形。

在加大後，我打算將判定改為：`Perfect`對應六角形，`Good`對應正方形，`Miss`對應三角形。

### 長音
問題點：
1. 有些人看不到長音的結尾（不過要記得，測試時，藍光會一直亮著，因此會擋到長音）
2. 有些人感覺不到他們正在打長音

#### 長音的粒子特效
長音的粒子特效，從頭尾各有一個，變成在打擊時一直維持。

#### 錯過的長音消失
錯過的長音，為了避免玩家以為可以在打擊，會做一個小動畫，讓音符消失。

### 滑動音
問題點：
1. 藍綠色盲不友善
2. 箭頭不明顯

#### 改善箭頭指示
我還想不到詳細的改良方法（加大＋某種動畫？）

### Catch音
寬度會調的比現在小一點，跟其他短音做區分。

### 音符其他改良點

#### 同時音提示
現在同時音的確會在旁邊會有黃色的點點，但是感覺還可以改善一些。

#### 音符由小到大
現在音符會從後面由小變大，改成讓玩家可以設置是否要由小變大（如果不要的話，就從頭到尾維持大小）

## 舞台 - 資訊
### 新增進度條
新增歌曲的進度條，而且進度條（跟Combo的背景一樣），會隨著目前的打擊變色。

# V 0.1 Build 40（預定）
目的：打擊手感更新，玩家設定完善。

## 觸控範圍
跟在DC裡說的一樣，人的手指有厚度（人的手指半徑）。問題是，要怎麼偵測這個厚度。

### iOS
可以用內建觸控來獲得正確半徑，不是問題。

### Android（問題所在）
因為每個裝置的生產商都不一樣，標準也都不一樣，內建的觸控獲得的半徑不一定是正確的。

想法是，可以用螢幕的DPI來反推回來觸控的大小。想法是這樣：

人的手指半徑約 0.15cm ~ 0.3cm。我可以拿到螢幕的DPI，再轉換成像素大小。

cm轉換成inch的比例為`0.393700787`。因此：手指半徑cm * 0.393700787 * DPI = 像素半徑。

就算想要用DPI來推估手指的半徑，裝置回傳的DPI也不一定是正確的，所以最後只能做一個猜測，但這也是沒辦法的。

### 玩家自訂觸控範圍
增加觸控範圍有好處，但也意味著可能會誤觸其他軌道，所以變成玩家可以自訂

- 小：半徑 0 cm （原點）
- 中：半徑 0.2 cm
- 大：半徑 0.4 cm

## 滑動
滑動音符的滑動動作偵測變成可自訂（低，中，高）

主要是觀測玩家的手指移動的速度（敏感度越低 = 需求得移動速度越高）

## 音符顏色，判定顏色
主要是為了色盲者而做的功能

我會提醒玩家「我們不建議調顏色，但是如果您有特殊需求，可以在此設定音符跟判定的顏色」

玩家可以自訂全部音符的顏色以及判定的顏色。

## 實驗性加入 Catch-Long 音符
暫時先入catch-long音符，看看反響如何。如果有問題，我會考慮移除。

`n clong 位置 開始拍 結束拍`

## Swipe音符的判定
Build 40之前的判定：

`[+200] Perfect [+140] Good [+70] Perfect [-70] Good [-140] Perfect [-200]`

Build 40之後的判定（暫時）：

`[+200] Perfect [+180] Good [+140] Perfect [-140] Good [-180] Perfect [-200]`

## 玩家自訂音效
如題。

## Windows Dev Song無法進入的錯誤修復
Windows跟Unix路徑分隔不同的問題

## 電腦版快捷鍵
D -> 打開開發者介面
F -> 切換全螢幕
P -> 打開Hexa的資料夾
Q -> 退出遊戲

在舞台內，打開測試模式的時候：
空白鍵 -> 播放，暫停
左右方向鍵 -> 快進，後退

## 測試模式閃退修復
應該是記憶體溢出的問題。現在記憶體應該不會溢出了

## 譜面規則整理
現在的譜面有點超出規則。我這邊會再整理一次明確的規則。

## Test Chart結算閃退
Test Chart結算時會閃退的問題修復。

# V 0.1 Build 41（預計）
## 程式檢修
程式就跟其他機器一樣，不定期檢修的話，就會壞掉。

## Discord機器人檢修
我想要把Discord機器人的功能增加到可以基本自主運行的程度。

## 小Bug修復
### 打擊音設定裡，左右鍵功能一樣的錯誤修復
如題。

### Android打擊音量錯誤？
為什麼明明設成0，但是還是會有音量？我不知道，但是我會修好。
