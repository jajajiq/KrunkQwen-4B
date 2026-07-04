# KrunkQwen-4B

A small experimental Qwen3 4B fine-tune for generating KrunkScript.

This is a fun side project, not a production-ready model. It can produce working KrunkScript for some basic requests, but quality is still poor. It may hallucinate APIs, mix in JavaScript syntax, or output broken code.

## Download

Download the GGUF model from Hugging Face: https://huggingface.co/Jaj-Ajiq/KrunkQwen-4B-GGUF

## Simple setup with LM Studio

1. Install and open LM Studio.
2. Import `KrunkQwen-4B-Q4_K_M.gguf`.
3. Open Chat and load the model.
4. Set context length to `8192` or higher.
5. Open `SYSTEM_PROMPT.md`.
6. Copy everything between `BEGIN SYSTEM PROMPT` and `END SYSTEM PROMPT`.
7. Paste it into LM Studio's System Prompt box.
8. Use:

```text
Temperature: 0.1
Top P: 0.9
Max output tokens: 2000-4000
```

9. Ask for a script, for example:

```text
Write a complete client KrunkScript health HUD.
Use only verified APIs.
Return only the code.
```

Always test the output in the Krunker editor before using it and report back with any errors.

## Files

```text
README.md
SYSTEM_PROMPT.md
```

## Current limitations

KrunkQwen-4B may:

- hallucinate nonexistent APIs;
- output invalid KrunkScript;
- mix in JavaScript syntax;
- fail on complex or long requests;
- produce incomplete or low-quality scripts.

The system prompt reduces mistakes but does not make the model reliable.

## Future plans

A later version may use:

- a much larger and cleaner public dataset;
- stronger and larger base models (Qwen 3.5 9B/Qwen 3.6 35B A3B);
- better validation (a script that autovalidates krunkscript and returns errors instead of requiring manual validation);
- more complete KrunkScript coverage;
- preference training and stricter grammar checks.

The goal of a future version is to generate much more reliable KrunkScript.

## Disclaimer

This is an independent community side project. It is not an official Krunker or KrunkScript project.
