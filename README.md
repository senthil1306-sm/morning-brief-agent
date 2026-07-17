
# ☀️ Morning Brief AI Agent — AWS Serverless

> 🏆 Built for AWS Weekend "Always-On Agent Challenge"

An **autonomous AI-powered agent** that wakes up every morning at 6:00 AM, generates a personalized morning briefing using Amazon Bedrock Nova Lite, saves it to S3, and emails it to you — **fully serverless, zero manual interaction.**

---

## 🏗️ Architecture

```mermaid
graph LR
    A[⏰ EventBridge Scheduler] -->|6:00 AM Daily| B[⚡ AWS Lambda Python 3.13]
    B -->|Prompt| C[🤖 Amazon Bedrock - Nova Lite]
    C -->|Generated Brief| B
    B -->|Save| D[📦 Amazon S3]
    B -->|Send Email| E[📧 Amazon SES]
    B -->|Logs| F[📊 CloudWatch]
