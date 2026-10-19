### Hi, I'm Dheeraj 👋

AI engineer in the Washington, DC area. I build LLM agents and RAG systems for real users, and I measure whether they actually work.

**Research: [Think Only When Unsure](https://github.com/dhegadde/think-only-when-unsure)**
When should a model stop and reason? I trained a small LoRA decision head on Gemma 4 that answers in one pass when it is confident and hands the question to the model's thinking mode only when it is unsure. On 10 held-out decision tasks (1,900 questions), routing this way matched always-thinking accuracy (80.7 ± 1.1% vs. 80.8%, 3 seeds) at about half the tokens (259 vs. 521 per question). Predictions were written down before each run, including the ones that turned out wrong. The whole study cost about $10 of rented GPU time.

**Research: [Small Model Repair](https://github.com/dhegadde/small-model-repair)** *(work in progress)*
Can a tiny trained add-on repair a language model compressed to about 2 bits? I trained a 64 MB LoRA "fix" by distilling from the near-original model and loaded it in llama.cpp on Unsloth's public 1.5 GB file of Qwen3-4B-Instruct. Across 3 seeds it improved the model on all five benchmarks, most on code (HumanEval+ 61.0 to 70.9, C++ 53.4 to 66.2), and the model finished its code about 97% of the time instead of 85%. It recovers only about a third of what compression loses, and the README separates what's confirmed from what's only likely.

**What I've built**
- **Production voice AI (xLead):** as the technical subject matter expert at an AI voice startup, I built a RAG voice assistant on the Claude API with FastAPI services that handled live calls for a paying client, booked real appointments through Google Calendar, and onboarded 15+ businesses through a Stripe Connect OAuth flow. *(Code is private.)*
- **[Agent Eval Loop](https://github.com/dhegadde/agent-eval-loop):** a three-agent pipeline with a seeded benchmark, an LLM judge that caught all three planted hallucinations with no false positives, prompt optimization with rollback, and a human approval gate. The results log keeps the run where a 0.856 dev score fell to 0.422 on held-out data.
- **[SecondBrain](https://github.com/dhegadde/secondbrain):** a private AI assistant for iPhone that runs a quantized LLM fully on the phone (llama.cpp, Qwen2.5 GGUF), with document scanning, local semantic search, agent pipelines and system actions.
- **[Sleeper MCP](https://github.com/dhegadde/sleeper-mcp):** an MCP server that gives Claude 22 tools over my fantasy football leagues, backed by LightGBM quantile models; on two held-out seasons it matched Sleeper's own projections with calibrated ranges.
- **Model serving:** a 27B model on vLLM under a hard cost cap, and quantization experiments with llama.cpp.

**Tools:** Python · FastAPI · TypeScript · React · Next.js · Swift / SwiftUI · PyTorch · Hugging Face Transformers / PEFT · vLLM · llama.cpp · MCP · Claude, OpenAI, and Gemini APIs · GitHub Actions

📫 [LinkedIn](https://www.linkedin.com/in/dheeraj-gadde-5a6087185/) · dhegadde@gmail.com
