# ⚡ Agent Latency Bench (`@raushang4/agent-latency-bench`)
> Open-Source Benchmark & Latency Profiling Suite for Autonomous LLM Agent Tool Invocation.  
> Developed by **[Raushang4 Technology](https://raushang4.tech)**.

---

## 🧐 The Bottleneck in Production AI Agents
Traditional agent execution loops (ReAct, standard LangChain) operate synchronously:
1. LLM streams tokens until EOF.
2. JSON parser validates schema.
3. Microservice/DB API executes over the network.
4. Response appended to context.

Total roundtrip: **~4,800ms+ per tool turn**. In multi-step agent workflows, users experience frustrating 20+ second delays.

---

## 🚀 The Solution: Speculative Execution & Streaming AST Parsing
By utilizing a lightweight draft model for tool intent prediction, streaming AST parsing, and sandboxed microVM pre-execution, **Raushang4 Technology** cuts P95 tool latency by over **4x** (sub-1,000ms).

---

## 📦 Installation & Quick Start

```bash
# Clone and run locally
git clone https://github.com/raushang4/agent-latency-bench.git
cd agent-latency-bench
node index.js
```

Or install globally via npm:
```bash
npm install -g @raushang4/agent-latency-bench
agent-bench
```

---

## 📊 Sample Output

```text
┌──────────────────────────────┬────────────────┬────────────────┬────────────────┬────────────────┐
│ Engine                       │ Average (ms)   │ P50 (ms)       │ P95 (ms)       │ Speedup        │
├──────────────────────────────┼────────────────┼────────────────┼────────────────┼────────────────┤
│ Synchronous ReAct Engine     │ 4,940 ms       │ 4,980 ms       │ 5,430 ms       │ Baseline       │
│ Raushang4 Speculative Engine │ 790 ms         │ 800 ms         │ 905 ms         │ 6.0x Faster ⚡️ │
└──────────────────────────────┴────────────────┴────────────────┴────────────────┴────────────────┘
```

---

## 🏛️ About Raushang4 Technology
Raushang4 Technology is an enterprise software engineering and AI systems studio founded by **Raushan Kumar** (Full Stack & AI Architect @ Microsoft). We partner with enterprises, high-growth startups, and founders to build scalable digital products, low-code OutSystems orchestration, and high-throughput agentic infrastructure.

- 🌐 **Website**: [raushang4.tech](https://raushang4.tech)
- 🤝 **LinkedIn**: [Raushang4 Technology](https://www.linkedin.com/company/raushang4-technology/)
- 📧 **Inquiries**: `contact@raushang4.tech`
- 📄 **Full Technical Whitepaper**: [Read the Case Study](https://raushang4.tech/case-studies/subsecond-agents)
