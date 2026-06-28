# 02. Executando comandos no Terminal

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 20 minutos

**Pré-requisitos:**

* Módulo 01 — Fundamentos do Linux
* 1. Conhecendo o Prompt

────────────────────────────────────────────

# Visão Geral

No capítulo anterior você conheceu o Prompt e executou seu primeiro comando.

Agora chegou o momento de entender como o Linux executa os comandos digitados no Terminal.

Embora existam centenas de comandos disponíveis, todos seguem exatamente o mesmo fluxo de execução.

Compreender esse processo será muito mais importante do que decorar comandos.

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

* Entender como um comando é executado.
* Conhecer a estrutura básica de um comando.
* Executar comandos simples.
* Interpretar a resposta apresentada pelo Terminal.

---

# Por que isso é importante?

Imagine aprender a dirigir decorando apenas o nome dos pedais.

Você conheceria os componentes do carro, mas não saberia dirigir.

Com Linux acontece a mesma coisa.

Nosso objetivo é compreender como os comandos funcionam.

Depois disso, aprender novos comandos será muito mais fácil.

---

# Como o Linux executa um comando?

Sempre que você digita um comando e pressiona **Enter**, acontece a seguinte sequência:

```text
Você
 │
 ▼
Digita um comando
 │
 ▼
Pressiona Enter
 │
 ▼
O Shell interpreta o comando
 │
 ▼
O Kernel executa a solicitação
 │
 ▼
O resultado é exibido
 │
 ▼
O Prompt retorna
```

Esse fluxo acontece praticamente para todos os comandos utilizados no Linux.

---

# Estrutura básica de um comando

A maioria dos comandos segue este padrão:

```text
comando [opções] [argumentos]
```

Exemplo:

```bash
ls -l Documentos
```

Neste capítulo utilizaremos apenas comandos simples, sem opções ou argumentos.

Mais adiante aprenderemos cada uma dessas partes.

---

# Comando 1 — pwd

## O que é?

O comando `pwd` mostra o diretório onde você está trabalhando no momento.

Seu nome vem da expressão em inglês:

**Print Working Directory**

---

## 📋 Ficha do comando

| Item                                   | Descrição               |
| -------------------------------------- | ----------------------- |
| **Nome**                               | `pwd`                   |
| **Significado**                        | Print Working Directory |
| **Categoria**                          | Navegação               |
| **Nível**                              | Iniciante               |
| **Uso diário**                         | ⭐⭐⭐⭐⭐                   |
| **Pode alterar arquivos?**             | Não                     |
| **Requer permissões administrativas?** | Não                     |

---

## Quando utilizar?

Sempre que você quiser descobrir onde está dentro do sistema de arquivos.

É um dos comandos mais utilizados no Linux.

---

## Exemplo

Digite:

```bash
pwd
```

Saída esperada:

```text
/home/rafa
```

O resultado pode variar de acordo com o nome do seu usuário.

---

## O que aconteceu?

O Shell solicitou ao Kernel o diretório atual.

Depois de exibir o resultado, o Prompt voltou a aparecer, indicando que o Terminal está pronto para receber outro comando.

---

# Comando 2 — whoami

## O que é?

O comando `whoami` informa qual usuário está utilizando o sistema.

Seu nome significa:

**Who am I**

("Quem sou eu?")

---

## 📋 Ficha do comando

| Item                                   | Descrição |
| -------------------------------------- | --------- |
| **Nome**                               | `whoami`  |
| **Significado**                        | Who am I  |
| **Categoria**                          | Usuário   |
| **Nível**                              | Iniciante |
| **Uso diário**                         | ⭐⭐⭐⭐☆     |
| **Pode alterar arquivos?**             | Não       |
| **Requer permissões administrativas?** | Não       |

---

## Quando utilizar?

Sempre que houver dúvida sobre qual usuário está autenticado no sistema.

---

## Exemplo

Digite:

```bash
whoami
```

Saída esperada:

```text
rafa
```

---

# Comando 3 — date

## O que é?

O comando `date` mostra a data e a hora atuais do sistema.

---

## 📋 Ficha do comando

| Item                                   | Descrição |
| -------------------------------------- | --------- |
| **Nome**                               | `date`    |
| **Categoria**                          | Sistema   |
| **Nível**                              | Iniciante |
| **Uso diário**                         | ⭐⭐⭐☆☆     |
| **Pode alterar arquivos?**             | Não       |
| **Requer permissões administrativas?** | Não       |

---

## Exemplo

Digite:

```bash
date
```

Saída semelhante:

```text
Wed Jul 30 21:30:45 BRT 2025
```

---

# Vamos praticar

Execute os três comandos:

```bash
pwd
```

```bash
whoami
```

```bash
date
```

Observe:

* cada comando produz uma resposta diferente;
* o Prompt desaparece durante a execução;
* o Prompt retorna quando o comando termina.

Esse comportamento será observado durante praticamente toda a utilização do Linux.

---

# Explore

Agora execute um comando inexistente:

```bash
abcd
```

O Terminal responderá algo semelhante a:

```text
Command 'abcd' not found
```

Isso significa que o Shell tentou localizar esse comando, mas não encontrou nenhum programa com esse nome.

Aprender a interpretar mensagens de erro faz parte do trabalho de qualquer usuário Linux.

---

# Erros comuns

* Esquecer de pressionar **Enter**.
* Escrever o comando com letras maiúsculas.
* Digitar o nome do comando incorretamente.
* Confundir o Prompt com a saída do comando.

---

# Curiosidade

Você percebeu que todos os comandos executados até agora apenas consultaram informações?

Nenhum deles alterou arquivos ou modificou o sistema.

Isso foi proposital.

Antes de aprender comandos que modificam o computador, é importante ganhar confiança utilizando comandos seguros.

---

# Referências

* GNU Bash Manual
* Ubuntu Documentation
* Linux Foundation

---

# Conclusão

Neste capítulo você aprendeu como o Linux executa comandos e conheceu três comandos fundamentais para consultar informações do sistema.

Mais importante do que memorizar esses comandos foi compreender o processo de execução realizado pelo Shell e pelo Kernel.

Esse conhecimento será utilizado em todos os próximos capítulos.

---

# Prepare-se para o próximo passo

Agora que você já sabe executar comandos, chegou o momento de aprender uma das habilidades mais importantes no Linux:

**navegar entre diretórios utilizando o comando `cd`.**
