# make-knowledge-cards2

将粘贴的文章或本地 Markdown/TXT 整理为通常 5～8 张 Markdown 知识卡片。每张包含标题、核心知识、简明解释，以及原文例子或带答案的自测题。合并重复信息，一张只讲一个重点，不编造原文信息；信息不足时不凑数量。

## 使用方法

这是供 AI 助手读取的指令包，不需要项目脚本。可让助手读取 `skills/make-knowledge-cards2/SKILL.md` 后执行；或将整个 `skills/make-knowledge-cards2` 目录复制到 Codex 用户 Skill 目录（通常为 `~/.codex/skills/`），重新加载后调用：

```text
请使用 $make-knowledge-cards2，把下面的文章整理成知识卡片：
（粘贴正文）
```

本地文件：

```text
请使用 $make-knowledge-cards2，读取 ./article.md 并生成知识卡片。
```

默认在对话输出。需要文件时追加“保存到 ./cards.md”。暂不支持网页抓取、PDF、Anki 和图形界面。

## 输入输出示例

输入：

```text
请整理为知识卡片：
检索练习是先不看材料尝试回忆，再对照材料检查。它能帮助发现记忆空缺。
例如读完一段后合上书，写出要点，再翻书核对。
```

输出：

```markdown
共 1 张知识卡片。原文只有一个独立知识点，因此不凑足 5 张。

### 卡片 1：检索练习
**核心知识**：检索练习是先回忆、再对照材料检查的方法。
**简明解释**：先不看材料尝试回忆，再核对，可以帮助发现记忆空缺。
**例子**：读完一段后合上书，写出要点，再翻书核对。
```

## 开发验证

由官方 `init_skill.py` 初始化；仅包含 `SKILL.md` 与 `agents/openai.yaml`，无额外脚本。手工行为测试见 [tests/behavior-tests.md](tests/behavior-tests.md)。官方 `quick_validate.py` 检查结构，不代替行为测试；Windows 中文文件请使用 Python `-X utf8`。

旧版 `skills/make-knowledge-cards` 和已有打包文件保留原样，不是新版发布包。本次未初始化 Git 或上传 GitHub。尚未指定开源许可证，正式发布前请维护者选择许可证。
