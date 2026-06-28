# 01. Conhecendo o Prompt

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 15 minutos

**Pré-requisitos:**

- Módulo 01 — Fundamentos do Linux

────────────────────────────────────────────

# Visão Geral

Ao abrir o Terminal pela primeira vez, você verá uma linha semelhante a esta:

```text
rafa@ubuntu:~$
```

Para muitas pessoas isso parece apenas um monte de letras e símbolos.

Mas, na realidade, essa pequena linha contém várias informações importantes sobre o sistema.

Ela é chamada de **Prompt**.

Neste capítulo você aprenderá a interpretar cada parte do Prompt e entenderá por que ele é tão importante para quem utiliza Linux.

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

- Entender o que é o Prompt.
- Identificar as informações exibidas nele.
- Saber onde está trabalhando dentro do sistema.
- Compreender por que o Prompt muda conforme você navega pelo Linux.

---

# Por que isso é importante?

Imagine entrar em uma cidade desconhecida sem saber em qual rua você está.

Provavelmente você ficaria perdido.

No Linux acontece algo parecido.

Antes de executar qualquer comando, é importante saber em qual diretório você está trabalhando.

O Prompt fornece exatamente essa informação.

Ele funciona como uma placa de localização.

---

# Conceitos

O Prompt é a linha exibida pelo Terminal indicando que o sistema está pronto para receber um comando.

Sempre que um comando termina sua execução, o Prompt volta a aparecer, aguardando a próxima instrução.

Exemplo:

```text
rafa@ubuntu:~$
```

Cada parte possui um significado.

---

## Usuário

```text
rafa
```

É o usuário atualmente conectado ao sistema.

Caso você utilize outro computador ou outro usuário, esse nome poderá ser diferente.

---

## Computador

```text
ubuntu
```

Depois do símbolo `@` aparece o nome do computador.

Esse nome também é conhecido como **hostname**.

Ele identifica a máquina dentro da rede.

---

## Diretório atual

```text
~
```

Este símbolo representa o diretório pessoal do usuário.

No Linux ele é conhecido como **Home**.

Mais adiante estudaremos a estrutura completa do sistema de arquivos.

---

## Símbolo final

Normalmente veremos um destes símbolos:

```text
$
```

ou

```text
#
```

O símbolo `$` indica um usuário comum.

Já o símbolo `#` normalmente indica que o Terminal está sendo utilizado com privilégios administrativos (usuário **root**).

---

# Como funciona

Sempre que você muda de diretório, o Prompt também muda.

Por exemplo:

Inicialmente:

```text
rafa@ubuntu:~$
```

Após entrar na pasta **Documentos**:

```text
rafa@ubuntu:~/Documentos$
```

O Prompt acompanha sua localização dentro do sistema.

É por isso que ele é uma ferramenta tão importante.

---

# Entenda antes de praticar

Antes de executar qualquer comando, vamos conhecer o primeiro conceito importante.

O comando que utilizaremos neste capítulo será:

```bash
pwd
```

A sigla significa:

> **Print Working Directory**

Em português:

> **Mostrar o diretório atual.**

Sempre que houver dúvida sobre onde você está no sistema, esse comando poderá ajudá-lo.

---

# Pratique

Abra o Terminal.

Digite:

```bash
pwd
```

Depois pressione:

```text
Enter
```

Você verá uma saída semelhante a esta:

```text
/home/rafa
```

O resultado pode ser diferente dependendo do nome do seu usuário.

---

# O que aconteceu?

Quando você executou o comando `pwd`, o Shell solicitou ao sistema operacional a informação sobre o diretório atual.

Depois de exibir essa informação, o Prompt apareceu novamente, indicando que o Terminal está pronto para receber outro comando.

Esse comportamento será observado praticamente durante todo o uso do Terminal.

---

# Explore

Agora execute o mesmo comando mais duas vezes.

Observe que o resultado permanece o mesmo.

Isso acontece porque você ainda não mudou de diretório.

Nos próximos capítulos aprenderemos como navegar pelo sistema e veremos esse resultado mudar.

---

# Erros comuns

- Confundir o Prompt com um comando.
- Pensar que o Prompt faz parte do comando digitado.
- Digitar apenas o símbolo `$`.

Lembre-se:

O símbolo `$` faz parte do Prompt.

Você deve digitar apenas o comando.

Exemplo:

Correto:

```bash
pwd
```

Incorreto:

```bash
$ pwd
```

---

# Dicas para aproveitar melhor este capítulo

Sempre observe o Prompt antes de executar qualquer comando.

Ele informa exatamente onde você está trabalhando.

Esse hábito evita muitos erros durante a utilização do Linux.

---

# Você sabia?

O Prompt pode ser completamente personalizado.

É possível alterar:

- cores;
- formato;
- informações exibidas;
- horário;
- usuário;
- nome da distribuição;
- versão do Git.

Desenvolvedores costumam personalizar bastante o Prompt para facilitar o trabalho diário.

---

# Referências

- GNU Bash Manual

- Ubuntu Documentation

---

# Conclusão

Neste capítulo você conheceu o Prompt do Linux.

Agora você sabe identificar o usuário conectado, o nome do computador e o diretório atual.

Também executou seu primeiro comando consciente no Terminal, entendendo seu significado e a informação retornada.

Esse conhecimento servirá como base para todos os próximos comandos.

---

# Prepare-se para o próximo passo

Agora que você já sabe interpretar o Prompt, chegou o momento de aprender a executar seus primeiros comandos no Terminal.

No próximo capítulo conheceremos comandos simples, mas extremamente úteis, que serão utilizados durante todo o restante da documentação.
