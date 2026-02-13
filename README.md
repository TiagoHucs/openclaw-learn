
video fonte:
```
https://www.youtube.com/watch?v=Hy0jRkFrwMc&t=1283s
```

Criar a imagem:
```
docker build -t openclaw-img .
```

Subir o container:
```
docker run -it -p 18790:18789 --name openclaw-container openclaw-img
```

Instalar o OpenClaw
```
curl -fsSL https://openclaw.ai/install.sh | bash
```

Escolher a API. Neste caso estou usando a API da OpenRouter

Estou usando o modelo openrouter/z-ai/glm-4.5-air:free

Configure skills:
yes


subir gateway
```
openclaw gateway --port 18789
```

acessar outro terminal e executar o TUI:
```
docker exec -it openclaw-container bash
openclaw tui
```
Esta opção é para chat no terminal


abrir aplicacao:
```
http://127.0.0.1:18789/#token=<token-fornecido-peela-aplicacao>
```
obs: possivelmente localhost
