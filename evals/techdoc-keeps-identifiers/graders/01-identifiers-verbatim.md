---
type: llm
focus: trace
weight: 1
---

反引号标识符逐字保留：最终文本里以下 7 个行内代码连同反引号原样出现：`RetryPolicy`、`max_retries`、`backoff_factor`、`jitter=True`、`retry_on_methods`、`ConnectionError`、`HTTPError`。大小写、下划线、等号、反引号都不能变，也不能换成中文说法（如用「最大重试次数」代替 `max_retries`）。

判法：7 个带反引号的字符串逐个做子串匹配，全部命中才通过。

最终文本：运行结束后 retry-policy.md 的内容。文件没动、改写稿只给在回复里时，以回复里的改写稿为准。
