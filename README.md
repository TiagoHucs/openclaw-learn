
video fonte:
```
https://www.youtube.com/watch?v=Hy0jRkFrwMc&t=1283s
```

Criar a imagem:
```
docker build -t clawdbot
```

Subir o container:
```
docker run -it -p 18790:18789 --name clawdbot clawdbot
```

Instalar o OpenClaw
```
curl -fsSL https://openclaw.ai/install.sh | bash
```

Escolher a API. Neste caso estou usando a API da OpenRouter

subir gateway
```
openclaw gateway --port 18789
```

acessar outro terminal e executar o TUI:
```
docker exec -it clawdbot bash
openclaw tui
```
Esta opção é para chat no terminal


abrir aplicacao:
```
http://127.0.0.1:18789/#token=<token-fornecido-peela-aplicacao>
```
obs: possivelmente localhost