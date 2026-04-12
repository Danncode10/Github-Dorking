# GitHub Dorking for Security Researchers

> [!CAUTION]
> **FOR EDUCATIONAL AND ETHICAL SECURITY RESEARCH PURPOSES ONLY.**
> This repository is intended to help developers and security researchers identify accidentally exposed secrets and improve their security posture. Unauthorized access to computer systems is illegal.

---

## Friendly Reminders & Security Tips
*   **Never commit secrets:** Use environment variables and keep your `.env` files out of version control.
*   **Use .gitignore:** Always ensure `.env`, `node_modules`, and other sensitive files are listed in your `.gitignore`.
*   **Scan your code:** Use tools like gitleaks or trufflehog to detect secrets before they are pushed.
*   **Rotate leaked keys:** If you accidentally expose a key, revoke it immediately and generate a new one. Even if you "delete" the commit, it may still exist in Git history.
*   **GitHub Secret Scanning:** Enable GitHub's built-in secret scanning to get notified when sensitive data is detected.

---

### The "AI Stack" Dork (LLMs & Generation) (Working...)
```
("ELEVENLABS_API_KEY" OR "REPLICATE_API_TOKEN" OR "HF_TOKEN" OR "COHERE_API_KEY" OR "PERPLEXITY_API_KEY" OR "TOGETHER_API_KEY" OR "FIREWORKS_API_KEY" OR "DEEPINFRA_API_KEY" OR "FAL_KEY" OR "STABILITY_API_KEY" OR "GROK_API_KEY") (path:.env OR path:.env.local OR path:.env.dev OR path:.env.prod OR path:.env.development OR path:.env.production OR path:.env.staging) NOT (path:*.example* OR path:*.sample* OR path:*.template*)
```

### The "Infrastructure & Messaging" Dork (Working...)
```
("DISCORD_TOKEN" OR "TELEGRAM_BOT_TOKEN" OR "TWILIO_AUTH_TOKEN" OR "SENDGRID_API_KEY" OR "SUPABASE_SERVICE_ROLE_KEY" OR "PINECONE_API_KEY" OR "LANGSMITH_API_KEY") (path:.env OR path:.env.local OR path:.env.dev OR path:.env.prod) NOT (path:*.example* OR path:*.sample*)
```

### LLM exposed .env (not working, Github automatically blocks exposed API keys)
```
sk-ant-api03- (path:.env OR path:.env.local OR path:.env.development OR path:.env.production OR path:.env.dev OR path:.env.prod OR path:.env.staging OR path:.env.server) -path:.env.example -path:.env.sample -path:.env.template -path:.env.dist -path:.env.test -path:.env.backup -path:example -path:sample -path:template
```

---

## How to Protect Your Repo
1. **Revoke and Rotate:** Use GitHub's [Secret Scanning](https://docs.github.com/en/code-security/secret-scanning/about-secret-scanning) features.
2. **Environment Isolation:** Use different keys for development and production.
3. **Education:** Share this repo with your team to help them understand how easy it is to leak data!

---
*Created for the developer community to stay safe.*
