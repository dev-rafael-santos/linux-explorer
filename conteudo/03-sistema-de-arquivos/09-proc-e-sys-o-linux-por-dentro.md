# 09. `/proc` e `/sys` — O Linux por dentro

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 45 minutos

**Pré-requisitos:**

- Módulos anteriores
- Capítulos anteriores deste módulo

────────────────────────────────────────────

# Visão Geral

Imagine abrir um arquivo e descobrir:

- quanto de memória o computador possui;
- qual versão do Kernel está em execução;
- informações sobre o processador;
- detalhes dos dispositivos conectados.

O mais curioso é que esses "arquivos" não estão gravados no disco.

Eles são gerados pelo Kernel no momento em que você os acessa.

Neste capítulo você conhecerá dois sistemas de arquivos virtuais extremamente importantes:

- `/proc`
- `/sys`

Eles funcionam como uma janela para o funcionamento interno do Linux.

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

- Entender o que são sistemas de arquivos virtuais.
- Conhecer a função de `/proc`.
- Conhecer a função de `/sys`.
- Consultar informações do sistema em tempo real.
- Entender como o Kernel disponibiliza essas informações.

---

# Por que isso é importante?

Grande parte das ferramentas utilizadas para monitoramento do Linux consulta informações presentes em `/proc` e `/sys`.

Quando você utiliza comandos como:

- top
- free
- uptime
- ps
- lscpu

essas ferramentas consultam informações disponibilizadas por esses diretórios.

---

# Quando você usará isso?

Você utilizará esses diretórios para:

- monitorar servidores;
- descobrir informações do hardware;
- analisar processos;
- estudar o Kernel;
- solucionar problemas;
- desenvolver aplicações de baixo nível.

---

# Você vai conhecer

| Item | Informação |
|------|------------|
| Diretórios | `/proc` e `/sys` |
| Categoria | Sistemas de arquivos virtuais |
| Importância | ⭐⭐⭐⭐⭐ |
| Utilizado diariamente? | ⚠️ Indiretamente |
| Pode alterar? | ⚠️ Muito cuidado |
| Equivalente no Windows | Não existe equivalente direto |

---

# O que é o diretório `/proc`?

O diretório `/proc` fornece informações sobre:

- processos;
- memória;
- CPU;
- Kernel;
- sistema.

Essas informações são geradas dinamicamente.

Elas não ocupam espaço em disco como arquivos tradicionais.

---

# O que é o diretório `/sys`?

O diretório `/sys` apresenta informações relacionadas principalmente ao hardware e aos dispositivos gerenciados pelo Kernel.

Ele permite visualizar como o sistema enxerga componentes como:

- discos;
- interfaces de rede;
- barramentos;
- dispositivos USB;
- módulos do Kernel.

---

# Como funciona

Imagine o Kernel como uma grande central de informações.

Quando um programa precisa descobrir algo sobre o computador, ele consulta `/proc` ou `/sys`.

```text
Aplicação
      │
      ▼
 /proc ou /sys
      │
      ▼
    Kernel
      │
      ▼
 Hardware
```

---

# 🧠 Como o Linux enxerga isso?

Esses diretórios fazem parte de sistemas de arquivos virtuais.

Isso significa que:

- os arquivos não estão gravados no disco;
- seu conteúdo é criado pelo Kernel quando solicitado;
- as informações refletem o estado atual do sistema.

---

# O que normalmente você encontrará em `/proc`?

```text
/proc
│
├── cpuinfo
├── meminfo
├── uptime
├── version
├── modules
└── 1234/
```

Arquivos importantes:

| Arquivo | Função |
|----------|--------|
| `cpuinfo` | Informações do processador |
| `meminfo` | Memória RAM |
| `uptime` | Tempo ligado |
| `version` | Versão do Kernel |

---

# O que normalmente você encontrará em `/sys`?

```text
/sys
│
├── class
├── devices
├── block
├── bus
└── firmware
```

Esses diretórios representam o hardware conhecido pelo Kernel.

---

# Comparando com o Windows

| Windows | Linux |
|----------|--------|
| Gerenciador de Tarefas | `/proc` (parcialmente) |
| Gerenciador de Dispositivos | `/sys` (conceitualmente) |
| Informações do Sistema | `/proc` |

---

# 🛠️ Ferramentas que utilizam esses diretórios

Diversas ferramentas consultam constantemente esses sistemas de arquivos:

- top
- htop
- free
- ps
- lscpu
- lsblk
- vmstat
- iostat

---

# Pratique

Entre em:

```bash
cd /proc
```

Veja alguns arquivos:

```bash
ls
```

Agora visualize informações da CPU:

```bash
cat /proc/cpuinfo
```

Veja a memória:

```bash
cat /proc/meminfo
```

Agora consulte o tempo ligado:

```bash
cat /proc/uptime
```

---

# Explore

Entre em:

```bash
cd /sys
```

Liste seu conteúdo:

```bash
ls
```

Observe a quantidade de informações relacionadas ao hardware.

Não altere nenhum arquivo.

---

# 💼 Exemplos do mundo real

Imagine que um servidor apresentou lentidão.

Antes mesmo de instalar ferramentas adicionais, um administrador pode consultar:

- `/proc/meminfo`
- `/proc/cpuinfo`
- `/proc/loadavg`

para obter informações importantes sobre o sistema.

Da mesma forma, diversas ferramentas gráficas consultam `/sys` para identificar dispositivos conectados.

---

# ⚠️ Pode alterar?

| Diretório | Pode alterar? | Observação |
|-----------|---------------|------------|
| `/proc` | ⚠️ Muito cuidado | Alguns arquivos permitem alterar parâmetros do Kernel. |
| `/sys` | ⚠️ Muito cuidado | Pode alterar o comportamento de dispositivos. |

---

# 💡 Dica profissional

Mesmo sendo arquivos de texto, nunca altere conteúdos em `/proc` ou `/sys` sem compreender exatamente sua finalidade.

Esses diretórios permitem modificar parâmetros importantes do sistema.

---

# 🧠 Mentalidade Linux

No Linux, o Kernel disponibiliza informações e interfaces de configuração utilizando arquivos.

Essa filosofia permite que programas obtenham informações do sistema utilizando operações simples de leitura, mantendo uma interface consistente em todo o sistema operacional.

---

# Você sabia?

Diversos comandos tradicionais do Linux, como `free`, `uptime` e `lscpu`, não calculam essas informações por conta própria.

Eles apenas leem dados disponibilizados pelo Kernel em `/proc` e `/sys`.

---

# Resumo rápido

| Situação | Comando |
|----------|----------|
| Entrar em `/proc` | `cd /proc` |
| Ver CPU | `cat /proc/cpuinfo` |
| Ver memória | `cat /proc/meminfo` |
| Ver tempo ligado | `cat /proc/uptime` |
| Entrar em `/sys` | `cd /sys` |

---

# Erros comuns

- Pensar que esses arquivos existem no disco.
- Alterar parâmetros do Kernel sem conhecimento.
- Confundir `/proc` com diretórios tradicionais.

---

# Referências

- Linux Foundation
- Kernel.org
- Filesystem Hierarchy Standard (FHS)

---

# Conclusão

Neste capítulo você conheceu os diretórios `/proc` e `/sys`, que permitem acessar informações sobre o sistema operacional, o Kernel e o hardware em tempo real.

Esses sistemas de arquivos virtuais demonstram uma das características mais elegantes do Linux: disponibilizar informações do sistema por meio de arquivos.

---

# 🔗 Revisite este conceito

Lembre-se do capítulo sobre o Kernel no Módulo 01.

É o Kernel quem gera dinamicamente as informações apresentadas em `/proc` e `/sys`, mantendo esses diretórios sempre atualizados.

---

# Prepare-se para o próximo capítulo

Agora conheceremos o último diretório deste módulo:

**`/opt`**.

Você descobrirá por que alguns programas são instalados nesse local e em quais situações ele é utilizado.
