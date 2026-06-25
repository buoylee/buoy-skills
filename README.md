# buoy-skills

我的自製 Agent Skills 集合，給 Claude Code 等 AI agent 使用。

## Skills

| Skill | 用途 |
|---|---|
| [decode-en](skills/decode-en/) | 拆解英文句子：切分短語、解釋英文邏輯（含功能詞的非字面用法）、給中文對照，幫中文母語學習者真正讀懂組合後的意思 |
| [senior-code-review](skills/senior-code-review/) | 互聯網大廠資深工程師級別的代碼審查：性能優先、邊界清晰、經驗老到、嚴守規範，按嚴重度輸出分級清單，每條附 file:line、後果與最小可行修復（分層、可灰度，不推倒重來） |
| [production-grade-solutions](skills/production-grade-solutions/) | 給出真正經過考驗的方案，而非「能跑就好」：點名當今業界主流解、驗證方案在規模下真的成立（反「生產級劇場」）、對偏離主流的做法先問限制再據理力爭（正確性 bug 直接做進碼裡，不靜默照單全收）|

## 安裝

用 [`npx skills`](https://github.com/vercel-labs/skills) 安裝到本機 agent：

```bash
# 列出這個 repo 裡的 skill
npx skills add buoylee/buoy-skills --list

# 安裝指定 skill
npx skills add buoylee/buoy-skills --skill decode-en
```

或手動：把 `skills/<名稱>/` 複製或符號連結到 `~/.claude/skills/<名稱>`。

## 新增 skill

在 `skills/` 下開一個新資料夾，放入 `SKILL.md`（含 YAML frontmatter），push 即可。
