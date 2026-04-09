# Before/After — Control OS effect
Language: [日本語版はこちら / Japanese version](../../ja/30-adoption/try/before-after-demo-ja.md)

> **Note:** The responses below are illustrative examples, not verbatim AI output.

## Test: "List ALL issues in this code"

This Python code has 6 embedded issues:

```python
import os
def get_user(id):
    query = f"SELECT * FROM users WHERE id = {id}"
    conn = connect(os.environ["DB_URL"])
    result = conn.execute(query)
    data = result.fetchall()
    conn.close()
    return data
```

Issues: ①SQL injection ②SELECT * ③No error handling ④Connection not managed ⑤No type hints ⑥Arg name shadows builtin

---

## Without Control OS

> Here are the main issues with this code:
>
> 1. **SQL Injection vulnerability**: Building the query with an f-string allows malicious input to attack the database. Use parameterized queries.
>
> 2. **No error handling**: No handling for database connection or query execution failures. Add try-except blocks.
>
> 3. **SELECT * usage**: Specify only the columns you need rather than selecting everything.
>
> These changes will make your code more secure and robust.

**Result: Stopped at 3.** Remaining 3 (connection management, type hints, arg name collision) not mentioned.

FM-09 (compression-first): Compressed to "main issues" — representative examples only.
FM-39 (specificity avoidance): Judged remaining 3 as "minor" and omitted.

---

## With Control OS

> Reporting all issues exhaustively:
>
> **[Security]**
> 1. **SQL injection**: `f"SELECT * FROM users WHERE id = {id}"` directly embeds user input. Change to `cursor.execute("SELECT ... WHERE id = ?", (id,))`.
>
> **[Quality]**
> 2. **SELECT ***: Retrieves unnecessary columns. Specify needed columns explicitly.
> 3. **No type hints**: `def get_user(id)` → `def get_user(user_id: int) -> list[dict]`
> 4. **Arg name `id` shadows builtin**: `id` → `user_id`.
>
> **[Robustness]**
> 5. **No error handling**: `connect()` / `execute()` failures are unhandled. Add `try-except-finally`.
> 6. **Connection not managed**: `conn.close()` skipped on exception. Use `with` statement or context manager.
>
> **Out of scope**: Logging, authentication/authorization, performance (index presence) are outside this code's scope and were not checked.

**Result: All 6 detected.** Plus explicit scope boundary to prevent false completion.

Which Control OS rules fired:
- "No-reduction rule" → "ALL" in request means no filtering to representative examples
- "Layer separation" → Reported by security / quality / robustness
- "Scope declaration" → Explicitly stated what was NOT checked


---

→ [Back to README](../README.md)
---
*This document is part of [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS).*
