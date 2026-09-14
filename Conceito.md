
# 🥑 Apache Guacamole

---

## 💡 O que é Apache Guacamole

O **Apache Guacamole** é uma aplicação web baseada em **HTML5** que permite realizar acesso remoto a máquinas **Linux e Windows**, incluindo servidores e desktops, diretamente pelo navegador web, sem instalação de agentes, softwares adicionais ou plugins.

O software **Apache Guacamole** serve como uma ferramenta de Área de Trabalho Remota, pois permite conexão SSH, VNC e RDP. Ele funciona como um "gateway" de Desktop Remoto que só precisa ser instalado em um servidor central. Assim, ele fornecerá um painel de controle, baseado na web, que lhe permitirá mudar rapidamente de uma máquina para outra tudo dentro da mesma janela no navegador. A presença de um proxy ou firewall corporativo não impede o uso do Guacamole

### 🔐 Protocolos suportados

O Guacamole funciona como um **gateway de acesso remoto**, oferecendo suporte a diferentes protocolos, como:

- 🐧 **SSH** — acesso remoto a servidores Linux;
- 🪟 **RDP** — acesso remoto a máquinas Windows;
- 🖥️ **VNC** — acesso remoto a desktops e outros sistemas compatíveis.

### 🌐 Como funciona?

O Guacamole é instalado em um **servidor central**, que atua como intermediário entre o usuário e as máquinas de destino.

O acesso ocorre de forma semelhante a:

```text
┌─────────────────┐
│     Usuário     │
│   Navegador Web │
└────────┬────────┘
         │
         │ HTTPS
         ▼
┌─────────────────┐
│    Guacamole    │
│     Gateway     │
└────────┬────────┘
         │
    ┌────┼────┐
    │    │    │
    ▼    ▼    ▼
  SSH   RDP   VNC
    │    │    │
    ▼    ▼    ▼
 Linux Windows Desktop

 ```

 ## 🏗️ Arquitetura do Apache Guacamole

O **Apache Guacamole** permite centralizar o acesso remoto a diferentes máquinas em uma única interface web.

Em vez de o usuário precisar memorizar os endereços IP, protocolos e credenciais de cada máquina, ele realiza a autenticação em um **servidor central** e visualiza as conexões às quais possui permissão de acesso.

A partir do painel do Guacamole, o usuário pode selecionar uma conexão e acessar o recurso correspondente diretamente pelo navegador.


### 🔄 Fluxo de acesso

```text
┌─────────────────┐
│     Usuário     │
│   Navegador Web │
└────────┬────────┘
         │
         │ HTTPS
         ▼
┌─────────────────┐
│    Guacamole    │
│ Servidor Central│
└────────┬────────┘
         │
    ┌────┼────┐
    │    │    │
    ▼    ▼    ▼
  SSH   RDP   VNC
    │    │    │
    ▼    ▼    ▼
 Linux Windows Desktop
