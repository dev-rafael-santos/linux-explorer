# 06. Histórico e produtividade no Terminal

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 25 minutos

**Pré-requisitos:**

* Módulo 01 — Fundamentos do Linux
* 1. Conhecendo o Prompt
* 2. Executando comandos no Terminal
* 3. Navegando entre diretórios
* 4. Listando arquivos e diretórios
* 5. Obtendo ajuda no Linux

────────────────────────────────────────────

# Visão Geral

Imagine que você acabou de executar um comando muito grande.

Poucos segundos depois, percebe que precisa executá-lo novamente.

Será que é necessário digitá-lo inteiro outra vez?

A resposta é:

**Não.**

O Terminal possui diversos recursos que aumentam sua produtividade e evitam trabalho repetitivo.

Neste capítulo você conhecerá alguns dos mais importantes.

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

* Consultar o histórico de comandos.
* Reutilizar comandos já executados.
* Utilizar o autocompletar com a tecla TAB.
* Limpar a tela do Terminal.
* Conhecer atalhos que aceleram o trabalho.

---

# Por que isso é importante?

Profissionais que trabalham diariamente com Linux não digitam tudo do zero.

Grande parte da produtividade vem do uso inteligente do histórico e dos atalhos do Terminal.

Aprender esses recursos desde o início tornará seu trabalho muito mais rápido.

---

# O comando `history`

## O que é?

O comando `history` exibe uma lista dos comandos executados anteriormente.

---

# 📋 Ficha do comando

| Item                                   | Descrição     |
| -------------------------------------- | ------------- |
| **Nome**                               | `history`     |
| **Categoria**                          | Produtividade |
| **Nível**                              | Iniciante     |
| **Uso diário**                         | ⭐⭐⭐⭐⭐         |
| **Pode alterar arquivos?**             | Não           |
| **Requer permissões administrativas?** | Não           |

---

# Exemplo

Digite:

```bash
history
```

Saída semelhante:

```text
1 pwd
2 ls
3 cd Documentos
4 pwd
5 history
```

Os números representam a ordem em que os comandos foram executados.

---

# Navegando pelo histórico

Em vez de digitar novamente um comando, utilize as teclas:

⬆️ **Seta para cima**

⬇️ **Seta para baixo**

Cada pressionamento percorre o histórico de comandos.

Depois basta pressionar **Enter**.

---

# Autocompletar com TAB

Um dos recursos mais úteis do Terminal é a tecla **TAB**.

Imagine que exista uma pasta chamada:

```text
Documentos
```

Em vez de digitar:

```bash
cd Documentos
```

Digite apenas:

```bash
cd Doc
```

Agora pressione:

```text
TAB
```

O Bash completará automaticamente o restante do nome, quando possível.

---

# Limpando a tela

Você já conheceu o comando:

```bash
clear
```

Ele limpa a tela do Terminal.

Existe também um atalho equivalente:

```text
Ctrl + L
```

Ambos produzem o mesmo resultado.

---

# Cancelando um comando

Caso um comando esteja demorando muito para terminar ou tenha sido iniciado por engano, pressione:

```text
Ctrl + C
```

Esse atalho interrompe a execução do comando atual.

É um dos atalhos mais importantes do Terminal.

---

# Vamos praticar

Execute:

```bash
pwd
```

Depois:

```bash
ls
```

Agora:

```bash
history
```

Utilize a seta para cima algumas vezes.

Observe os comandos reaparecendo no Prompt.

Depois pressione **TAB** para completar o nome de um diretório.

Por fim, utilize:

```text
Ctrl + L
```

para limpar a tela.

---

# Explore

Abra uma pasta utilizando:

```bash
cd
```

Depois execute:

```bash
ls
```

Agora pressione várias vezes a seta para cima.

Observe como você consegue reutilizar comandos sem precisar digitá-los novamente.

Experimente também utilizar a tecla TAB para completar nomes de diretórios e arquivos.

---

# Resumo rápido

| Situação                 | Recurso               |
| ------------------------ | --------------------- |
| Ver histórico            | `history`             |
| Repetir comando anterior | ↑                     |
| Avançar no histórico     | ↓                     |
| Completar nomes          | `TAB`                 |
| Limpar tela              | `clear` ou `Ctrl + L` |
| Cancelar comando         | `Ctrl + C`            |

---

# Erros comuns

* Digitar novamente comandos que já estão no histórico.
* Não utilizar o autocompletar.
* Pensar que `clear` apaga o histórico.

O comando apenas limpa a tela.

O histórico continua disponível.

---

# Curiosidade

O Bash mantém um arquivo com o histórico de comandos do usuário.

Esse arquivo normalmente é:

```text
~/.bash_history
```

Mais adiante aprenderemos como visualizar esse arquivo.

---

# Referências

* GNU Bash Manual
* Ubuntu Documentation

---

# Conclusão

Neste capítulo você conheceu recursos que aumentam significativamente a produtividade no Terminal.

Aprendeu a reutilizar comandos, completar nomes automaticamente, limpar a tela e interromper comandos em execução.

Esses recursos fazem parte da rotina diária de praticamente todo profissional que utiliza Linux.

---

# Prepare-se para o próximo passo

Você já conhece os principais comandos básicos do Terminal.

No próximo capítulo aprenderá a combinar comandos e compreenderá como eles podem trabalhar juntos para realizar tarefas mais eficientes.
