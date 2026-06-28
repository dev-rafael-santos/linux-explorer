# 03. Navegando entre diretórios

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 25 minutos

**Pré-requisitos:**

* Módulo 01 — Fundamentos do Linux
* 1. Conhecendo o Prompt
* 2. Executando comandos no Terminal

────────────────────────────────────────────

# Visão Geral

Imagine que você acabou de abrir o Terminal e precisa acessar a pasta **Documentos** para editar um arquivo.

Como chegar até ela?

No Linux, navegar entre diretórios é uma das tarefas mais comuns do dia a dia.

Neste capítulo você aprenderá como mudar de diretório utilizando o comando `cd` e entenderá a diferença entre caminhos absolutos e relativos.

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

* Navegar entre diretórios.
* Utilizar o comando `cd`.
* Entender caminhos absolutos e relativos.
* Voltar para o diretório anterior.
* Retornar rapidamente ao diretório pessoal.

---

# Por que isso é importante?

Imagine entrar em uma biblioteca enorme sem saber em qual corredor está.

Antes de procurar um livro, você precisa saber onde está e para onde deseja ir.

No Linux acontece exatamente a mesma coisa.

Antes de criar, editar ou remover arquivos, é importante saber navegar pelo sistema de arquivos.

---

# O comando `cd`

O comando `cd` significa:

> **Change Directory**

Em português:

> **Alterar diretório.**

Ele é utilizado para mudar o diretório de trabalho do Terminal.

---

# 📋 Ficha do comando

| Item                                   | Descrição        |
| -------------------------------------- | ---------------- |
| **Nome**                               | `cd`             |
| **Significado**                        | Change Directory |
| **Categoria**                          | Navegação        |
| **Nível**                              | Iniciante        |
| **Uso diário**                         | ⭐⭐⭐⭐⭐            |
| **Pode alterar arquivos?**             | Não              |
| **Requer permissões administrativas?** | Não              |

---

# Como funciona?

Sempre que você executa o comando `cd`, o Terminal passa a trabalhar em outro diretório.

Você pode confirmar isso utilizando o comando `pwd`.

Exemplo:

```bash
pwd
```

Saída:

```text
/home/rafa
```

Agora execute:

```bash
cd Documentos
```

Depois execute novamente:

```bash
pwd
```

Saída:

```text
/home/rafa/Documentos
```

Observe que apenas o diretório mudou.

---

# Caminhos absolutos

Um caminho absoluto informa o endereço completo de um diretório.

Exemplo:

```text
/home/rafa/Documentos
```

Independentemente de onde você estiver, esse caminho sempre aponta para o mesmo lugar.

Exemplo:

```bash
cd /home/rafa/Documentos
```

---

# Caminhos relativos

Um caminho relativo depende do diretório onde você está.

Se você estiver em:

```text
/home/rafa
```

Basta executar:

```bash
cd Documentos
```

O Linux entende que a pasta **Documentos** está dentro do diretório atual.

---

# Atalhos importantes

## Voltar para o diretório pessoal

```bash
cd
```

ou

```bash
cd ~
```

O símbolo `~` representa o diretório pessoal do usuário.

---

## Voltar um nível

```bash
cd ..
```

Os dois pontos (`..`) representam o diretório pai.

Exemplo:

```text
/home/rafa/Documentos
```

Após executar:

```bash
cd ..
```

Você estará em:

```text
/home/rafa
```

---

## Permanecer no diretório atual

```bash
cd .
```

O ponto (`.`) representa o diretório atual.

Na prática, esse comando raramente é utilizado sozinho, mas você o verá com frequência em outros comandos.

---

# Vamos praticar

Execute os comandos abaixo exatamente nesta ordem:

```bash
pwd
```

```bash
cd Documentos
```

```bash
pwd
```

```bash
cd ..
```

```bash
pwd
```

```bash
cd
```

```bash
pwd
```

Observe como o resultado muda após cada navegação.

---

# Explore

Tente acessar um diretório que não existe:

```bash
cd pasta_inexistente
```

O Terminal exibirá uma mensagem semelhante a:

```text
bash: cd: pasta_inexistente: No such file or directory
```

Leia essa mensagem com atenção.

Ela informa exatamente o motivo do erro.

Aprender a interpretar essas mensagens é uma habilidade essencial para trabalhar com Linux.

---

# Erros comuns

* Esquecer de verificar o diretório atual antes de navegar.
* Confundir caminhos absolutos com caminhos relativos.
* Digitar nomes de diretórios com letras maiúsculas ou minúsculas diferentes.

Lembre-se: o Linux diferencia letras maiúsculas de minúsculas.

`Documentos` e `documentos` podem representar diretórios diferentes.

---

# Curiosidade

O comando `cd` é um dos poucos comandos internos do Shell.

Isso significa que ele não é um programa separado executado pelo sistema.

Ele faz parte do próprio Bash, pois precisa alterar o diretório do processo atual.

---

# Referências

* GNU Bash Manual
* Ubuntu Documentation

---

# Conclusão

Neste capítulo você aprendeu a navegar entre diretórios utilizando o comando `cd`.

Também conheceu os conceitos de caminho absoluto, caminho relativo e alguns atalhos importantes que serão utilizados constantemente nos próximos módulos.

Dominar o comando `cd` é um passo importante para trabalhar com eficiência no Terminal.

---

# Prepare-se para o próximo passo

Agora que você já sabe se mover pelo sistema de arquivos, chegou o momento de descobrir como visualizar o conteúdo de um diretório.

No próximo capítulo aprenderemos o comando `ls` e suas opções mais utilizadas para listar arquivos e pastas.

