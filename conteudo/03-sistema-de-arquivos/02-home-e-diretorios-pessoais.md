# 02. Home e diretórios pessoais (`/home`)

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 35 minutos

**Pré-requisitos:**

* Módulo 01 — Fundamentos do Linux
* Módulo 02 — Terminal
* Capítulo 01 — Tudo começa na raiz (`/`)

────────────────────────────────────────────

# Visão Geral

Imagine que você acabou de instalar o Ubuntu.

Depois de ligar o computador pela primeira vez, você cria seu usuário:

**rafael**

Mas onde ficam seus documentos?

Onde estão suas imagens?

Onde ficam seus downloads?

No Linux, todos esses arquivos são armazenados dentro do diretório **Home**.

Neste capítulo você conhecerá esse diretório e entenderá por que ele é um dos locais mais importantes do sistema.

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

* Entender o conceito de diretório Home.
* Localizar seu diretório pessoal.
* Identificar os principais diretórios do usuário.
* Comparar a organização do Linux com a do Windows.

---

# Por que isso é importante?

Quase tudo o que você faz como usuário acontece dentro do seu diretório pessoal.

É nele que ficam:

* documentos;
* downloads;
* imagens;
* vídeos;
* músicas;
* configurações pessoais.

Conhecer essa estrutura permitirá trabalhar com segurança, sem alterar arquivos importantes do sistema.

---

# Você vai conhecer

| Item                   | Informação            |
| ---------------------- | --------------------- |
| Diretório              | `/home`               |
| Categoria              | Diretório de usuários |
| Importância            | ⭐⭐⭐⭐⭐                 |
| Utilizado diariamente? | ✅ Sim                 |
| Pode alterar?          | ✅ Sim                 |
| Equivalente no Windows | `C:\Users`            |

---

# O que é o diretório `/home`?

O diretório `/home` é onde o Linux armazena os diretórios pessoais dos usuários.

Cada usuário possui seu próprio espaço.

Exemplo:

```text
/home
│
├── rafael
├── maria
├── joao
└── ana
```

Cada pasta pertence a um usuário diferente.

Isso facilita a organização e aumenta a segurança do sistema.

---

# Seu diretório pessoal

Quando você faz login, normalmente inicia dentro do seu diretório pessoal.

Você pode verificar isso executando:

```bash
pwd
```

Saída:

```text
/home/rafael
```

O último nome do caminho corresponde ao nome do usuário conectado.

---

# O símbolo `~`

No Linux existe um atalho muito útil:

```text
~
```

Esse símbolo representa o diretório Home do usuário atual.

Por exemplo:

```bash
cd ~
```

ou simplesmente:

```bash
cd
```

Ambos levam você para o diretório pessoal.

---

# Estrutura do diretório Home

Dentro do diretório pessoal é comum encontrar pastas como:

```text
/home/rafael
│
├── Desktop
├── Documentos
├── Downloads
├── Imagens
├── Música
├── Público
├── Modelos
├── Vídeos
└── Área de Trabalho
```

Dependendo do idioma da distribuição, alguns nomes podem variar.

---

# Arquivos ocultos

Além das pastas visíveis, existe outro tipo de arquivo muito importante.

Execute:

```bash
ls -la
```

Você verá arquivos semelhantes a estes:

```text
.bashrc
.profile
.cache
.config
.local
```

Eles armazenam configurações do usuário.

Arquivos iniciados com um ponto (`.`) são considerados ocultos.

---

# Comparando com o Windows

| Windows           | Linux                                 |
| ----------------- | ------------------------------------- |
| `C:\Users`        | `/home`                               |
| `C:\Users\Rafael` | `/home/rafael`                        |
| Área de Trabalho  | `~/Desktop` ou equivalente localizado |
| Documentos        | `~/Documentos`                        |

Embora os nomes mudem, a ideia é semelhante: cada usuário possui seu próprio espaço para armazenar arquivos e configurações pessoais.

---

# Pratique

Execute:

```bash
pwd
```

Depois:

```bash
cd ~
```

Agora:

```bash
pwd
```

Por fim:

```bash
ls
```

Observe as pastas disponíveis no seu diretório pessoal.

---

# Explore

Liste também os arquivos ocultos:

```bash
ls -la
```

Procure identificar:

* `.bashrc`
* `.profile`
* `.config`

Não altere esses arquivos neste momento.

O objetivo é apenas conhecê-los.

---

# Você sabia?

Os arquivos iniciados com um ponto (`.`) são chamados de **dotfiles**.

Eles armazenam configurações pessoais de programas e do próprio ambiente de trabalho.

É por isso que muitos usuários conseguem configurar um novo computador simplesmente copiando seus dotfiles.

---

# Resumo rápido

| Situação                  | Comando  |
| ------------------------- | -------- |
| Ir para o diretório Home  | `cd`     |
| Ir para o diretório Home  | `cd ~`   |
| Mostrar o diretório atual | `pwd`    |
| Listar arquivos           | `ls`     |
| Listar arquivos ocultos   | `ls -la` |

---

# Erros comuns

* Confundir `/home` com `/root`.
* Alterar arquivos ocultos sem saber sua função.
* Pensar que `/home` contém arquivos do sistema.

Na prática, `/home` é destinado aos usuários.

---

# Curiosidade

Em muitas distribuições Linux é possível reinstalar o sistema operacional mantendo a partição `/home`.

Assim, documentos e configurações pessoais permanecem preservados mesmo após a reinstalação do sistema.

---

# Referências

* Filesystem Hierarchy Standard (FHS)
* Ubuntu Documentation
* Linux Foundation

---

# Conclusão

Neste capítulo você conheceu o diretório `/home`, responsável por armazenar os arquivos pessoais dos usuários.

Também aprendeu que cada usuário possui seu próprio diretório, onde ficam documentos, downloads, imagens e configurações pessoais.

Compreender essa estrutura é essencial para utilizar o Linux com segurança e organização.

---

# Prepare-se para o próximo capítulo

Agora que você conhece o diretório dos usuários, chegou o momento de explorar um dos diretórios mais importantes para o funcionamento do sistema:

**`/etc`**

É nele que ficam a maioria das configurações do Linux.
