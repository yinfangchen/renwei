# 人味（renwei）

中文文本的双向「调味」skill：按场景去 AI 味，或者反过来，把大白话变成正式文体 / 标准 AI 腔。

## 为什么再做一个 humanizer

这几个前辈项目各有侧重：

| 项目 | 语言 | 场景支持 | 思路 |
|---|---|---|---|
| [blader/humanizer](https://github.com/blader/humanizer) | 英文 | 无 | 维基百科「Signs of AI writing」的 33 条模式 |
| [op7418/humanizer-zh](https://github.com/op7418/humanizer-zh) | 中文 | 无 | 上者的中文本地化 |
| [MrGeDiao/shuorenhua](https://github.com/MrGeDiao/shuorenhua) | 中文 | 工程/工作沟通场景 | 场景包 + 事实保护 + 评测 |

内容创作场景一直没人覆盖，而这恰恰是 AI 痕迹最「场景相对」的地方：

- emoji 分点在文档里是 AI 味，在小红书里删光了反而假
- 排比在百科条目里是套路，在口播稿里是修辞
- 「解锁」「拉满」在正式文案里违和，在短视频里是平台通用语

所以 renwei 不用一套规则打天下：先判场景，再按该场景自己的「人味标准」改写。每个场景包带一张**极性表**，写明通用规则在这个场景里哪些反转、哪些放宽、哪些收紧。

## 支持的场景

- **对话/聊天回复**（微信、群聊、评论区）：删客服腔，长度向对方看齐；私聊给两个语气候选，让你按关系挑
- **长文案**（公众号、博客、知乎）：删宏大开头和升华结尾，立场要敢站队
- **短视频口播稿**（抖音、视频号）：按「说出来的文字」改——气口、前三秒钩子、数字念法
- **小红书笔记**：emoji 和碎排版保留，均匀分布打破；种草文严禁编造经历
- 其他文本走通用模式库（32 条中文原生 AI 痕迹 + 防误伤清单）

场景判不准时，skill 会给出可点击的场景选项（Claude Code 里走 AskUserQuestion 组件），点一下就走对应场景包。

## 反向模式

- **正式化 / 官腔化**（实用）：大白话 → 工作群通知、正式邮件、书面汇报。承诺刻度一格不松：「今晚发」永远不会被改成「近期发送」。
- **AI 腔化**（演示 / 整活）：把模式库反着用，制造教科书级 AI 味，拿来做对比教学正合适。

## 事实铁律

两个方向共用一条底线：数字、日期、价格原样保留且保留修饰关系；人名、引语不改字；承诺、条件不漂移；原文没有的事实一个不补。唯一例外是口播稿允许数字念法口语化（不损关键精度）。

## 安装

### Claude Code

```bash
git clone https://github.com/darknesschen1997/renwei.git ~/renwei && ln -s ~/renwei ~/.claude/skills/renwei
```

或者直接把整个目录拷进 `~/.claude/skills/`。新会话里说「帮我去去 AI 味」，或直接 `/renwei`。

### 其他 agent

SKILL.md 是纯 Markdown，没有依赖。把仓库路径给任何能读文件的 agent，让它先读 SKILL.md 再干活即可。

## 项目结构

```
renwei/
├── SKILL.md                 # 主文件：流程、场景判定、事实铁律、审核
├── references/
│   ├── patterns.md          # 通用模式库：32 条中文原生 AI 痕迹 + 防误伤与人味保护清单
│   ├── scene-chat.md        # 场景包：对话/聊天回复
│   ├── scene-longform.md    # 场景包：长文案
│   ├── scene-video.md       # 场景包：短视频口播稿
│   ├── scene-xhs.md         # 场景包：小红书笔记
│   └── reverse.md           # 反向模式：正式化/官腔化 + AI 腔化
└── evals/evals.json         # 测试用例
```

## 致谢

思路起点是上表三个项目，以及 [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)。模式库为中文语料原生整理，不是翻译。

MIT License
