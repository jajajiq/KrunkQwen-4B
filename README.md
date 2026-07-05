# KrunkQwen-4B

A small experimental Qwen-3 4B fine-tune for generating KrunkScript locally on edge devices. Can be run on as little as 3 GB VRAM. 

A larger and better-validated version is planned. KrunkQwen-4B can produce working KrunkScript for some basic requests and has learned many of the language's syntax and API patterns. However, its small size, limited training coverage and lack of runtime validation mean it may hallucinate APIs, mix in JavaScript syntax, confuse client and server code, or choose the wrong system for a task. For example, a request for a 2D enemy system may incorrectly use `GAME.AI.spawn`, which is intended for 3D AI. The final training loss was approximately 0.4, but this is only a training metric and does not guarantee correct output. Always test generated scripts in the Krunker Editor and ensure the script works as intended. A potential use case for this model can be teaching krunkscript instead of generating it.

## Download

Download the GGUF model from Hugging Face: https://huggingface.co/Jaj-Ajiq/KrunkQwen-4B-GGUF

## Simple setup with LM Studio

1. Install and open LM Studio.
2. Go to Model Search and download `KrunkQwen-4B-Q4_K_M.gguf` (search for KrunkQwen-4B-GGUF).
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
