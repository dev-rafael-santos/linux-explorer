# 01. Tudo começa na raiz (`/`)

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 30 minutos

**Pré-requisitos:**

* Módulo 01 — Fundamentos do Linux
* Módulo 02 — Terminal

────────────────────────────────────────────

# Visão Geral

Imagine que você acabou de instalar o Ubuntu.

Você abre o Terminal e começa a navegar pelo sistema.

Logo percebe algo curioso:

Não existe um disco **C:**.

Também não existe um disco **D:**.

Na verdade, tudo parece começar em um único lugar.

Esse lugar é chamado de **diretório raiz**.

Neste capítulo você entenderá por que toda a estrutura do Linux começa na raiz (`/`) e como essa organização difere da utilizada no Windows.

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

* Entender o conceito de diretório raiz.
* Compreender por que tudo começa em `/`.
* Visualizar a árvore principal do sistema de arquivos.
* Comparar a organização do Linux com a do Windows.

---

# Por que isso é importante?

Imagine uma árvore.

Ela possui:

* um tronco;
* vários galhos;
* centenas de folhas.

Mas tudo nasce do mesmo ponto.

No Linux acontece exatamente a mesma coisa.

Todos os diretórios do sistema fazem parte de uma única árvore.

Conhecer essa estrutura facilitará muito sua navegação e compreensão do sistema.

---

# Você vai conhecer

| Item                   | Informação                                         |
| ---------------------- | -------------------------------------------------- |
| Diretório              | `/`                                                |
| Nome                   | Diretório Raiz                                     |
| Importância            | ⭐⭐⭐⭐⭐                                              |
| Utilizado diariamente? | ✅ Sim                                              |
| Pode alterar?          | ⚠️ Com cuidado                                     |
| Equivalente no Windows | Aproximadamente `C:\` (com diferenças importantes) |

---

# O que é a raiz?

A raiz é o ponto inicial de todo o sistema de arquivos Linux.

Todos os diretórios existentes fazem parte dela.

Visualmente:

```text
/
```

Esse único caractere representa o início da árvore do sistema.

---

# Como funciona

Imagine uma árvore.

```text
/
│
├── home
├── etc
├── usr
├── var
├── boot
├── dev
├── proc
├── tmp
└── opt
```

Cada diretório possui uma responsabilidade específica.

Nos próximos capítulos estudaremos cada um deles separadamente.

---

# Comparando com o Windows

No Windows normalmente trabalhamos com diferentes unidades.

```text
C:\
D:\
E:\
```

Cada unidade possui sua própria árvore de diretórios.

No Linux a lógica é diferente.

Tudo faz parte da mesma árvore.

Mesmo discos adicionais podem ser "encaixados" em qualquer ponto dessa estrutura.

Essa característica torna o sistema muito mais flexível.

---

# Como descobrir onde você está?

Abra o Terminal e execute:

```bash
pwd
```

Se estiver no diretório pessoal, o resultado será semelhante a:

```text
/home/rafa
```

Agora execute:

```bash
cd /
```

Em seguida:

```bash
pwd
```

Resultado:

```text
/
```

Parabéns!

Você acabou de chegar ao ponto mais alto da árvore do sistema de arquivos Linux.

---

# Pratique

Execute os comandos abaixo:

```bash
pwd
```

```bash
cd /
```

```bash
pwd
```

Agora liste os diretórios da raiz:

```bash
ls
```

Observe os nomes exibidos.

Nos próximos capítulos estudaremos cada um deles.

---

# Explore

Navegue pela raiz utilizando:

```bash
ls /
```

Depois entre em alguns diretórios apenas para observar sua estrutura.

Por exemplo:

```bash
cd /home
ls
```

Depois retorne à raiz:

```bash
cd /
```

Não altere nenhum arquivo neste momento.

O objetivo é apenas explorar.

---

# Resumo rápido

| Situação                  | Comando |
| ------------------------- | ------- |
| Ir para a raiz            | `cd /`  |
| Mostrar o diretório atual | `pwd`   |
| Listar a raiz             | `ls /`  |

---

# Erros comuns

### Confundir `/` com `\`

No Linux utiliza-se:

```text
/
```

No Windows utiliza-se:

```text
\
```

---

### Pensar que a raiz é a pasta do usuário

Não.

O diretório pessoal normalmente é:

```text
/home/seu_usuario
```

A raiz é:

```text
/
```

Ela está acima de todos os demais diretórios.

---

# Curiosidade

Em sistemas Unix e Linux existe apenas uma árvore de diretórios.

Mesmo um novo HD, um SSD ou um pendrive será integrado a essa árvore por meio de um ponto de montagem.

Essa filosofia existe desde os primeiros sistemas Unix e continua sendo uma das características mais marcantes do Linux.

---

# Referências

* Filesystem Hierarchy Standard (FHS)
* Linux Foundation
* Ubuntu Documentation

---

# Conclusão

Neste capítulo você conheceu o ponto inicial do sistema de arquivos Linux: o diretório raiz (`/`).

Também aprendeu que todos os demais diretórios fazem parte de uma única árvore, diferentemente do que acontece no Windows.

Compreender esse conceito será fundamental para entender os próximos capítulos.

---

# Prepare-se para o próximo capítulo

Agora que você sabe onde tudo começa, chegou o momento de conhecer o diretório mais importante para o usuário comum:

**`/home`**

É nele que ficam seus arquivos pessoais, documentos, downloads, imagens e configurações individuais.
