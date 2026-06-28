# 04. `/usr` — Programas e bibliotecas do sistema

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 40 minutos

**Pré-requisitos:**

* Módulo 01 — Fundamentos do Linux
* Módulo 02 — Terminal
* Capítulos anteriores deste módulo

────────────────────────────────────────────

# Visão Geral

Imagine que você acabou de instalar o Ubuntu.

Depois instala o Git.

Depois instala o Python.

Depois instala o VS Code.

Mas onde esses programas ficam armazenados?

Ao contrário do que muitos imaginam, eles não ficam no diretório `/home`.

Grande parte dos programas instalados pelo sistema é armazenada dentro do diretório **`/usr`**.

Neste capítulo você entenderá a função desse diretório e conhecerá sua estrutura principal.

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

* Entender a finalidade do diretório `/usr`.
* Conhecer seus principais subdiretórios.
* Diferenciar programas do sistema e arquivos do usuário.
* Entender por que `/usr` é um dos maiores diretórios do Linux.

---

# Por que isso é importante?

Sempre que você instalar um compilador, uma linguagem de programação, um editor ou diversas ferramentas do sistema, parte desses arquivos estará localizada em `/usr`.

Mesmo sem perceber, você utilizará esse diretório diariamente.

---

# Quando você usará isso?

Você encontrará o diretório `/usr` em diversas situações:

* Instalação de programas.
* Desenvolvimento de software.
* Utilização de compiladores.
* Execução de comandos do sistema.
* Consulta de manuais.
* Administração de servidores.
* Investigação de dependências de aplicações.

Conhecer sua estrutura facilita bastante a compreensão de como o Linux organiza seus programas.

---

# Você vai conhecer

| Item                   | Informação                           |
| ---------------------- | ------------------------------------ |
| Diretório              | `/usr`                               |
| Categoria              | Programas e bibliotecas              |
| Importância            | ⭐⭐⭐⭐⭐                                |
| Utilizado diariamente? | ✅ Sim                                |
| Pode alterar?          | ⚠️ Com cuidado                       |
| Equivalente no Windows | `C:\Program Files` (aproximadamente) |

---

# O que é o diretório `/usr`?

O diretório `/usr` reúne boa parte dos programas, bibliotecas, documentações e arquivos compartilhados utilizados pelo sistema.

Ele não pertence a um usuário específico.

Seu conteúdo pode ser utilizado por todos os usuários do computador.

---

# Estrutura do `/usr`

Uma visão simplificada:

```text
/usr
│
├── bin
├── lib
├── local
├── sbin
├── share
└── src
```

Cada subdiretório possui uma finalidade específica.

---

# Conhecendo os principais subdiretórios

## `/usr/bin`

Contém milhares de programas executáveis utilizados pelos usuários.

Exemplos:

* python
* git
* nano
* ls
* cat

Quando você executa um comando no Terminal, muitas vezes ele está localizado aqui.

---

## `/usr/lib`

Armazena bibliotecas compartilhadas utilizadas pelos programas.

Essas bibliotecas evitam duplicação de código e permitem que diferentes aplicações reutilizem os mesmos recursos.

---

## `/usr/share`

Contém arquivos independentes da arquitetura do computador.

Exemplos:

* documentação;
* ícones;
* traduções;
* arquivos de ajuda.

---

## `/usr/local`

Reservado para programas instalados manualmente pelo administrador.

É muito comum utilizá-lo quando compilamos programas a partir do código-fonte.

---

## `/usr/sbin`

Contém programas administrativos utilizados principalmente para gerenciamento do sistema.

---

## `/usr/src`

Utilizado para armazenar códigos-fonte de programas e, em alguns casos, do próprio kernel.

---

# Comparando com o Windows

| Windows                 | Linux        |
| ----------------------- | ------------ |
| `C:\Program Files`      | `/usr`       |
| Executáveis             | `/usr/bin`   |
| Bibliotecas (.dll)      | `/usr/lib`   |
| Arquivos compartilhados | `/usr/share` |

Embora existam diferenças importantes, essa comparação ajuda a entender a finalidade geral do diretório.

---

# Pratique

Entre no diretório:

```bash
cd /usr
```

Confira sua localização:

```bash
pwd
```

Liste o conteúdo:

```bash
ls
```

Agora entre em:

```bash
cd /usr/bin
```

Liste alguns programas:

```bash
ls | head
```

Observe a quantidade de executáveis disponíveis.

---

# Explore

Explore outros subdiretórios:

```bash
cd /usr/share
ls
```

Depois:

```bash
cd /usr/lib
ls | head
```

Não altere nenhum arquivo.

O objetivo é apenas compreender a organização do sistema.

---

# ⚠️ Pode alterar?

| Diretório | Pode alterar?  | Observação                                                        |
| --------- | -------------- | ----------------------------------------------------------------- |
| `/usr`    | ⚠️ Com cuidado | Alterações incorretas podem impedir o funcionamento de programas. |

---

# Você sabia?

O nome **`/usr`** costuma gerar confusão.

Muitas pessoas imaginam que ele significa **User**.

Historicamente, porém, sua origem é **Unix System Resources**, pois ele reúne recursos compartilhados utilizados pelo sistema e pelos usuários.

---

# Resumo rápido

| Situação                | Comando       |
| ----------------------- | ------------- |
| Entrar em `/usr`        | `cd /usr`     |
| Listar conteúdo         | `ls`          |
| Entrar em `/usr/bin`    | `cd /usr/bin` |
| Mostrar diretório atual | `pwd`         |

---

# Erros comuns

* Pensar que arquivos pessoais ficam em `/usr`.
* Alterar arquivos do sistema sem necessidade.
* Confundir `/usr/local` com o diretório pessoal do usuário.

---

# Referências

* Filesystem Hierarchy Standard (FHS)
* Ubuntu Documentation
* Linux Foundation

---

# Conclusão

Neste capítulo você conheceu o diretório `/usr`, responsável por armazenar programas, bibliotecas, documentação e diversos recursos compartilhados do sistema.

Também explorou seus principais subdiretórios e compreendeu por que ele é um dos componentes mais importantes da estrutura do Linux.

---

# Prepare-se para o próximo capítulo

Até agora conhecemos:

* Onde ficam os usuários (`/home`);
* Onde ficam as configurações (`/etc`);
* Onde ficam os programas (`/usr`).

No próximo capítulo descobriremos onde o Linux armazena logs, filas de impressão, bancos de dados e outros arquivos que mudam constantemente:

**`/var`**.
