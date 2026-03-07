# Findings

The experiments suggest that GitHub Copilot does not classify or redact secret values based on their content.

Instead, Copilot appears to rely on **context eligibility**.

Three context modes were observed:

1. Repository review  
   Copilot derived configuration variables from source code without reading `.env`.

2. Repository search with `.gitignore`  
   `.env` was treated as if it did not exist in the repository.

3. Editor or repository access to `.env`  
   Once `.env` entered Copilot’s accessible context, the assistant reproduced the file contents when asked.

## Key Insight

The effective trust boundary is **file accessibility**, not secret awareness.

If a secret-bearing file is visible to the assistant, Copilot will summarize its contents.

## Practical Risk

A common workflow may expose secrets unintentionally:

1. Developer opens `.env`
2. Developer asks Copilot for configuration help
3. Copilot summarizes the file
4. Secrets appear in assistant output
5. Output is copied into Slack, tickets, or screenshots

This pattern is best described as **contextual secret exposure** rather than unauthorized access.
