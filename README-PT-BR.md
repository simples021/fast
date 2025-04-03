<p align="center">
  <a href="https://github.com/gozargah/marzban" target="_blank" rel="noopener noreferrer">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://github.com/Gozargah/Marzban-docs/raw/master/screenshots/logo-dark.png">
      <img width="160" height="160" src="https://github.com/Gozargah/Marzban-docs/raw/master/screenshots/logo-light.png">
    </picture>
  </a>
</p>

<h1 align="center">Marzban</h1>

<p align="center">
    Solução Unificada de Resistência à Censura GUI Alimentada por <a href="https://github.com/XTLS/Xray-core">Xray</a>
</p>

<br/>
<p align="center">
    <a href="#">
        <img src="https://img.shields.io/github/actions/workflow/status/gozargah/marzban/build.yml?style=flat-square" />
    </a>
    <a href="https://hub.docker.com/r/gozargah/marzban" target="_blank">
        <img src="https://img.shields.io/docker/pulls/gozargah/marzban?style=flat-square&logo=docker" />
    </a>
    <a href="#">
        <img src="https://img.shields.io/github/license/gozargah/marzban?style=flat-square" />
    </a>
    <a href="https://t.me/gozargah_marzban" target="_blank">
        <img src="https://img.shields.io/badge/telegram-group-blue?style=flat-square&logo=telegram" />
    </a>
    <a href="#">
        <img src="https://img.shields.io/badge/twitter-commiunity-blue?style=flat-square&logo=twitter" />
    </a>
    <a href="#">
        <img src="https://img.shields.io/github/stars/gozargah/marzban?style=social" />
    </a>
</p>

<p align="center">
 <a href="./README.md">
 Inglês
 </a>
 /
 <a href="./README-fa.md">
 فارسی
 </a>
  /
  <a href="./README-zh-cn.md">
 简体中文
 </a>
   /
  <a href="./README-ru.md">
 Русский
 </a>
</p>

<p align="center">
  <a href="https://github.com/gozargah/marzban" target="_blank" rel="noopener noreferrer" >
    <img src="https://github.com/Gozargah/Marzban-docs/raw/master/screenshots/preview.png" alt="Marzban screenshots" width="600" height="auto">
  </a>
</p>

## Índice

- [Visão Geral](#overview)
  - [Por que usar Marzban?](#why-using-marzban)
    - [Recursos](#features)
- [Guia de Instalação](#installation-guide)
- [Configuração](#configuration)
- [Documentação](#documentation)
- [API](#api)
- [Backup](#backup)
- [Bot do Telegram](#telegram-bot)
- [CLI do Marzban](#marzban-cli)
- [Node do Marzban](#marzban-node)
- [Notificações de Webhook](#webhook-notifications)
- [Doação](#donation)
- [Licença](#license)
- [Contribuidores](#contributors)

# Visão Geral

Marzban (a palavra persa para "guarda de fronteira" - pronunciado /mærz'ban/) é uma ferramenta de gerenciamento de proxy que fornece uma interface de usuário simples e fácil de usar para gerenciar centenas de contas de proxy alimentadas por Xray.

## Por que usar Marzban?

Marzban é amigável, rico em recursos e confiável. Ele permite que você crie diferentes proxies para seus usuários sem qualquer configuração complicada. Usando sua interface web integrada, você é capaz de monitorar e gerenciar suas contas de proxy facilmente.

### Recursos

- Interface web integrada
- Backend totalmente baseado em API REST
- Suporte a múltiplos nós (para distribuição de infraestrutura e escalabilidade)
- Suporta os protocolos Vmess, VLESS, Trojan e Shadowsocks
- Multi-protocolo para um único usuário
- Multi-usuário em uma única entrada
- Multi-entrada em uma única porta (suporte a fallbacks)
- Limitações de tráfego e data de expiração
- Limite de tráfego periódico (por exemplo, diário, semanal, etc.)
- Link de assinatura compatível com V2ray (como V2RayNG, SingBox, Nekoray, etc.), Clash e ClashMeta
- Gerador automático de link de compartilhamento e QRcode
- Monitoramento do sistema e estatísticas de tráfego
- Configuração personalizável do xray
- Suporte a TLS e REALITY
- Bot do Telegram integrado
- Interface de Linha de Comando Integrada (CLI)
- Multi-idioma
- Suporte a múltiplos administradores (em desenvolvimento)

# Guia de Instalação

Execute o comando a seguir para instalar o Marzban com banco de dados SQLite:

```bash
sudo bash -c "$(curl -sL https://github.com/Gozargah/Marzban-scripts/raw/master/marzban.sh)" @ install
```

Execute o comando a seguir para instalar o Marzban com banco de dados MySQL:

```bash
sudo bash -c "$(curl -sL https://github.com/Gozargah/Marzban-scripts/raw/master/marzban.sh)" @ install --database mysql
```

Execute o comando a seguir para instalar o Marzban com banco de dados MariaDB:
```bash
sudo bash -c "$(curl -sL https://github.com/Gozargah/Marzban-scripts/raw/master/marzban.sh)" @ install --database mariadb
```

Após a conclusão da instalação:

- Você verá os logs que pode parar de assistir fechando o terminal ou pressionando `Ctrl+C`
- Os arquivos do Marzban estarão localizados em `/opt/marzban`
- O arquivo de configuração pode ser encontrado em `/opt/marzban/.env` (consulte a seção de [configurações](#configuration) para ver as variáveis)
- Os arquivos de dados serão colocados em `/var/lib/marzban`
- Por razões de segurança, o painel do Marzban não é acessível via endereço IP. Portanto, você deve [obter um certificado SSL](https://gozargah.github.io/marzban/en/examples/issue-ssl-certificate)
- Você também pode usar o encaminhamento de porta SSH para acessar o painel do Marzban localmente sem um domínio. Substitua `user@serverip` pelo seu nome de usuário SSH e IP do servidor reais e execute o comando abaixo:

```bash
ssh -L 8000:localhost:8000 user@serverip
```

Finalmente, você pode inserir o seguinte link no seu navegador para acessar o painel do Marzban:

http://localhost:8000/dashboard/

Você perderá o acesso ao painel assim que fechar o terminal SSH. Portanto, este método é recomendado apenas para fins de teste.

Em seguida, você precisa criar um administrador sudo para fazer login no painel do Marzban com o comando a seguir

```bash
marzban cli admin create --sudo
```

É isso! Você pode fazer login no seu painel usando essas credenciais.

Para ver a mensagem de ajuda do script Marzban, execute o comando a seguir

```bash
marzban --help
```

Se você estiver ansioso para executar o projeto usando o código-fonte, verifique a seção abaixo.
<details markdown="1">
<summary><h3>Instalação Manual (avançado)</h3></summary>

Instale o xray na sua máquina

Você pode instalá-lo usando [Xray-install](https://github.com/XTLS/Xray-install)

```bash
bash -c "$(curl -L https://github.com/XTLS/Xray-install/raw/main/install-release.sh)" @ install
```

Clone este projeto e instale as dependências (você precisa de Python >= 3.8)

```bash
git clone https://github.com/Gozargah/Marzban.git
cd Marzban
wget -qO- https://bootstrap.pypa.io/get-pip.py | python3 -
python3 -m pip install -r requirements.txt
```

Alternativamente, para ter um ambiente isolado, você pode usar [Python Virtualenv](https://pypi.org/project/virtualenv/)

Em seguida, execute o comando a seguir para rodar os scripts de migração do banco de dados

```bash
alembic upgrade head
```

Se você quiser usar `marzban-cli`, deve vinculá-lo a um arquivo no seu `$PATH`, torná-lo executável e instalar a auto-completação:

```bash
sudo ln -s $(pwd)/marzban-cli.py /usr/bin/marzban-cli
sudo chmod +x /usr/bin/marzban-cli
marzban-cli completion install
```

Agora é hora de configurar

Faça uma cópia do arquivo `.env.example`, dê uma olhada e edite-o usando um editor de texto como `nano`.

Provavelmente você vai querer modificar as credenciais do administrador.

```bash
cp .env.example .env
nano .env
```

> Verifique a seção de [configurações](#configuration) para mais informações

Finalmente, inicie o aplicativo usando o comando abaixo

```bash
python3 main.py
```

Para iniciar com o systemctl do linux (copie o arquivo marzban.service para `/var/lib/marzban/marzban.service`)

```
systemctl enable /var/lib/marzban/marzban.service
systemctl start marzban
```

Para usar com nginx

```
server {
    listen 443 ssl http2;
    listen [::]:443 ssl http2;
    server_name  example.com;

    ssl_certificate      /etc/letsencrypt/live/example.com/fullchain.pem;
    ssl_certificate_key  /etc/letsencrypt/live/example.com/privkey.pem;

    location ~* /(dashboard|statics|sub|api|docs|redoc|openapi.json) {
        proxy_pass http://0.0.0.0:8000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }

    # xray-core ws-path: /
    # client ws-path: /marzban/me/2087
    #
    # Todo o tráfego é encaminhado através da porta 443 e enviado para a porta xray(2087, 2088, etc.).
    # O '/marzban' no caminho regex de localização pode ser alterado para quaisquer caracteres por você.
    #
    # /${path}/${username}/${xray-port}
    location ~* /marzban/.+/(.+)$ {
        proxy_redirect off;
        proxy_pass http://127.0.0.1:$1/;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
        proxy_set_header Host $http_host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }
}
```

ou

```
server {
    listen 443 ssl http2;
    listen [::]:443 ssl http2;
    server_name  marzban.example.com;

    ssl_certificate      /etc/letsencrypt/live/example.com/fullchain.pem;
    ssl_certificate_key  /etc/letsencrypt/live/example.com/privkey.pem;

    location / {
        proxy_pass http://0.0.0.0:8000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }
}
```

Por padrão, o aplicativo será executado em `http://localhost:8000/dashboard`. Você pode configurá-lo alterando as variáveis de ambiente `UVICORN_HOST` e `UVICORN_PORT`.
</details>

# Configuração

> Você pode definir as configurações abaixo usando variáveis de ambiente ou colocando-as no arquivo `.env`.

| Variável                                 | Descrição                                                                                                              |
| ---------------------------------------- |------------------------------------------------------------------------------------------------------------------------|
| SUDO_USERNAME                            | Nome de usuário do superusuário                                                                                        |
| SUDO_PASSWORD                            | Senha do superusuário                                                                                                  |
| SQLALCHEMY_DATABASE_URL                  | URL do banco de dados ([docs do SQLAlchemy](https://docs.sqlalchemy.org/en/20/core/engines.html#database-urls))        |
| UVICORN_HOST                             | Vincular o aplicativo a este host (padrão: `0.0.0.0`)                                                                  |
| UVICORN_PORT                             | Vincular o aplicativo a esta porta (padrão: `8000`)                                                                    |
| UVICORN_UDS                              | Vincular o aplicativo a um socket de domínio UNIX                                                                      |
| UVICORN_SSL_CERTFILE                     | Arquivo de certificado SSL para ter o aplicativo em https                                                              |
| UVICORN_SSL_KEYFILE                      | Arquivo de chave SSL para ter o aplicativo em https                                                                    |
| UVICORN_SSL_CA_TYPE                      | Tipo de certificado de autoridade SSL. Use `private` para testar CA autoassinado (padrão: `public`)                    |
| XRAY_JSON                                | Caminho do arquivo de configuração json do Xray (padrão: `xray_config.json`)                                           |
| XRAY_EXECUTABLE_PATH                     | Caminho do binário do Xray (padrão: `/usr/local/bin/xray`)                                                             |
| XRAY_ASSETS_PATH                         | Caminho dos ativos do Xray (padrão: `/usr/local/share/xray`)                                                           |
| XRAY_SUBSCRIPTION_URL_PREFIX             | Prefixo dos URLs de assinatura                                                                                         |
| XRAY_FALLBACKS_INBOUND_TAG               | Tag da entrada que inclui fallbacks, necessário no caso de você estar usando fallbacks                                 |
| XRAY_EXCLUDE_INBOUND_TAGS                | Tags das entradas que não devem ser gerenciadas e incluídas nos links pelo aplicativo                                  |
| CUSTOM_TEMPLATES_DIRECTORY               | Diretório de templates personalizados (padrão: `app/templates`)                                                        |
| CLASH_SUBSCRIPTION_TEMPLATE              | O template que será usado para gerar configs de Clash (padrão: `clash/default.yml`)                                    |
| SUBSCRIPTION_PAGE_TEMPLATE               | O template usado para gerar a página de informações de assinatura (padrão: `subscription/index.html`)                   |
| HOME_PAGE_TEMPLATE                       | Template da página de disfarce (padrão: `home/index.html`)                                                             |
| TELEGRAM_API_TOKEN                       | Token da API do bot do Telegram  (obtenha o token de [@botfather](https://t.me/botfather))                             |
| TELEGRAM_ADMIN_ID                        | ID numérico do administrador do Telegram (use [@userinfobot](https://t.me/userinfobot) para encontrar seu ID)          |
| TELEGRAM_PROXY_URL                       | Executar o bot do Telegram através de proxy                                                                            |
| JWT_ACCESS_TOKEN_EXPIRE_MINUTES          | Tempo de expiração dos tokens de acesso em minutos, `0` considerado como infinito (padrão: `1440`)                     |
| DOCS                                     | Se os documentos da API devem estar disponíveis em `/docs` e `/redoc` ou não (padrão: `False`)                         |
| DEBUG                                    | Modo de depuração para desenvolvimento (padrão: `False`)                                                               |
| WEBHOOK_ADDRESS                          | Endereço do webhook para enviar notificações. As notificações de webhook serão enviadas se este valor for definido.    |
| WEBHOOK_SECRET                           | O segredo do webhook será enviado com cada solicitação como `x-webhook-secret` no cabeçalho (padrão: `None`)           |
| NUMBER_OF_RECURRENT_NOTIFICATIONS        | Quantas vezes tentar novamente se um erro for detectado ao enviar uma notificação (padrão: `3`)                        |
| RECURRENT_NOTIFICATIONS_TIMEOUT          | Tempo de espera entre cada tentativa se um erro for detectado ao enviar uma notificação em segundos (padrão: `180`)    |
| NOTIFY_REACHED_USAGE_PERCENT             | Em qual porcentagem de uso enviar a notificação de aviso (padrão: `80`)                                                |
| NOTIFY_DAYS_LEFT                         | Quando enviar a notificação de aviso sobre a expiração (padrão: `3`)                                                   |
| USERS_AUTODELETE_DAYS                    | Excluir usuários expirados (e opcionalmente limitados) após esse número de dias (valores negativos desativam esse recurso, padrão: `-1`) |
| USER_AUTODELETE_INCLUDE_LIMITED_ACCOUNTS | Se deve incluir contas limitadas no recurso de exclusão automática (padrão: `False`)                                   |
| USE_CUSTOM_JSON_DEFAULT                  | Habilitar configuração JSON personalizada para TODOS os clientes suportados (padrão: `False`)                          |
| USE_CUSTOM_JSON_FOR_V2RAYNG              | Habilitar configuração JSON personalizada apenas para V2rayNG (padrão: `False`)                                        |
| USE_CUSTOM_JSON_FOR_STREISAND            | Habilitar configuração JSON personalizada apenas para Streisand (padrão: `False`)                                      |
| USE_CUSTOM_JSON_FOR_V2RAYN               | Habilitar configuração JSON personalizada apenas para V2rayN (padrão: `False`)                                         |

# Documentação

A [Documentação do Marzban](https://gozargah.github.io/marzban) fornece todos os guias essenciais para você começar, disponível em três idiomas: Farsi, Inglês e Russo. Essa documentação é continuamente atualizada para fornecer a você os guias mais recentes.

---

# API

O Marzban fornece uma API REST que permite aos desenvolvedores interagir programaticamente com os serviços do Marzban. Para visualizar a documentação da API no Swagger UI ou ReDoc, defina a variável de configuração `DOCS=True` e navegue até `/docs` e `/redoc`.
---

# Backup

É sempre uma boa ideia fazer backup dos seus arquivos do Marzban regularmente para evitar a perda de dados em caso de falhas do sistema ou exclusão acidental. Aqui estão os passos para fazer backup do Marzban:

1. Por padrão, todos os arquivos importantes do Marzban são salvos em `/var/lib/marzban` (versões Docker). Copie todo o diretório `/var/lib/marzban` para um local de backup de sua escolha, como um disco rígido externo ou armazenamento em nuvem.
2. Além disso, certifique-se de fazer backup do seu arquivo env, que contém suas variáveis de configuração, e também do seu arquivo de configuração do Xray. Se você instalou o Marzban usando marzban-scripts (abordagem de instalação recomendada), o arquivo env e outras configurações devem estar dentro do diretório `/opt/marzban/`.

O serviço de backup do Marzban compacta eficientemente todos os arquivos necessários e os envia para o bot do Telegram especificado. Ele suporta bancos de dados SQLite, MySQL e MariaDB. Uma de suas principais características é a automação, permitindo que você agende backups a cada hora. Não há limitações em relação aos limites de upload do Telegram para bots; se um arquivo exceder o limite, ele será dividido e enviado em várias partes. Além disso, você pode iniciar um backup imediato a qualquer momento.

Instale a Versão Mais Recente do Script do Marzban:
```bash
sudo bash -c "$(curl -sL https://github.com/Gozargah/Marzban-scripts/raw/master/marzban.sh)" @ install-script
```

Configurar o Serviço de Backup:
```bash
marzban backup-service
```

Obter um Backup Imediato:
```bash
marzban backup
```

Seguindo esses passos, você pode garantir que tem um backup de todos os seus arquivos e dados do Marzban, bem como suas variáveis de configuração e configuração do Xray, caso precise restaurá-los no futuro. Lembre-se de atualizar seus backups regularmente para mantê-los atualizados.
