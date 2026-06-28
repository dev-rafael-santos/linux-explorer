# 04. Listando arquivos e diretórios

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 25 minutos

**Pré-requisitos:**

* Módulo 01 — Fundamentos do Linux
* 1. Conhecendo o Prompt
* 2. Executando comandos no Terminal
* 3. Navegando entre diretórios

────────────────────────────────────────────

# Visão Geral

Imagine que você acabou de entrar em uma pasta utilizando o comando `cd`.

Agora surge uma nova pergunta:

> **Quais arquivos e pastas existem aqui?**

É exatamente para isso que serve o comando `ls`.

Ele permite listar o conteúdo de um diretório e é um dos comandos mais utilizados por quem trabalha com Linux.

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

* Utilizar o comando `ls`.
* Listar arquivos e diretórios.
* Entender algumas opções muito utilizadas.
* Interpretar a saída apresentada pelo comando.

---

# Por que isso é importante?

Sempre que você entra em um diretório, normalmente deseja saber quais arquivos estão disponíveis.

O comando `ls` será utilizado constantemente durante toda a sua jornada com Linux.

É um dos comandos fundamentais para navegar pelo sistema.

---

# O comando `ls`

O comando `ls` significa:

> **List**

Em português:

> **Listar**.

Sua função é mostrar o conteúdo de um diretório.

---

# 📋 Ficha do comando

| Item                                   | Descrição |
| -------------------------------------- | --------- |
| **Nome**                               | `ls`      |
| **Significado**                        | List      |
| **Categoria**                          | Navegação |
| **Nível**                              | Iniciante |
| **Uso diário**                         | ⭐⭐⭐⭐⭐     |
| **Pode alterar arquivos?**             | Não       |
| **Requer permissões administrativas?** | Não       |

---

# Como funciona?

Digite:

```bash
ls
```

O Terminal exibirá todos os arquivos e diretórios presentes no diretório atual.

Exemplo:

```text
Documentos  Downloads  Imagens  Música  Vídeos
```

O conteúdo será diferente em cada computador.

---

# Opção `-l`

Uma das opções mais utilizadas é:

```bash
ls -l
```

Ela exibe informações detalhadas sobre cada arquivo.

Exemplo:

```text
drwxr-xr-x  2 rafa rafa 4096 Jul 31 10:20 Documentos
```

Neste momento, não se preocupe em entender todas as colunas.

Elas serão estudadas quando aprendermos permissões e gerenciamento de arquivos.

---

# Opção `-a`

Por padrão, o Linux oculta arquivos que começam com um ponto (`.`).

Para visualizá-los, utilize:

```bash
ls -a
```

Você verá arquivos como:

```text
.bashrc
.profile
.cache
```

Esses arquivos normalmente armazenam configurações do sistema ou do usuário.

---

# Combinando opções

Você pode utilizar mais de uma opção ao mesmo tempo.

Exemplo:

```bash
ls -la
```

ou

```bash
ls -al
```

O resultado será uma listagem detalhada, incluindo arquivos ocultos.

---

# Vamos praticar

Execute os seguintes comandos:

```bash
ls
```

Depois:

```bash
ls -l
```

Depois:

```bash
ls -a
```

E por fim:

```bash
ls -la
```

Compare os resultados.

Observe como cada opção altera a forma como as informações são apresentadas.

---

# Explore

Entre em outro diretório utilizando o comando `cd`.

Depois execute novamente:

```bash
ls
```

O resultado será diferente.

Isso acontece porque cada diretório possui seu próprio conteúdo.

Experimente navegar por:

* Documentos
* Downloads
* Imagens

Observe as diferenças.

---

# Resumo rápido do comando

| Situação                                | Comando  |
| --------------------------------------- | -------- |
| Listar conteúdo                         | `ls`     |
| Listagem detalhada                      | `ls -l`  |
| Mostrar arquivos ocultos                | `ls -a`  |
| Listagem detalhada com arquivos ocultos | `ls -la` |

---

# Erros comuns

* Esquecer que `ls` mostra apenas o diretório atual.
* Confundir arquivos ocultos com arquivos inexistentes.
* Pensar que `ls` altera arquivos.

O comando apenas consulta informações.

---

# Curiosidade

Arquivos iniciados com um ponto (`.`) são chamados de **arquivos ocultos**.

Eles normalmente armazenam configurações do sistema ou de aplicações.

Por exemplo:

```text
.bashrc
```

é um dos arquivos responsáveis por configurar o Bash.

Mais adiante aprenderemos a utilizá-lo.

---

# Referências

* GNU Coreutils Manual
* Ubuntu Documentation

---

# Conclusão

Neste capítulo você aprendeu a utilizar o comando `ls` para listar arquivos e diretórios.

Também conheceu algumas das opções mais utilizadas (`-l`, `-a` e `-la`), que serão empregadas frequentemente ao longo desta documentação.

Dominar esse comando facilitará bastante a navegação pelo sistema.

---

# Prepare-se para o próximo passo

Agora que você já sabe navegar e listar arquivos, chegou o momento de aprender onde encontrar ajuda quando surgir uma dúvida.

No próximo capítulo você conhecerá os comandos `man`, `--help` e `info`, aprendendo a consultar a documentação oficial diretamente pelo Terminal.
