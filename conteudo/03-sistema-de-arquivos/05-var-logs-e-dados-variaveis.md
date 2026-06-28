# 05. `/var` — Logs e dados variáveis

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 40 minutos

**Pré-requisitos:**

* Módulo 01 — Fundamentos do Linux
* Módulo 02 — Terminal
* Capítulos anteriores deste módulo

────────────────────────────────────────────

# Visão Geral

Imagine que um servidor parou de funcionar durante a madrugada.

Ao chegar para investigar o problema, qual seria um dos primeiros lugares que um administrador consultaria?

Na maioria das vezes, a resposta é:

**`/var`**

Esse diretório armazena informações que mudam constantemente durante o funcionamento do sistema, como logs, caches, bancos de dados e filas de impressão.

Neste capítulo você conhecerá sua estrutura e entenderá por que ele é tão importante.

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

* Entender a finalidade do diretório `/var`.
* Identificar seus principais subdiretórios.
* Compreender onde ficam os logs do sistema.
* Reconhecer aplicações que utilizam esse diretório.

---

# Por que isso é importante?

Sempre que algo der errado em um servidor Linux, uma das primeiras ações será consultar os arquivos de log.

Grande parte dessas informações está localizada em `/var`.

Mesmo desenvolvedores frequentemente precisam consultar esse diretório para investigar erros de aplicações.

---

# Quando você usará isso?

Você encontrará o diretório `/var` em diversas situações:

* Investigar erros do sistema.
* Consultar logs de servidores web.
* Analisar falhas de aplicações.
* Trabalhar com bancos de dados.
* Utilizar Docker.
* Monitorar serviços Linux.

---

# Você vai conhecer

| Item                   | Informação                                           |
| ---------------------- | ---------------------------------------------------- |
| Diretório              | `/var`                                               |
| Categoria              | Dados variáveis                                      |
| Importância            | ⭐⭐⭐⭐⭐                                                |
| Utilizado diariamente? | ✅ Sim                                                |
| Pode alterar?          | ⚠️ Com cuidado                                       |
| Equivalente no Windows | `C:\ProgramData` + Logs do Windows (conceitualmente) |

---

# O que é o diretório `/var`?

O nome **`var`** vem da palavra inglesa **Variable**.

Ele armazena arquivos cujo conteúdo muda constantemente durante a utilização do sistema.

Exemplos:

* logs;
* caches;
* filas;
* bancos de dados;
* arquivos temporários de serviços.

---

# Estrutura do `/var`

```text
/var
│
├── log
├── cache
├── lib
├── spool
├── tmp
└── mail
```

Cada subdiretório possui uma função específica.

---

# Conhecendo os principais subdiretórios

## `/var/log`

Armazena logs do sistema e de aplicações.

É um dos diretórios mais importantes para diagnóstico de problemas.

---

## `/var/cache`

Armazena arquivos temporários utilizados por programas para melhorar desempenho.

---

## `/var/lib`

Guarda dados persistentes utilizados por diversos serviços.

Exemplos:

* PostgreSQL
* MySQL
* Docker
* NetworkManager

---

## `/var/spool`

Utilizado para filas de impressão, e-mails e outras tarefas pendentes.

---

## `/var/tmp`

Semelhante ao `/tmp`, porém os arquivos costumam permanecer disponíveis por mais tempo.

---

# O que normalmente você encontrará aqui?

| Tipo de conteúdo | Exemplos                               |
| ---------------- | -------------------------------------- |
| Logs             | `/var/log/syslog`, `/var/log/auth.log` |
| Cache            | arquivos temporários de aplicações     |
| Bancos de dados  | PostgreSQL, MySQL                      |
| Docker           | volumes e metadados                    |
| Filas            | impressão e e-mails                    |

---

# Comparando com o Windows

| Windows                 | Linux        |
| ----------------------- | ------------ |
| Visualizador de Eventos | `/var/log`   |
| `C:\ProgramData`        | `/var/lib`   |
| Cache de aplicações     | `/var/cache` |

---

# 🛠️ Ferramentas que utilizam este diretório

Diversas aplicações importantes utilizam o `/var`, entre elas:

* Apache HTTP Server
* Nginx
* MySQL
* PostgreSQL
* Docker
* CUPS (impressão)
* Systemd

Mesmo que você nunca acesse esses diretórios manualmente, essas ferramentas dependem deles para armazenar informações importantes.

---

# Pratique

Entre no diretório:

```bash
cd /var
```

Confira onde está:

```bash
pwd
```

Liste seu conteúdo:

```bash
ls
```

Agora entre em:

```bash
cd /var/log
```

Liste alguns arquivos:

```bash
ls | head
```

---

# Explore

Visualize alguns logs:

```bash
ls /var/log
```

Se existir:

```bash
cat /var/log/syslog
```

ou

```bash
cat /var/log/auth.log
```

Caso algum arquivo não exista na sua distribuição, não se preocupe. Os nomes podem variar entre diferentes distribuições Linux.

---

# 💼 Exemplos do mundo real

Imagine que um servidor web deixou de responder.

Uma das primeiras verificações será consultar os logs armazenados em `/var/log`.

Outro exemplo é o Docker, que utiliza partes de `/var` para armazenar informações sobre contêineres, imagens e volumes.

Administradores de bancos de dados também trabalham frequentemente com arquivos armazenados em `/var/lib`.

---

# ⚠️ Pode alterar?

| Diretório | Pode alterar?  | Observação                                                 |
| --------- | -------------- | ---------------------------------------------------------- |
| `/var`    | ⚠️ Com cuidado | Alterações podem afetar serviços e aplicações em execução. |

---

# Você sabia?

Em servidores Linux, o diretório `/var/log` pode crescer bastante com o tempo.

Por isso, muitas distribuições utilizam ferramentas de rotação de logs, como o **logrotate**, para arquivar, compactar e remover logs antigos automaticamente.

---

# Resumo rápido

| Situação                | Comando       |
| ----------------------- | ------------- |
| Entrar em `/var`        | `cd /var`     |
| Entrar em `/var/log`    | `cd /var/log` |
| Listar conteúdo         | `ls`          |
| Mostrar diretório atual | `pwd`         |

---

# Erros comuns

* Excluir arquivos de log sem entender sua finalidade.
* Limpar caches indiscriminadamente.
* Alterar dados utilizados por serviços em execução.

---

# Referências

* Filesystem Hierarchy Standard (FHS)
* Ubuntu Documentation
* Linux Foundation

---

# Conclusão

Neste capítulo você conheceu o diretório `/var`, responsável por armazenar dados que mudam constantemente durante a execução do sistema.

Também identificou seus principais subdiretórios e compreendeu por que ele é essencial para monitoramento, diagnóstico e administração de sistemas Linux.

---

# Prepare-se para o próximo capítulo

Agora conheceremos um diretório que costuma gerar muitas dúvidas:

**`/tmp`**

Você descobrirá como o Linux utiliza arquivos temporários, quando eles são removidos e por que esse diretório é tão importante para o funcionamento de diversas aplicações.
