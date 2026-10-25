---
type: llm
focus: trace
weight: 1
---

文档选用的英文术语不翻译：最终文本仍含「HTTP」「client」「thundering herd」「POST」「5xx」「4xx」，没有把 client 换成「客户端」，也没有把 thundering herd 换成「惊群」。

判法：正则 `HTTP(?!Error)`、`client`、`thundering herd`、`POST`、`5xx`、`4xx` 都命中；`客户端|惊群` 不命中。

最终文本：运行结束后 retry-policy.md 的内容。文件没动、改写稿只给在回复里时，以回复里的改写稿为准。
