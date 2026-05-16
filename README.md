# buoy-skills

我的自製 Agent Skills 集合，給 Claude Code 等 AI agent 使用。

## Skills

| Skill | 用途 |
|---|---|
| [decode-en](skills/decode-en/) | 拆解英文句子：切分短語、解釋英文邏輯（含功能詞的非字面用法）、給中文對照，幫中文母語學習者真正讀懂組合後的意思 |

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
