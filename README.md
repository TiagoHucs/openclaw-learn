
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


abrir aplicacao será necessario ajustar o arquivo openclaw.json na pasta:

<usuario>/.openclaw

para abrir no editor:
```
vim openclaw.json
```
i para inserir , navegar até gateway> bin> loopback
trocar por: "Lan"
esc para sair do modo insert e depois
:wq


 também precisa adicionar a seguinte instrução  "controlUi": { "dangerouslyAllowHostHeaderOriginFallback": true}," se não dara erro ao executar o gateway nas novas versoes.

em vez de usarmos o 18789 vamos usar a porta 18790, pois foi a que configuramos para expor no docker.

```
http://127.0.0.1:18790/#token=<token-fornecido-peela-aplicacao>
```

o dashboard aparecerá mas desconectado. 
neste caso vamos dar permissao ao dispositivo com o comando:

```
openclaw devices list
```

aparecerá uma lista de dispositivos , vamos pegar o ID do dispositivo e enviar o comando:

```
openclaw devices approve "<id do device>"
```



