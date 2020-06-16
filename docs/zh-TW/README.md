# Style Guide Chinese, Traditional (zh-TW)

*若需分享此文件，可使用 [http://bit.ly/MozTW-L10nStyles](http://bit.ly/MozTW-L10nStyles)*

這是由 MozTW 維護的 Mozilla 正體中文（台灣）在地化樣式與翻譯規範文件。除非另有規範，否則本文件所定義的格式會使用在所有由 MozTW 維護的 Mozilla 產品與網頁內容，在您開始進行貢獻前請先詳讀。若對本格式有疑問或意見，請寄信到 [moztw-general@googlegroups.com](https://groups.google.com/forum/#!forum/moztw-general) 並[副本通知 l10n owner](https://moztw.org/about/)，謝謝。

This is the style guide of Mozilla’s Traditional Chinese (Taiwan) [zh-TW] locale. Except noted elsewhere, this style shall apply to all MozTW Projects and Mozilla projects/contents maintained by MozTW. Please read carefully before starting contributing. Should you have any question or concern, please raise discussion in [moztw-general@googlegroups.com](https://groups.google.com/forum/#!forum/moztw-general) and [CC l10n owner](https://moztw.org/about/), thanks.

<!-- toc -->

-----

## 原則

1. 應採意譯，不必逐句、逐字翻譯，可適度依照在地文化或語境調整語句或作刪減，但仍需準確表達原文含意，避免因翻譯而造成的模糊性、誤導並確保一致性。
2. 機器翻譯僅可做為參考，不應直接使用。翻譯內容亦需符合台灣常用語法。

    |   | 原文 | 譯文 | 說明 |
    | - | - | - | - |
    | ✓ | Internet | 網際網路 |   |
    | ⍻ | Internet | 網路 | 「網際網路」的慣用簡略說法，部份情況下可接受 |
    | ✗ | Internet | 互聯網 | 非台灣常用語法 |

3. 若有不清楚的字詞，可到 Telegram 群組、mailing list 詢問，或暫時擱置、標記為 fuzzy。
4. 可適度參考其他廠商的翻譯樣式/內容，但仍應以本樣式的規範為準。
    * [Microsoft](https://www.microsoft.com/en-us/language/StyleGuides?rtc=1)
    * [Wordpress](https://translate.wordpress.com/glossaries-and-style-guides/chinese-traditional-style-guide/)
    * [Facebook](https://www.facebook.com/translations/guide/)
5. 翻譯時，應注意是否有 Localization Note 或 Comment 等註解。當中會有針對原文的描述或說明。

## 語氣、用字遣詞

1. 語氣應與原文相同。若語境較為輕鬆幽默，可使用中文的類似說法，但仍應保持正式、專業、淺顯易懂。
    * 例如：若文案內容用詞出自足球競賽用語，則可適當調整為棒球、籃球競賽等較習慣的用詞。
2. 性別：除非原文明確表示性別，否則應使用中性語氣。
    * `you` 的譯法：原則上使用敬詞`您`，若原文沒有那麼嚴肅可視情況使用`你`，但產品內仍應使用`您`。
3. 可適度使用成語，但仍應力求淺顯易懂。
4. 應注意用詞的一致性，若不知道該怎麼翻可至 [Transvision](https://transvision.mozfr.org/) 尋找 Translation Memory。
5. 可依字串出現的位置或功能區塊適當調整技術用語。
    * 例如：「設定」頁面中的翻譯用語，應比開發工具的翻譯來得簡單。

## 特殊情況

1. 若遇到長原文、有換行符號的原文或 C-Format 的原文內容，可適度依照譯文增減行數，但翻譯完應特別測試譯文是否會被截斷或影響畫面。
2. 中文沒有複數型，遇到原文可能有複數的情況，只翻譯複數部分；但仍需考慮這一句有沒有以不同數量顯示的可能。
    * Java DTD/properties 格式

      這是比較傳統的翻譯字串格式，翻譯字串會以 `.dtd` 與 `.properties` 格式儲存。一個字串僅能對應到一組訊息，遇同一個訊息可能會有單複數形時，會以分號隔開並列於同一個字串中。

      |   | 原文 | 譯文 | 說明 |
      | - | - | - | - |
      | ✓ | One item;#1 items | #1 個項目 | 執行時，會將 #1 取代為阿拉伯數字；只須翻譯複數句（分號起的後半）。 |
      | ✗ | One item;#1 items | 一個項目;#1 個項目 | 單數形的中文數字與複數形的阿拉伯數字不一致 |
      | ✗ | One item;#1 items | 1 個項目;#1 個項目 | 多餘的單數形 |

    * FTL (Fluent) 格式

      這是比較新穎的翻譯字串格式，可在字串中保留單複數、陰陽性、不同平台的翻譯對應關係。中文環境下預設使用 `[other]` 規則，其餘的翻譯則視原文與上下文決定是否加入。

        * 原文

                security-visits-number =
                  { $visits ->
                     [0] No
                     [one] Yes, once
                    *[other] Yes, { $visits } times
                  }

        * 譯文

                security-visits-number =
                  { $visits ->
                     [0] 沒有
                     [one] 有，1 次
                    *[other] 有，{ $visits } 次
                  }

3. 注意中英文的 `and`、`or` 意義可能相反，尤其是反向表列的時候。
4. 注意 Gettext 的跳脫符號 `\`，例如 `\"%s\"` 應翻譯為`「%s」`，但若能確定該參數會顯示的內容語言非中文時則保留使用跳脫符號與引號。
5. 若語句中包含變數，應注意語句順序。

|   | 原文 | 譯文 | 說明 |
| - | - | - | - |
| ✓ | Powered by `%1$s` | 由 `%1$s` 提供 | `%1$s` 應配合中文語法，置於 `由…提供` 的中間 |
| ✓ | Powered by `%1$s` | Powered by `%1$s` | 選擇不翻譯，保持原文 |

## 字元、數字、標點符號

1. 中文字元：應使用一致的正體字（繁體字）。異體字可接受但在單一字串或段落中不應混用。不得使用簡體字。
2. 英文字元：應使用半形英文字母、數字與標點符號。
3. 數字：可視上下文自由決定使用阿拉伯或中文數字，但同一個字串、段落中應保持一致
    * 依據來源文字決定是否加入千分號
    * 除非刻意表達需使用中文大寫數字的情況（例如表示支票金額），否則都使用小寫
    * 若遇下列情況應優先使用阿拉伯數字。
        * 程式執行或網頁載入時，由程式自動插入數值的情況
        * 有版面設計因素，必需使用阿拉伯數字的情況
        * 使用中文數字造成翻譯文字冗長的情況（反之亦然）

            |   | 原文 | 譯文 | 說明 |
            | - | - | - | - |
            | ✓ | 1000 member | 1000 個會員 | 從原文，但`一千個會員`也可以 |
            | ✓ | 4 bllion users | 40 億使用者 | 應配合中文閱讀習慣，重新對數字分組 |
            | ✗ | 300 million users | 300 百萬使用者 | 應譯為 3 億 |
            | ✓ | […]2,000 people representing 90 countries and 114 languages gathered[…] | 有來自 90 個國家，操 114 種不同語言的 2,000 人聚集在一起 | 保持整段文字的一致性 |
            | ✓ | Yes, once | 有，1 次 | 超過一次的時候數字會被對應的阿拉伯數字取代，所以不譯成「有，一次」 |

4. 中文標點符號：使用中華民國教育部出版之[《重訂標點符號手冊》修訂版](http://language.moe.gov.tw/001/Upload/FILES/SITE_CONTENT/M0001/HAU/haushou.htm)當中的標點符號。
    * `.` 作為句點應譯為 `。`；`'`、`"`、`‘’`、`“”`作為引號，應翻譯為`「」`或`『』`，先單引號後雙引號。
    * 刪節號應譯為 `…` (U+2026)，可使用一組就好。遇到原文使用三個點 `...` 時可報 Bug 修正。
    * 於應用程式中，無論句子語言為何，句尾冒號使用半形冒號 `:`，而非全形冒號 `：`。
5. 全形字、標點符號與半形英數、符號字元間需使用半形空格隔開，但與全形符號間則免。
6. 數字與單位間是否補空格應依循原文，但若單位為中文則應一律補空格。

|   | 原文 | 譯文 | 說明 |
| - | - | - | - |
| ✓ | Firefox and the Firefox logos are trademarks of the Mozilla Foundation. | Firefox 字樣與 Firefox 標誌為 Mozilla 基金會之註冊商標。 |   |
| ✓ | `By proceeding, you agree to the <a data-l10n-name="terms">Terms of Service</a> and <a data-l10n-name="privacy">Privacy Notice</a>.` | `繼續使用，代表您同意我們的<a data-l10n-name="terms">使用條款</a>及<a data-l10n-name="privacy">隱私權公告</a>。` | 鏈結文字與前後皆為中文字，不補空白 |
| ✓ | Firefox has canceled the request for your protection. | 為了安全性考量，Firefox 已經取消連線要求。 | `Firefox` 前面連接全形逗號，不補空白；後面連接中文字，需補空白 |
| ✓ | 15 files, 2130KB | 15 個檔案，2130KB |  |

## 特殊標籤、快速鍵

1. 部分字串由於介面設計因素，可能會以比較簡略的方式顯示，並加入文字標籤以方便無障礙系統閱讀。此類標籤會以 `aria-label` 的名稱存在，翻譯時應該注意原字串的功能。

    | 字串名稱 | 原文 | 譯文 | 說明 |
    | - | - | - | - |
    | settings.label | ⚙️ | ⚙️ | 若使用的文字或 emoji 不會造成混淆，就可直接使用原文 |
    | settings.aria-label | Settings | 設定 | 應根據原文翻譯，螢幕閱讀器讀取到此按鈕時方可說出「設定」而非「齒輪」 |

2. 譯文中的 accesskey / commandkey 指的是選單或對話框重要按鈕功能的快速鍵。若未與系統中其它功能發生衝突，原則上保持與英文版相同。若發生衝突應報 bug 由上游修正。

    | 字串名稱 | 原文 | 譯文 | 說明 |
    | - | - | - | - |
    | settings.menuitem | Settings | 設定 |  |
    | settings.macitem | Preferences | 偏好設定 | Mac OS 上的慣用譯法 |
    | settings.accesskey | S | S | 程式執行時，選單項目會顯示為「設定 (<u>S</u>)」 |
    | settings.commandkey | K | K | 代表程式執行時，按下 `Ctrl`/`Cmd + K` 即可開啟此功能 |
    | settings.tooltip | Tweak application settings | 調整應用程式設定 | 游標停留於該 UI 元素時會顯示的說明文字內容 |

## 譯乎，不譯乎

1. 商標、品牌：原則上不應翻譯
    1. Mozilla 商標/品牌：不翻譯。
        * 注意：雖然 Mozilla 在台灣設立分公司，也有註冊商標，但在介面翻譯上仍應保持英文原名。

            |   | 原文 | 譯文 | 說明 |
            | - | - | - | - |
            | ✓ | Mozilla Firefox | Mozilla Firefox |   |
            | ✗ | Mozilla Firefox | 謀智火狐 |   |

    2. Mozilla 產品功能：看前後文意而定，但商標/品牌本身仍不翻譯
        * `Firefox Accounts` 可翻譯成 `Firefox 帳號`
        * `Private Browsing` 可翻譯成 `隱私瀏覽`
        * `Sync` 可翻譯成 `同步`、`同步功能`
    3. 其他公司、品牌：原則上不翻譯，但看情況而定。
        * 例如 `Microsoft` 可視情況在 SUMO 文件內翻譯為 `微軟`，但不將 `Microsoft Edge` 翻譯為 `微軟 Edge`。
    4. 其他產品的功能名稱：若該功能在正體中文版產品當中有翻譯，應無視原文，直接使用該產品內的翻譯名稱，並加註引號。

        |   | 原文 | 譯文 | 說明 |
        | - | - | - | - |
        | ✓ | File Explorer | 檔案總管 | Windows 內翻譯名稱 |
        | ✓ | Finder | Finder | Mac OS 內翻譯名稱 |
2. 變數
    * 例如：Firefox 會依照 release channel 的不同，在產品內以 Firefox、Aurora、Nightly 取代 `&brandShortName;` 變數
3. 表示預留位置的文字（Placeholders）：可翻可不翻。

    |   | 譯文 | 說明 |
    | - | - | - |
    | ✓ | Firefox 會將您的使用者設定檔存放於：`C:\Users\<your Windows login username>\AppData\Roaming\Mozilla\Firefox\Profiles\` | 兩者皆可 |
    | ✓ | Firefox 會將您的使用者設定檔存放於：`C:\Users\<Windows 使用者名稱>\AppData\Roaming\Mozilla\Firefox\Profiles\` | 兩者皆可 |

4. 縮寫

原則上，中文不使用縮寫，但使用許多來自外文的縮寫。以下規則依譯者主觀判斷：

* 大眾所熟知的縮寫，可以直接使用原文，亦可以翻譯。
* 不常見的縮寫，則應翻譯為中文，無須再補充縮寫全文。
* 若使用縮寫，應視為一個字，不能換行；若翻譯，應注意是否會造成語句冗長或超出版面。

    |   | 原文 | 譯文 | 說明 |
    | - | - | - | - |
    | ✓ | HTML | HTML | 保留原文不翻譯 |
    | ✗ | HTML | 超文本標記語言 | 顯得冗長，且未幫助使用者了解 |
    | ✓ | SEPA/BACS | SEPA/BACS（歐洲/英國區域內匯款） | 保留原文，適度加入說明 |
    | ✗ | SEPA/BACS | SEPA/BACS | 不翻譯，但使用者也較難理解 |
    | ✗ | SEPA/BACS | 單一歐元支付區/英國銀行自動清帳服務（Single Euro Payments Area/Bankers' Automated Clearing Services, SEPA/BACS） | 太冗長 |

* 若縮寫使用複數，譯文應改為單數

    |   | 原文 | 譯文 | 說明 |
    | - | - | - | - |
    | ✓ | Multiple PDFs | 多個 PDF 檔案 | 使用單數形 |
    | ✗ | Multiple PDFs | 多個 PDFs 檔案 | 使用複數形 |

## 測試 / QA

1. 注意以動名詞開頭的句子在中文語境下的型態。
    * 例：`Installing` 可能翻譯為 `安裝中` 或 `安裝`。
2. 注意英文句子中，子句順序與中文不同的情況。
3. 注意一字多義的情況，若語句怪怪的或不通順可發信討論。
4. 注意字串長度，看看譯文是否會被截斷。若無法直接透過 l10n 調整則可報 Bug 修正。
5. 遇到樣式、排版或是因為中文缺少好用的 Web Font 而造成的不美觀，可請 l10n owner 聯絡專案負責人修正。
6. 注意日期時間格式是否符合使用習慣。
7. 可調整 ordered arguments 在句中的順序。

    |   | 原文 | 譯文 | 範例 | 說明 |
    | - | - | - | - | - |
    | ✓ | `Downloading %1$d of %2$d` | `正在下載 %2$d 個檔案當中的第 %1$d 個` | 正在下載 5 個檔案當中的第 1 個 | `%1$d` 表示在這一句當中第一次出現的 `%d`，格式為十進位整數 |
    | ✓ | `Downloading %1$d of %2$d` | `正在下載 %1$d／%2$d 個檔案` | 正在下載 1／5 個檔案 |   |
    | ✓ | `%s on %s %s` | `%2$s %3$s 上的 %1$s` | Apple iPhone 7 上的 Firefox | `%s` 格式為字串 |

8. 翻譯之後可重新閱讀幾遍，看看譯文通不通順，再行修飾。
    * 同一句裡面不要重複出現相同的主詞或所有格，某些數量與量詞亦可省略。
    * 注意同一個介面文字段落可能由多個不同的字串連結組成，應注意在多個字串間重複出現的可能。

        |   | 原文 | 譯文 | 說明 |
        | - | - | - | - |
        | ✓ | If you reset your master password, all of your stored web and e-mail passwords, form data, personal certificates, and private keys will be lost. | 若您重設主控密碼，將失去所有網頁與電子郵件密碼、表單資料、個人憑證以及私鑰。 | 減少贅字、調整語句順序 |
        | ✗ | If you reset your master password, all of your stored web and e-mail passwords, form data, personal certificates, and private keys will be lost. | 若您重設**您的**主控密碼，**您**所有**儲存的**網頁與電子郵件密碼、表單資料、個人憑證以及私鑰都將會消失。 |  |

9. 應注意中文排版規則、畫面/版面美觀與易讀性。
    * 避頭點
        * 不應放在句尾的標點符號：`([{£¥‘“‵〈《「『【〔〝︵︷︹︻︽︿﹁﹃﹙﹛﹝（｛`
        * 不應放在句首的標點符號：`!),.:;?]}¢·–—’”•‥…‧′╴、。〉》」』】〕〞︰︱︳︴︶︸︺︼︾﹀﹂﹄﹏﹐﹑﹒﹔﹕﹖﹗﹚﹜﹞！），．：；？］｜｝､`
        * （以上取自 Microsoft Office Word version 1912 build 12325.20288 內建 Normal.dotx 檔案設定）
    * 單字不成行、單行不成頁
    * 並列的文字區塊行數應接近
    * 字型、行高、行距大小
    * 若因網頁 RWD 設計，或程式限制以致文字調整困難，可適度無視此規則

10. 若原文當中使用的資訊僅適用特定國家/市場，應從上下文推斷並註明。

|   | 原文 | 譯文 | 說明 |
| - | - | - | - |
| ✓ | The collective liability under these terms will not exceed $500 (five hundred dollars). | 各種損害賠償責任的總合須不逾**美金**五百元。 | 原文並未說明貨幣單位，依上下文推斷為美金。 |
| ✓ | The Mozilla Foundation Tax ID is 20-0097189. | Mozilla 基金會的**美國**稅籍編號是 20-0097189。 | 特別說明是美國的稅籍編號。 |

## 單位與格式

### 日期

1. 翻譯時，若原文並未特別要求，可自由使用合理的日期表示方式

    |   | 格式 | 範例 | 說明 |
    | - | - | - | - |
    | ✓ | yyyy/mm/dd | 2020/01/01 |  |
    | ✓ | m 月 d 日 | 1 月 7 日 |  |
    | ✓ | m 月 d 日 | 二月廿一日 |  |
    | ✓ | yyyy 年 m 月 d 日www | 2020 年 1 月 15 日星期三 |  |
    | ⍻ | m/d | 1/15 | 較不建議使用 |

2. 若月份或日期未達 2 位數，可以選擇補零或不補零，但不應混用

    |   | 譯文 | 說明 |
    | - | - | - |
    | ✓ |  1 月  1 日 | 建議使用 |
    | ✓ | 01 月 01 日 |  |
    | ✗ |  1 月 01 日 | 補零規則不一致 |
    | ✗ | 01 月  1 日 | 補零規則不一致 |

3. 標準的月份翻譯格式：

    | 原文 | 譯文（長） | 譯文（短） |
    | - | - | - |
    | Janurary, Jan | 一月 | 1 月 |
    | February, Feb | 二月 | 2 月 |
    | March, Mar | 三月 | 3 月 |
    | April, Apr | 四月 | 4 月 |
    | May, May | 五月 | 5 月 |
    | June, Jun | 六月 | 6 月 |
    | July, Jul | 七月 | 7 月 |
    | August, Aug | 八月 | 8 月 |
    | September, Sep | 九月 | 9 月 |
    | October, Oce | 十月 | 10 月 |
    | November, Nov | 十一月 | 11 月 |
    | December, Dec | 十二月 | 12 月 |

4. 標準的星期翻譯格式：

    | 原文（長） | 原文（短） | 譯文（長） | 譯文（短） |
    | - | - | - | - |
    | Monday | Mon, Mo | 星期一 | 週一, 一 |
    | Tuesday | Tue, Tu | 星期二 | 週二, 二 |
    | Wednesday | Wed, We | 星期三 | 週三, 三 |
    | Thursday | Thu, Th | 星期四 | 週四, 四 |
    | Friday | Fri, Fr | 星期五 | 週五, 五 |
    | Saturday | Sat, Sa | 星期六 | 週六, 六 |
    | Sunday | Sun, Su | 星期日 | 週日, 日 |

僅一字的短格式適用於顯示空間不足時；應優先考慮使用兩個字的「週一」格式。

### 時間

1. 翻譯時，若原文並未特別要求，可自由使用合理的時間表示方式。
2. 使用 12 小時制或 24 小時制均可。採用 12 小時制時，上下午標示應標註於時間之前。
3. 無需轉換時區，但若原文提供時區資訊，應置於時間後方。

        |   | 譯文 | 說明 |
        | - | - | - |
        | ✓ | 下午 03:15:30 | 建議使用 |
        | ✓ | 15:15:30 | 建議使用 |
        | ✓ | 下午 03:15（UTC+8） |   |
        | ✓ | 下午 03:15（台北時間） |   |
        | ✗ | 03:15 下午 | 上/下午應置於時間之前 |

### 曆法

1. 顯示萬年曆時，應使用格里曆（公曆），每週起始於星期一。
2. 若提供次要曆法顯示，則顯示農曆。

### 數字表現

| 符號用途 | 符號 | 範例 |
| - | - | - |
| 小數點 | `.` | 3.14159 |
| 千分位符號 | `,` | 1,234 |
| 百分號 | `%` | 99.95% |

以上全部使用半形符號。

### 貨幣

1. 使用新台幣（ISO 4217 代碼 TWD、符號為 NT$ 或 NTD、單位：圓/元）表示貨幣金額。
2. 若原文使用其他貨幣，無須特別轉換或加註新台幣金額。
3. 金額出現於貨幣前或後均可，但應注意慣用語法。
4. 貨幣符號與數字間不加空格。

    |   | 譯文 | 說明 |
    | - | - | - |
    | ✓ | 日幣 10,000 圓 |  |
    | ✓ | 123.45 新加坡元 |  |
    | ✓ | €30 | 不加空格 |
    | ✗ | $100 美元 | 符號與單位重複出現 |

### 單位

1. 使用公制（國際單位制）單位。
2. 表示數位資料大小時，除 `Byte` 翻譯為 `位元組` 外，其餘單位如 KB、MB、GB、TB 不翻譯。

### 地址

使用中式或西式表示法皆可。

中式表示法

>     10058 台灣台北市中正區八德路一段 94 號 3 樓 摩茲工寮 狐耳摩莎收

西式表示法

>     To: Foxmosa
>     Mozilla Community Space Taipei
>     3rd Fl., No. 94, Sec. 1, Ba-de Rd.
>     Zhongzheng District, Taipei City 10058
>     Taiwan

### 電話號碼

使用中式或西式表示法皆可。

國內表示法

| 類型 | 號碼 | 說明 |
| - | - | - |
| 市內電話 | (%a) %b-%c | %a = 區碼（2-4 位數）, %b = 局碼（1-4 位數）, %c = 用戶碼（4 位數） |
| 行動電話 | %a-%b | %a |

國際表示法

| 類型 | 號碼 | 說明 |
| - | - | - |
| 國際電話 | +###-############ |  |

## 各專案特殊規定

### SUMO

1. 文章的 slug（網址後面的 seo 文章 id）不須翻譯，直接複製英文版即可。
2. 若不小心弄出了 slug 錯誤的文件，請聯絡 L10n 團隊編輯將錯誤的文件砍除，並修正連結。
3. 語意正確度、不漏譯、標點符號正確為先，文章的連貫性與通順度次之。不要有沒必要的空格或是零碎的句子。
4. 未完成翻譯前若需先送出手上的文件，請在送出審核前描述編修內容時勾選`This edit does not make this article up to date. The English differences should not change on the next edit.`，下次進行翻譯時將不會自動取回最新的原文。
5. 文件中若提及某軟體或產品內的功能，應依照該軟體內的文字翻譯。
6. `Warning:` 譯為 `警告：`、`Note:` 譯為 `註：`、`Tip:` 譯為 `秘訣：`

### MDN

1. 貼上內容時，請盡量避免直接貼上 HTML 樣式，可切換成原始碼模式來檢查。
2. 其餘同 SUMO。

### MozLinks

1. 開始翻譯時請在標題時間前面加上`[翻譯中]`，文章翻譯完成後改成`[已翻譯]`。翻譯完成後 Mail 至 [mozlinks-zh-editor@googlegroups.com](https://groups.google.com/forum/#!forum/mozlinks-zh-editor) 通知編輯已完成某篇文章翻譯。
2. 將翻譯內容寫在轉貼原文下方的「中譯：（請在下方翻譯）」區塊；翻譯區塊下的原文、授權等內容應放在翻譯內容的最後，翻譯者不應做任何更改。
3. 編輯內容如遇連結或其他語法請參考 Markdown 語法編輯。
    * 若需要將 `MozLinks` 加上超連結至 `http://mozlinks.moztw.org/` ，則翻譯內容寫法應為 `[MozLinks](http://mozlinks.moztw.org/)`
    * 若需要將 `MozLinks` 套用標題二的樣式，則翻譯內容寫法應為 `##MozLinks`
    * 若需要建立 `MozLinks` 清單項目，則翻譯內容寫法應為 `- MozLinks` 或 `* MozLinks`
4. 文章翻譯者應在 `φ [  ] 翻譯 - [   ] 編輯` 當中，前者的 `[ ] 翻譯` 方框改成自己的名字；編輯的方框則是留給校閱文章的審核者使用。

## 參考資料

* [教育部成語典](http://dict.idioms.moe.edu.tw/cydic/index.htm)
* [教育部重編國語辭典](http://dict.revised.moe.edu.tw/cbdic/)
* [教育部異體字字典](https://dict.variants.moe.edu.tw/variants/rbt/home.do)
* [建置 Windows PC 適用的傳統型應用程式](https://docs.microsoft.com/zh-tw/windows/apps/desktop/)
* [Apple Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines/)
* [Android Android Design Guidelines](https://developer.android.com/design)
* [W3C 中文排版需求](https://www.w3.org/TR/clreq/)
