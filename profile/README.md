# IronShard

**Cloud storage for the agentic age.** An S3-compatible bucket your agents connect to over MCP.

IronShard is governed object storage built for AI agent workloads. Branch production data instantly, read with zero egress by default, scope every agent to exactly what it needs, and keep a cryptographically signed record of everything it does.

[Website](https://www.ironshard.ai) · [Docs](https://www.ironshard.ai/docs) · [Console](https://console.ironshard.ai) · [Pricing](https://www.ironshard.ai/pricing) · [Compare](https://www.ironshard.ai/compare)

## What you get

| | |
|---|---|
| **Instant production branching** | Snapshot production at any moment, at zero copy. Copy-on-write isolation gives each agent its own branch, with rollback to any point in time. |
| **Zero-egress reads** | Read-heavy workloads stay free of egress fees by default. Latency-sensitive workloads can optimize for speed instead, configurable per credential. |
| **Per-agent access control** | Each agent authenticates with its own identity and gets a policy-defined scope, for example `read-only · /datasets/q1/*`. |
| **Signed audit trail** | Every action leaves an immutable, cryptographically signed record in structured JSON that you can search and export. |
| **Multi-cloud by design** | Data is encrypted end to end, erasure-coded into shards, and distributed across the providers and jurisdictions you choose. |

## Quickstart

### Connect an agent over MCP

1. Create an account and a bucket in the [console](https://console.ironshard.ai).
2. Add the MCP endpoint to your client (Claude, Cursor, VS Code) and authenticate with OAuth:

   ```
   https://mcp.ironshard.ai/mcp
   ```

3. Prompt your agent to read, write, branch, and snapshot.

### Use your existing S3 code

Generate S3 credentials in the console and swap one endpoint:

```python
import boto3

s3 = boto3.client(
    "s3",
    endpoint_url="https://s3.ironshard.ai",
)
s3.download_file("my-bucket", "datasets/dataset.parquet", "local.parquet")
```

### Let an autonomous agent try it

No account or OAuth required. The agent provisions its own sandbox bucket:

```
https://agents-mcp.ironshard.ai/mcp
```

See [agent buckets](https://www.ironshard.ai/docs/agent-buckets) for details.

## Works with what you already use

- **Python:** boto3, PyTorch, LangChain
- **Command line:** AWS CLI, rclone, s3fs
- **Pipelines:** Airflow, Prefect, Apache Spark
- **MLOps:** Terraform, DVC, MLflow

## Built for

Model training, fine-tuning, regression testing, RAG pipelines, and any workload where agents need governed access to real data.

## Learn more

- [Branching](https://www.ironshard.ai/branch)
- [Storage for agents](https://www.ironshard.ai/agents)
- [IronShard Log](https://www.ironshard.ai/log)
- [Compliance](https://www.ironshard.ai/compliance)
- [llms.txt](https://www.ironshard.ai/llms.txt) for agents and LLMs

## Get in touch

Start free in the [console](https://console.ironshard.ai), no credit card required, or [book a call](https://calendar.app.google/qEqAwLKZ9jC7SpF89) with the team.
