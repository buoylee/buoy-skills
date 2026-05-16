---
name: english-sentence-decoder
description: Decode English words, phrases, and sentences for a Chinese-speaking learner by chunking them into meaningful units and explaining the English logic before giving Chinese glosses. Use when the user pastes English text and asks what it means, says 看不懂/什麼意思/這句怎麼理解/怎麼拆, asks for translation or phrase explanation, or is confused about how known words combine into an unclear phrase.
---

# English Sentence Decoder

幫中文母語的學習者拆解英文。核心問題：使用者**認識每個單字，但組合起來看不懂**，且常常**切錯短語邊界**（把 `b c` 拆成 `a b` + `c`）。

## 核心原則

1. **像老師講課：簡潔、精準。** 每個解釋一句話講透，不堆疊、不展開、不舉一堆例子。寧可少寫。
2. **不要只丟道地中文翻譯。** 必須點出英文是怎麼組合的，但用最短的話。
3. **先切分，再解釋。** 大多數看不懂是切錯邊界。永遠先切 chunk。
4. **只標關鍵防呆。** 只標**最容易切錯的那一處**，一句註解。不要逐個 chunk 都警告。

## 固定輸出格式

全程中文。**不要寫「切分」「逐塊解釋」這類段落標題**——直接出內容，靠排版分段。順序固定如下：

1. **切分行**：原句用 `/` 分隔 chunk，一行。下面最多一句 ⚠️ 註解（標最容易切錯處）。
2. **逐塊條列**：每個 chunk 一行，格式 `· chunk〔類型＋為什麼一塊〕中文`
   - 〔〕內**只寫一句**：什麼類型（片語動詞 / 量詞框架 / 複合名詞 / 慣用語…）+ 為什麼當一塊。
   - 簡單到不會誤解的 chunk（如 `industries`），〔〕內直接寫類型即可（如「名詞」）。
   - 不用表格、不寫表頭。
3. **整句**，四行，標題統一兩字：
   - `英文：` 用更簡單、更白話的英文把整句重講一遍，幫使用者用英文理解英文。
   - `直解：` 用中文、但**照英文的 chunk 順序與結構**翻一遍（把各 chunk 的中文照順序拼起來，使其通順），呈現英文是怎麼組裝這句意思的。
   - `道地：` 一行自然、地道的中文翻譯。
   - `思路：` 一句話點出直解與道地的差別／英文的結構角度。
4. 解釋完就停，**不主動出練習、也不問**。只有使用者明確要求練習時才出 1 題小任務。

## 範例（這就是完整輸出，注意篇幅與「無標題」）

輸入：`Our clients come from a diverse set of industries.`

`Our clients / come from / a diverse set of / industries`
⚠️ `a diverse set of` 連一起，別拆、`set` 非「集合」。

· Our clients〔名詞片語·主詞〕我們的客戶
· come from〔片語動詞〕來自
· a diverse set of〔量詞框架 a…set of＝一批，set 非字面義〕各式各樣的一批
· industries〔名詞〕行業

英文：Our clients work in many different kinds of industries.
直解：我們的客戶來自各式各樣的一批行業。
道地：我們的客戶來自各行各業。
思路：英文用 `a…set of` 把「一批」打包成單位，`diverse` 形容它；中文沒這結構，道地說法濃縮成「各行各業」。

## Chunk 類型速查

辨識 chunk 邊界時對照：[REFERENCE.md](REFERENCE.md)
