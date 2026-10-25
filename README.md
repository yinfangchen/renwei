# 人味儿（renwei）

中文文本的双向「调味」skill。按场景去 AI 味，或者反过来，把大白话变成正式文体 / 标准 AI 腔。

## 支持的场景

- **对话/聊天回复**（微信、QQ、群聊、评论区）：删客服腔，回多长看对方要拿这条消息去做什么，多热络看关系，对方要用的信息不砍；私聊在关系不明时给两个语气候选；店铺、客服回买家时保留售后礼貌
- **小红书笔记**（朋友圈、微博短帖也走这个包）：emoji 和碎排版保留，均匀分布打破；种草文严禁编造经历
- **正式书面**（邮件、周报、汇报、方案、简历、学术论文、技术文档）：改掉套话和欧化句法，语体不降，邮件改完还是邮件，论文改完还是论文
- **长文案**（公众号、博客、知乎）：删宏大开头和升华结尾；立场要清楚，原文没表态就问作者，不替作者站队
- **短视频口播稿**（抖音、视频号）：按「说出来的文字」改：气口、前三秒钩子、数字念法
- 其他文本走通用模式库

## 反向模式

- **正式化 / 官腔化**（实用）：大白话 → 工作群通知、正式邮件、书面汇报。
- **AI 腔化**（演示 / 整活）：把模式库反着用，制造教科书级 AI 味，拿来做对比教学正合适。

走不走反向，看输入和目标的语体差，不看发到哪。大白话要写成通知，是反向；「太像 AI 了，要发工作群」「改成人话但要正式」还是正向，语体不动，只去 AI 味。


## 安装

### Claude Code

```bash
git clone https://github.com/yinfangchen/renwei.git ~/renwei && ln -s ~/renwei ~/.claude/skills/renwei
```

或者直接把整个目录拷进 `~/.claude/skills/`。新会话里说「帮我去去 AI 味」，或直接 `/renwei`。



## 致谢

思路起点是 [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)。模式库的部分类目参考了这份清单（三段式排比、破折号、宣传腔夸词等），判据和例句按中文语料重新整理。

几个前辈项目各有侧重：

| 项目 | 语言 | 场景支持 | 思路 |
|---|---|---|---|
| [blader/humanizer](https://github.com/blader/humanizer) | 英文 | 无 | 维基百科「Signs of AI writing」的 33 条模式 |
| [op7418/humanizer-zh](https://github.com/op7418/humanizer-zh) | 中文 | 无 | 上者的中文本地化 |
| [MrGeDiao/shuorenhua](https://github.com/MrGeDiao/shuorenhua) | 中文 | 工程/工作沟通场景 | 场景包 + 事实保护 + 评测 |

MIT License
