# IHasMultiTextDictionary
為了因應多語言而需要在Json輸入的檔案。

本質上就是一個`string to string Dictionary`（但是被包在一個`class`裡）。

類似小型的`TextManager`

`Key`是`${某個標籤}_{語言}`，比如說`notify_english`，`notify_chinesetraditional`⋯⋯等等。其他`run time Action`就可以直接用`notify`當標籤，遊戲會試著用當前的語言來在字典裡尋找，如果找不到的話，就會試著找`notify_english`，如果連`notify_english`都沒有的話，就會丟出錯誤。

# 通用標籤
## UnlockMenu_Hint
在Lock Menu上寫的字

## Unlock_Notify
LockMenu被點下去時，但是還沒有達到解鎖條件時，在Notify上顯示的字

## Unlock_Confirm
LockMenu被點下去時，達成解鎖條件的話，確認是否真的要解鎖的字

# SongPack
## Name
章節的名字

## SubTitle
章節的副標（Chapter 1, Chatper +....

## Type
章節的類型（Main Story, Side Story, Collection）

## Year
章節的時間（AD 2000....）

# SongMenu
注：`Name`，`Composer`，`Illustrators`都不需要`MultLangaugeDictionary`，因為他們應該只有一個名字。

# ChartMenu
注：同理，`Charter`也不需要。
