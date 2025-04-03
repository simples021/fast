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
