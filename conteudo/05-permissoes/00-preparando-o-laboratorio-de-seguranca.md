# 00. Preparando o Laboratório de Segurança

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 30 minutos

**Pré-requisitos:**

- Conclusão do Módulo 04 — Manipulação de Arquivos e Diretórios

────────────────────────────────────────────

# Visão Geral

Neste módulo você aprenderá como o Linux controla quem pode acessar, modificar e executar arquivos.

Para praticar esses conceitos com segurança, criaremos um novo ambiente dentro do Linux Explorer Lab.

Durante todos os capítulos deste módulo, os experimentos serão realizados nesse laboratório.

Assim, você poderá alterar permissões e propriedades sem afetar arquivos importantes do sistema.

---

# Objetivo do laboratório

Ao concluir esta preparação, você terá um ambiente contendo:

- arquivos públicos;
- arquivos privados;
- diretórios compartilhados;
- scripts;
- usuários fictícios (quando possível);
- estruturas para experimentar permissões.

Esse ambiente será utilizado em todos os capítulos do módulo.

---

# Estrutura do laboratório

Ao final desta preparação, sua estrutura deverá ficar semelhante a esta:

```text
linux-explorer-lab
│
└── seguranca
    ├── documentos
    ├── grupos
    ├── privados
    ├── publicos
    ├── scripts
    ├── compartilhados
    └── testes
```

---

# Criando o ambiente

Entre no laboratório:

```bash
cd ~/linux-explorer-lab
```

Crie toda a estrutura:

```bash
mkdir -p seguranca/{documentos,grupos,privados,publicos,scripts,compartilhados,testes}
```

Visualize:

```bash
tree seguranca
```

---

# Criando arquivos para os exercícios

Execute:

```bash
touch seguranca/publicos/manual.txt

touch seguranca/privados/senha.txt

touch seguranca/documentos/relatorio.txt

touch seguranca/scripts/backup.sh

touch seguranca/compartilhados/README.md
```

Confira:

```bash
tree seguranca
```

---

# Criando um pequeno script

Abra o arquivo:

```bash
nano seguranca/scripts/backup.sh
```

Cole:

```bash
#!/bin/bash

echo "Backup iniciado..."
```

Salve:

```
CTRL + O
ENTER
CTRL + X
```

---

# O que você aprenderá neste módulo?

Durante este módulo estudaremos:

- leitura das permissões;
- chmod;
- chown;
- chgrp;
- permissões especiais;
- umask;
- ACLs;
- boas práticas de segurança.

Todo o aprendizado acontecerá utilizando esse laboratório.

---

# 🧠 Como o Linux enxerga isso?

No Linux, praticamente tudo possui permissões.

Arquivos.

Diretórios.

Scripts.

Dispositivos.

Até mesmo processos dependem de permissões para funcionar corretamente.

Por isso, compreender esse mecanismo é fundamental para administrar qualquer sistema Linux.

---

# Estado esperado do laboratório

Ao concluir esta preparação, sua estrutura deverá estar semelhante a:

```text
linux-explorer-lab
│
└── seguranca
    ├── compartilhados
    │   └── README.md
    │
    ├── documentos
    │   └── relatorio.txt
    │
    ├── grupos
    │
    ├── privados
    │   └── senha.txt
    │
    ├── publicos
    │   └── manual.txt
    │
    ├── scripts
    │   └── backup.sh
    │
    └── testes
```

---

# Resumo rápido

| Comando | Finalidade |
|----------|------------|
| `mkdir -p` | Criar estrutura do laboratório |
| `touch` | Criar arquivos |
| `nano` | Editar arquivos |
| `tree` | Visualizar estrutura |

---

# Conclusão

O Laboratório de Segurança está pronto.

Durante todo este módulo você utilizará essa estrutura para compreender como o Linux controla o acesso aos arquivos e diretórios.

---

# Prepare-se para o próximo capítulo

Agora começaremos a estudar o conceito mais importante da segurança no Linux:

**Como interpretar permissões como:**

```text
-rwxr-xr--
```

Ao final do próximo capítulo, essa sequência deixará de ser um conjunto de letras e passará a representar exatamente quem pode fazer o quê dentro do sistema.

---

# 📈 Evolução do Laboratório de Segurança

## Competências conquistadas

Até este momento você já consegue:

- ✅ Preparar o Laboratório de Segurança.
- ✅ Criar a estrutura de diretórios do módulo.
- ✅ Criar arquivos para experimentação.
- ✅ Preparar scripts para os próximos exercícios.

Nos próximos capítulos, cada diretório desse laboratório será utilizado para experimentar permissões e propriedades de forma segura.
