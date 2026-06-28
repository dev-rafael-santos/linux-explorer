# 01. Criando Arquivos e Diretórios

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 40 minutos

**Pré-requisitos:**

- Capítulo 00 — Preparando o Linux Explorer Lab

────────────────────────────────────────────

# Visão Geral

Todo sistema operacional trabalha com arquivos e diretórios.

No Linux não é diferente.

Criar arquivos é uma das tarefas mais comuns do dia a dia de qualquer profissional.

Neste capítulo você aprenderá como criar arquivos e diretórios utilizando diferentes comandos do Terminal.

Todos os exercícios serão realizados dentro do Linux Explorer Lab.

---

# Estado atual do laboratório

Antes de começar, seu laboratório deverá estar semelhante a este:

```text
linux-explorer-lab
│
├── backup
├── compactados
├── documentos
│   └── meu-primeiro-arquivo.txt
├── downloads
├── imagens
├── projetos
├── temporarios
└── testes
```

Caso esteja diferente, volte ao capítulo anterior e prepare novamente o ambiente.

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

- criar arquivos;
- criar diretórios;
- criar vários diretórios de uma vez;
- criar estruturas completas utilizando apenas um comando.

---

# Por que isso é importante?

Sempre que iniciar um projeto, organizar documentos ou preparar ambientes de desenvolvimento, você utilizará comandos de criação de arquivos e diretórios.

Esses comandos fazem parte da rotina de qualquer usuário Linux.

---

# Quando você usará isso?

Você utilizará esses comandos para:

- iniciar novos projetos;
- criar estruturas de aplicações;
- organizar documentos;
- preparar backups;
- automatizar tarefas.

---

# Você vai conhecer

| Comando | Finalidade |
|----------|------------|
| `touch` | Criar arquivos |
| `mkdir` | Criar diretórios |
| `mkdir -p` | Criar estruturas completas |

---

# O comando `touch`

O comando `touch` é utilizado para criar arquivos vazios.

Sintaxe:

```bash
touch nome-do-arquivo
```

Exemplo:

```bash
touch arquivo.txt
```

Após executar esse comando, o arquivo será criado imediatamente.

---

# Criando vários arquivos

Você pode criar vários arquivos ao mesmo tempo.

Exemplo:

```bash
touch documento.txt notas.txt tarefas.txt
```

Todos os arquivos serão criados em um único comando.

---

# O comando `mkdir`

O comando `mkdir` cria diretórios.

Exemplo:

```bash
mkdir projetos-novos
```

Resultado:

```text
projetos-novos/
```

---

# Criando vários diretórios

Também é possível criar vários diretórios de uma vez.

```bash
mkdir frontend backend banco
```

Resultado:

```text
frontend/
backend/
banco/
```

---

# Criando estruturas completas

O parâmetro `-p` permite criar vários níveis simultaneamente.

```bash
mkdir -p projetos/site/css
```

Mesmo que os diretórios anteriores não existam, todos serão criados automaticamente.

---

# 🧠 Como o Linux enxerga isso?

Para o Linux, diretórios também são arquivos especiais.

Quando você utiliza:

```bash
mkdir documentos
```

o sistema cria uma nova entrada na árvore de arquivos.

Da mesma forma, quando utiliza:

```bash
touch arquivo.txt
```

o Kernel cria um novo inode representando aquele arquivo.

Você ainda não precisa conhecer detalhes sobre inodes.

Basta entender que criar um arquivo significa registrar sua existência dentro do sistema de arquivos.

---

# O que normalmente você encontrará aqui?

Após este capítulo, seu laboratório começará a crescer.

Você criará:

- arquivos de texto;
- diretórios;
- estruturas de projetos;
- árvores de diretórios.

Esses elementos serão utilizados nos próximos capítulos.

---

# Comparando com Windows

| Windows | Linux |
|----------|--------|
| Novo → Pasta | `mkdir` |
| Novo → Documento | `touch` |
| Explorer | Terminal |

---

# 🛠️ Ferramentas que utilizam esses comandos

Os comandos apresentados neste capítulo são utilizados diariamente em praticamente qualquer distribuição Linux.

Também são utilizados por diversas ferramentas e ambientes de desenvolvimento, como:

- Visual Studio Code
- Docker
- Git
- Node.js
- Python
- Java
- PHP
- Shell Scripts

Sempre que um projeto é criado automaticamente, existe uma grande chance de que comandos como `mkdir` e `touch` estejam sendo executados nos bastidores.

---

# Pratique

Entre no laboratório:

```bash
cd ~/linux-explorer-lab
```

Agora crie alguns arquivos:

```bash
touch documentos/clientes.txt
touch documentos/produtos.txt
touch documentos/fornecedores.txt
```

Liste os arquivos:

```bash
ls documentos
```

Agora crie alguns diretórios:

```bash
mkdir projetos/site
mkdir projetos/api
mkdir projetos/mobile
```

Liste novamente:

```bash
tree
```

---

# 🧪 Experimento

Agora vamos utilizar apenas um comando para criar uma estrutura completa.

Execute:

```bash
mkdir -p projetos/ecommerce/{frontend,backend,banco}
```

Agora visualize:

```bash
tree projetos
```

Observe que diversos diretórios foram criados automaticamente.

Experimente criar outra estrutura semelhante.

Por exemplo:

```bash
mkdir -p testes/linux/{scripts,logs,backup}
```

Visualize novamente:

```bash
tree
```

### O que observar?

Perceba como um único comando pode criar uma árvore inteira de diretórios.

Imagine quanto tempo isso economiza em projetos grandes.

---

# Explore

Experimente criar arquivos dentro dos diretórios recém-criados.

Por exemplo:

```bash
touch projetos/site/index.html
```

Depois:

```bash
touch projetos/api/app.py
```

Agora visualize toda a estrutura:

```bash
tree
```

Observe como o laboratório começa a parecer um projeto real.

---

# 💼 Exemplos do mundo real

Imagine que você iniciou um novo projeto Web.

Em poucos segundos você pode criar toda a estrutura inicial utilizando apenas um comando:

```bash
mkdir -p projeto-web/{css,js,img,fonts,pages}
```

Da mesma forma, uma API pode começar assim:

```bash
mkdir -p api/{controllers,models,routes,services}
```

Essa prática é muito comum em equipes de desenvolvimento.

---

# ⚠️ Pode alterar?

| Local | Pode alterar? | Observação |
|--------|---------------|------------|
| `~/linux-explorer-lab` | ✅ Sim | Ambiente criado exclusivamente para estudos. |

---

# 💡 Dica profissional

Antes de criar diretórios manualmente, pense na organização do projeto.

Uma boa estrutura facilita manutenção, colaboração entre equipes e automação de tarefas.

---

# 🧠 Mentalidade Linux

No Linux, criar arquivos e diretórios é uma operação extremamente simples.

Por isso, profissionais costumam automatizar a criação de estruturas utilizando scripts.

Em vez de criar dezenas de pastas manualmente, basta executar um único comando.

Automatizar tarefas repetitivas é uma das características mais importantes do ecossistema Linux.

---

# Você sabia?

O comando `touch` não serve apenas para criar arquivos.

Se o arquivo já existir, ele atualiza a data e a hora da última modificação (timestamp).

Esse comportamento é muito utilizado por scripts e ferramentas de automação.

---

# 🏁 Estado esperado do laboratório

Ao concluir este capítulo, seu laboratório deverá estar semelhante a este:

```text
linux-explorer-lab
│
├── backup
├── compactados
├── documentos
│   ├── clientes.txt
│   ├── fornecedores.txt
│   ├── meu-primeiro-arquivo.txt
│   └── produtos.txt
│
├── downloads
├── imagens
│
├── projetos
│   ├── api
│   │   └── app.py
│   │
│   ├── ecommerce
│   │   ├── backend
│   │   ├── banco
│   │   └── frontend
│   │
│   ├── mobile
│   └── site
│       └── index.html
│
├── temporarios
├── testes
│   └── linux
│       ├── backup
│       ├── logs
│       └── scripts
```

Se sua estrutura estiver semelhante a essa, significa que todos os exercícios foram executados corretamente.

---

# Resumo rápido

| Comando | Finalidade |
|----------|------------|
| `touch arquivo.txt` | Criar arquivo |
| `mkdir pasta` | Criar diretório |
| `mkdir pasta1 pasta2` | Criar vários diretórios |
| `mkdir -p projeto/site/css` | Criar estrutura completa |

---

# Erros comuns

- Criar arquivos fora do laboratório.
- Esquecer de utilizar `-p` ao criar estruturas com vários níveis.
- Digitar nomes de diretórios com espaços sem utilizar aspas.
- Não verificar em qual diretório você está antes de criar arquivos.

---

# Referências

- GNU Coreutils
- Linux Foundation
- Ubuntu Documentation

---

# Conclusão

Neste capítulo você aprendeu a criar arquivos e diretórios utilizando os comandos `touch` e `mkdir`.

Também conheceu o parâmetro `-p`, que permite criar estruturas completas com um único comando.

Esses comandos serão utilizados constantemente ao longo do restante do curso e fazem parte da rotina de qualquer profissional que trabalha com Linux.

---

# 🔗 Revisite este conceito

Lembre-se do **Módulo 03 — Sistema de Arquivos Linux**.

Agora que você conhece a organização dos diretórios, ficou muito mais fácil compreender onde criar arquivos e como estruturar projetos dentro do sistema.

---

# Prepare-se para o próximo capítulo

Agora que você já sabe criar arquivos e diretórios, chegou o momento de aprender a organizá-los.

No próximo capítulo você aprenderá a:

- copiar arquivos;
- mover arquivos entre diretórios;
- renomear arquivos e pastas.

Esses comandos estão entre os mais utilizados no dia a dia de qualquer usuário Linux.

---

---

# 📈 Evolução do Linux Explorer Lab

Ao concluir este capítulo, seu laboratório deverá estar semelhante ao exemplo abaixo.

```text
Linux Explorer Lab
│
├── backup
├── compactados
├── documentos
│   ├── clientes.txt
│   ├── fornecedores.txt
│   ├── meu-primeiro-arquivo.txt
│   └── produtos.txt
│
├── downloads
├── imagens
│
├── projetos
│   ├── api
│   │   └── app.py
│   │
│   ├── ecommerce
│   │   ├── backend
│   │   ├── banco
│   │   └── frontend
│   │
│   ├── mobile
│   └── site
│       └── index.html
│
├── temporarios
└── testes
    └── linux
        ├── backup
        ├── logs
        └── scripts
```

## Competências conquistadas

Até este momento você já domina:

* ✅ Preparar um ambiente seguro para estudos.
* ✅ Criar arquivos com `touch`.
* ✅ Criar diretórios com `mkdir`.
* ✅ Criar estruturas completas com `mkdir -p`.
* ✅ Organizar arquivos e projetos utilizando o Terminal.

À medida que os próximos capítulos forem sendo concluídos, novas competências serão adicionadas a esta lista.

Seu laboratório também continuará evoluindo, acompanhando seu aprendizado.
