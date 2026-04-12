### LLM exposed .env (not working, Github automatically blocks exposed API keys)
```
sk-ant-api03- (path:.env OR path:.env.local OR path:.env.development OR path:.env.production OR path:.env.dev OR path:.env.prod OR path:.env.staging OR path:.env.server) -path:.env.example -path:.env.sample -path:.env.template -path:.env.dist -path:.env.test -path:.env.backup -path:example -path:sample -path:template
```

### The "AI Stack" Dork (LLMs & Generation) (Working...)
```
("ELEVENLABS_API_KEY" OR "REPLICATE_API_TOKEN" OR "HF_TOKEN" OR "COHERE_API_KEY" OR "PERPLEXITY_API_KEY" OR "TOGETHER_API_KEY" OR "FIREWORKS_API_KEY" OR "DEEPINFRA_API_KEY" OR "FAL_KEY" OR "STABILITY_API_KEY" OR "GROK_API_KEY") (path:.env OR path:.env.local OR path:.env.dev OR path:.env.prod OR path:.env.development OR path:.env.production OR path:.env.staging) NOT (path:*.example* OR path:*.sample* OR path:*.template*)
```

### The "Infrastructure & Messaging" Dork (Working...)
```
("DISCORD_TOKEN" OR "TELEGRAM_BOT_TOKEN" OR "TWILIO_AUTH_TOKEN" OR "SENDGRID_API_KEY" OR "SUPABASE_SERVICE_ROLE_KEY" OR "PINECONE_API_KEY" OR "LANGSMITH_API_KEY") (path:.env OR path:.env.local OR path:.env.dev OR path:.env.prod) NOT (path:*.example* OR path:*.sample*)
```
