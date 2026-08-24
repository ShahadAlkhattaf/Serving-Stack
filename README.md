# AIDC W2D2 – Wrap the Model

**Model:** `Qwen/Qwen2.5-0.5B-Instruct`  
**Runtime:** CPU

## Step 1 – Pin, Install, and Run

### Installed Versions

```text
Python 3.12.10
torch 2.5.1+cpu
transformers 4.46.3
openai 1.54.5
```

### Health Check

```bash
curl http://localhost:8000/health
```

```json
{"status":"ok","model":"Qwen/Qwen2.5-0.5B-Instruct"}
```

## Step 2 – GET /v1/models

```bash
curl http://localhost:8000/v1/models
```

```json
{
  "object": "list",
  "data": [
    {
      "id": "Qwen/Qwen2.5-0.5B-Instruct",
      "object": "model",
      "created": 0,
      "owned_by": "aidc"
    }
  ]
}
```

## Step 3 – POST /v1/chat/completions

```text
id      : chatcmpl-f98071f78b4e4da48672a4f4ca0bf0fa
object  : chat.completion
created : 1787577400
model   : Qwen/Qwen2.5-0.5B-Instruct
choices : {@{index=0; message=; finish_reason=stop}}
usage   : @{prompt_tokens=35; completion_tokens=3; total_tokens=38}
```

## Step 4 – OpenAI Client

```bash
python client_test.py
```

```text
reply: Three primary colors are red, blue, and yellow.
finish_reason: stop
usage: CompletionUsage(completion_tokens=12, prompt_tokens=24, total_tokens=36, completion_tokens_details=None, prompt_tokens_details=None)
```

## Verify – Green Check

```bash
python verify.py
```

```text
model: Qwen/Qwen2.5-0.5B-Instruct
completion content: 'Hello!'
usage: {'prompt_tokens': 35, 'completion_tokens': 3, 'total_tokens': 38}
streaming: not implemented (optional this week)
GREEN CHECK: PASS
```

![Green Check](images/green-check.png)

## Result

**GREEN CHECK: PASS**
