# Generic Lock Menu

## string InfoText;
// 在畫面上直接提示的字串

## Func<bool> UnlockCondition
// 解鎖的條件

## Action OnAttemptUnlockFailed
// 在玩家試著解鎖，但是沒有能達成解鎖目標時發生的事

## Action OnAttemptUnlock
// 在玩家有能力解鎖時，確認是否真的要解鎖時發生的事

## Action OnUnlockSuccessful
// 在玩家確認要解鎖時發生的事
// 會被系統自動用在適合的地方

# IHasMultiTextDictionary
為了因應多語言而需要在Json輸入的檔案。

本質上就是一個`string to string Dictionary`（但是被包在一個`class`裡）。

`Key`是`${某個標籤}_{語言}`，比如說`notify_english`，`notify_chinesetraditional`⋯⋯等等。其他`run time Action`就可以直接用`notify`當標籤，遊戲會試著用當前的語言來在字典裡尋找，如果找不到的話，就會試著找`notify_english`，如果連`notify_english`都沒有的話，就會丟出錯誤。


# Serializable Action
兩個需要輸入的東西：`Name`跟`arguments`。

- `Name`：用來判斷這到底是什麼`Action`
- `arguments`：一個Dictionary，`key`為`string`，`value`也為`string`。實際內容會因為每一個不同的`Action`而不同。

# Actions List

## write file
從`Addressable`裡，將檔案寫入玩家的檔案中。

Name：`write file`

arguments：
1. string - `input path`：在Addressable裡完整的路徑。
2. string - `output path`：在`Application.persistentpath`裡要寫入的路徑。（寫入的路徑：`$"{Application.persistentpath}/{output path}"`

注意：`input`的檔案必須是`.bytes`結尾。

如果output path上已經有檔案了，就不會再寫入檔案。

## write player data
寫進`player data`裡。

Name：`write player data`

arguments：
1. string - `key`：就是`key`
2. string - `value`：想寫入的值。

## notify notfiy

發出`NotifyMenu.Instance.Notify`

arguments：
1. string - `text_key`：要顯示的字串的`key`。這個`key`指的是在呼叫這個`Action`的`Load Data`裡，作為`IHasMultiTextDictionary`裡的`key`
2. string - 要在按下`okay`時發生的事（todo: 要做嗎？）

## notify confirm

發出`NotifyMenu.Instance.Confirm`

arguments：
1. string -

# Serializable Condition
會回傳`boolean`。跟`Serializable Action`一樣，需要`Name`跟`arguments`

## Player Data Has key
回傳`Player Data`裡是否有`key`

Name：`player data has key`

arguments：
1. string - `key`：`key`的值

## Play Data Key Value
如果`Player Data`裡有`key`，回傳`key`之`value`是否等於輸入的值。

如果`Player Data`裡根本沒有`key`，那就回傳`false`。

name: `player data key value`

arguments：
1. string - `key`：`key`的值
2. string - `value`：`key`之`value`的值

## Save File Has Key
查找`path`上的存檔，回傳`key`是否在存檔裡

如果`path`不存在，則回傳`false`

arguments：
1. string - `path` - 查看`$"{Application.persistentDataPath}/{path}"`

## Path Exists
查找`path`存不存在。

arguments：
1. string - `path` - 查看`$"{Application.persistentDataPath}/{path}"`存不存在。

# SongPack的事件

## OnSongPackEnter
`List of Serializable Action`

在玩家進入曲包時發生。

## OnUnlockingHiddenBackground
`List of Serializable Action`

在玩家切換成隱藏背景時發生。

## OnUnlockingHiddenBackgroundFail
`List of Serializable Action`

在玩家按下「切換隱藏背景按鈕」時，但是卻沒有達到解鎖條件時發生。通常會用notify來告知解鎖條件。

## HiddenBackgroundCondition
`List of Serializable Condition`

解鎖`Hidden Background`的條件。

## UnlockCondition
解鎖的條件（要怎麼處理IAP？）


# 歌曲


# 記憶物品的事件

## OnMemoryItemUnlock
在「這個」記憶物品被解鎖時發生。

## OnAllMemoryItemUnlock
在這個章節裡所有的記憶物品被解鎖時發生。


# ChartMenu

## OnPlayingComplete
在遊玩完譜面後發生。

## OnRankingComplete
在遊玩完譜面並且獲得評等C以上後發生。

## OnRankingBComplete
在遊玩完譜面並且獲得評等B以上後發生。

## OnRankingAComplete
在遊玩完譜面並且獲得評等A以上後發生。

## OnRankingSComplete
在遊玩完譜面並且獲得評等S以上後發生。

## OnRankingSSComplete
在遊玩完譜面並且獲得評等SS以上後發生。

## UnlockCondition
解鎖的條件

## OnUnlock
在解鎖時發生

"OnUnlockingHiddenBackground": [
    {
        "Name": "write file",
        "arguments": {
            "output path": "test/audio.ogg",
            "input path": "SongPack/000-Before Journey/SongPackInfo/secret/audio.bytes"
        }
    },
    {
        "Name": "write file",
        "arguments": {
            "output path": "test/test.txt",
            "input path": "SongPack/000-Before Journey/SongPackInfo/secret/chart.txt"
        }
    },
    {
        "Name": "write file",
        "arguments": {
            "output path": "test/pdf.pdf",
            "input path": "SongPack/000-Before Journey/SongPackInfo/secret/pdf.bytes"
        }
    }
]
