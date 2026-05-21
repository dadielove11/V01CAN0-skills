# V01CAN0-skills

我在 Claude Code 里折腾的 Skills 合集，放这里供人参考或直接用。

Skills 这玩意是 Claude Code 的插件机制，写一个 SKILL.md 文件，放进 `~/.claude/skills/你的技能名/` 目录，Claude Code 就多了一项专属能力，对话里直接 `/技能名` 触发。

## 安装方式

把你想要的 skill 文件夹整个复制到 `~/.claude/skills/` 目录下，重启 Claude Code 即可。

```bash
# 以 khazix-reader 为例
cp -r khazix-reader ~/.claude/skills/
```

---

## Skills 列表

### khazix-reader — 卡兹克公众号阅读器

在 Claude Code 里直接查阅「数字生命卡兹克」微信公众号的文章，不用开手机，不用开浏览器。

我是卡兹克的重度读者，又是重度 Claude Code 用户。每次想回头找他的某篇文章，都得掏手机翻公众号。后来想了想，都在 Claude Code 里待着了，能不能顺手把这事也解决掉？于是折腾了这个。

**能干什么**

说专辑名，秒出文章列表，共 8 个专辑 91 篇，全程不需要开浏览器。

说关键词，本地模糊搜索，标题里有这个词就给你列出来。

选一篇，自动加载全文，读过一次之后写入本地缓存，下次 0 秒出结果。

说「刷新索引」，重新爬一遍所有专辑页面，同步卡兹克最新文章。

**前置条件**

需要安装 Playwright MCP，用于加载文章全文（本地有缓存的话不需要）。

```bash
claude mcp add playwright npx @playwright/mcp@latest
```

**用法举例**

在 Claude Code 里直接说，

- 「看看 Claude Code攻略 有哪些文章」
- 「搜一下 MCP 相关的文章」
- 「刷新索引」
- 粘贴一个 mp.weixin.qq.com 的链接

**文件说明**

```
khazix-reader/
├── SKILL.md      # Skill 主文件，Claude Code 读这个
└── index.yaml    # 8 个专辑 91 篇文章的本地索引
```

---

> 永远对世界保持好奇。
