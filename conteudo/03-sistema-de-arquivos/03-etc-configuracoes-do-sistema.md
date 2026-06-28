# 03. `/etc` — Configurações do sistema

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 35 minutos

**Pré-requisitos:**

* Módulo 01 — Fundamentos do Linux
* Módulo 02 — Terminal
* Capítulos anteriores deste módulo

────────────────────────────────────────────

# Visão Geral

Imagine que você deseja alterar o nome do computador.

Ou configurar a rede.

Ou modificar o comportamento de algum serviço do sistema.

Onde essas configurações ficam?

No Linux, grande parte delas está concentrada no diretório **`/etc`**.

Neste capítulo você entenderá por que esse diretório é tão importante e aprenderá a explorá-lo com segurança.

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

* Entender a função do diretório `/etc`.
* Identificar alguns dos principais arquivos de configuração.
* Diferenciar configurações do sistema das configurações do usuário.
* Explorar o diretório sem alterar arquivos importantes.

---

# Por que isso é importante?

Praticamente toda configuração importante do Linux passa por arquivos localizados em `/etc`.

É por isso que administradores de sistemas acessam esse diretório diariamente.

Mesmo como desenvolvedor, você encontrará configurações de serviços, bancos de dados, servidores web e diversas aplicações armazenadas ali.

---

# Quando você usará isso?

Você encontrará o diretório `/etc` em várias situações práticas, como:

- Configurar o nome da máquina.
- Ajustar configurações de rede.
- Configurar acesso SSH.
- Administrar usuários e grupos.
- Configurar servidores web.
- Configurar bancos de dados.
- Ajustar serviços do sistema.
- Investigar problemas de configuração.

Mesmo que você não altere arquivos em `/etc` todos os dias, é muito comum consultar esse diretório para entender como o sistema está configurado.

---

# Você vai conhecer

| Item                   | Informação                                                       |
| ---------------------- | ---------------------------------------------------------------- |
| Diretório              | `/etc`                                                           |
| Categoria              | Configurações do sistema                                         |
| Importância            | ⭐⭐⭐⭐⭐                                                            |
| Utilizado diariamente? | ✅ Sim                                                            |
| Pode alterar?          | ⚠️ Com cuidado                                                   |
| Equivalente no Windows | Registro do Windows (conceitualmente) + arquivos de configuração |

---

# O que é o diretório `/etc`?

O diretório `/etc` armazena arquivos de configuração utilizados pelo sistema operacional e por diversos programas.

Em vez de guardar essas informações em um banco de dados central, como o Registro do Windows, o Linux utiliza principalmente arquivos de texto.

Isso torna as configurações mais transparentes e fáceis de gerenciar.

---

# Como funciona

Veja uma visão simplificada:

```text
/etc
│
├── hostname
├── hosts
├── passwd
├── group
├── fstab
├── ssh/
├── network/
└── ...
```

Cada arquivo ou subdiretório possui uma finalidade específica.

Você não precisa decorar todos agora. Vamos conhecer os mais importantes.

---

# Alguns arquivos importantes

## `/etc/hostname`

Define o nome do computador.

Exemplo:

```text
ubuntu
```

---

## `/etc/hosts`

Relaciona nomes de máquinas a endereços IP.

É muito utilizado para testes e desenvolvimento local.

---

## `/etc/passwd`

Contém informações sobre os usuários cadastrados no sistema.

**Importante:** ele não armazena as senhas dos usuários.

---

## `/etc/group`

Armazena os grupos existentes no sistema e quais usuários pertencem a cada grupo.

---

## `/etc/fstab`

Define quais discos e partições devem ser montados automaticamente durante a inicialização do sistema.

---

# Comparando com o Windows

| Windows                  | Linux              |
| ------------------------ | ------------------ |
| Registro do Windows      | `/etc`             |
| Nome do computador       | `/etc/hostname`    |
| Arquivo Hosts            | `/etc/hosts`       |
| Configurações do sistema | Arquivos em `/etc` |

A abordagem do Linux facilita backups, auditorias e controle de versões, já que muitas configurações são apenas arquivos de texto.

---

# Pratique

Entre no diretório:

```bash
cd /etc
```

Confira onde você está:

```bash
pwd
```

Liste alguns arquivos:

```bash
ls
```

Agora visualize apenas os primeiros itens:

```bash
ls | head
```

Observe a quantidade de arquivos e diretórios disponíveis.

---

# Explore

Pesquise alguns arquivos específicos:

```bash
ls /etc/hostname
```

```bash
ls /etc/hosts
```

```bash
ls /etc/passwd
```

Você também pode visualizar o conteúdo desses arquivos utilizando:

```bash
cat /etc/hostname
```

```bash
cat /etc/hosts
```

Neste momento, apenas observe o conteúdo.

Não faça alterações.

---

# ⚠️ Pode alterar?

| Diretório | Pode alterar?  | Observação                                         |
| --------- | -------------- | -------------------------------------------------- |
| `/etc`    | ⚠️ Com cuidado | Alterações incorretas podem afetar todo o sistema. |

Sempre faça alterações apenas quando souber exatamente o que está modificando.

---

# Você sabia?

O nome **`etc`** tem origem histórica no Unix.

Embora muitas pessoas associem o nome à palavra inglesa *etcetera*, na prática ele passou a representar o local destinado aos arquivos de configuração do sistema.

Hoje, essa é a função reconhecida pela comunidade Linux.

---

# Resumo rápido

| Situação                      | Comando       |
| ----------------------------- | ------------- |
| Entrar no diretório           | `cd /etc`     |
| Listar arquivos               | `ls`          |
| Mostrar diretório atual       | `pwd`         |
| Exibir conteúdo de um arquivo | `cat arquivo` |

---

# Erros comuns

* Alterar arquivos sem criar um backup.
* Editar configurações como usuário comum esperando que a alteração seja salva.
* Confundir configurações do sistema (`/etc`) com configurações do usuário (`~/.config` e outros dotfiles).

---

# Referências

* Filesystem Hierarchy Standard (FHS)
* Ubuntu Documentation
* Linux Foundation

---

# Conclusão

Neste capítulo você conheceu o diretório `/etc`, responsável por armazenar grande parte das configurações do sistema Linux.

Também aprendeu que o Linux utiliza principalmente arquivos de texto para armazenar essas configurações, o que torna o sistema transparente e flexível.

Nos próximos módulos, vários desses arquivos voltarão a aparecer quando estudarmos administração do sistema e serviços.

---

# Prepare-se para o próximo capítulo

Até agora conhecemos:

* Onde ficam os usuários (`/home`);
* Onde ficam as configurações (`/etc`).

No próximo capítulo responderemos outra pergunta importante:

> **Onde ficam os programas instalados no Linux?**

Você conhecerá o diretório **`/usr`**, um dos maiores e mais importantes do sistema.
