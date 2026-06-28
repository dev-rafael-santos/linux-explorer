# 07. Executando múltiplos comandos

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 25 minutos

**Pré-requisitos:**

- Módulo 01 — Fundamentos do Linux
- Todos os capítulos anteriores deste módulo

────────────────────────────────────────────

# Visão Geral

Até aqui você executou um comando por vez.

Mas imagine que você queira:

1. Descobrir onde está.
2. Listar os arquivos do diretório.
3. Ver a data do sistema.

Seria necessário executar três comandos separados?

Sim.

Mas existe uma forma mais prática de pedir isso ao Terminal.

Neste capítulo você aprenderá como executar vários comandos em sequência.

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

- Executar vários comandos em sequência.
- Entender a diferença entre `;`, `&&` e `||`.
- Saber quando utilizar cada operador.
- Compreender a ordem de execução dos comandos.

---

# Por que isso é importante?

Durante o trabalho diário é comum executar diversos comandos relacionados.

Saber organizá-los economiza tempo e torna o Terminal mais eficiente.

---

# Executando comandos em sequência

## Operador `;`

O ponto e vírgula permite executar vários comandos, um após o outro.

Independentemente de um comando falhar ou não, o próximo será executado.

---

## 📋 Ficha

| Item | Descrição |
|------|-----------|
| **Operador** | `;` |
| **Categoria** | Execução |
| **Nível** | Iniciante |
| **Uso diário** | ⭐⭐⭐⭐☆ |

---

## Exemplo

```bash
pwd ; ls ; date
```

O Terminal executará:

1. `pwd`
2. `ls`
3. `date`

Sempre nessa ordem.

---

# Operador `&&`

O operador `&&` significa:

> Execute o próximo comando **somente se o anterior tiver sido executado com sucesso**.

---

## 📋 Ficha

| Item | Descrição |
|------|-----------|
| **Operador** | `&&` |
| **Categoria** | Execução Condicional |
| **Nível** | Iniciante |
| **Uso diário** | ⭐⭐⭐⭐⭐ |

---

## Exemplo

```bash
cd Documentos && ls
```

Se o diretório existir:

- o comando `cd` será executado;
- em seguida o `ls` mostrará seu conteúdo.

Caso contrário, o `ls` não será executado.

---

# Operador `||`

O operador `||` significa:

> Execute o próximo comando apenas se o anterior falhar.

---

## 📋 Ficha

| Item | Descrição |
|------|-----------|
| **Operador** | `||` |
| **Categoria** | Execução Condicional |
| **Nível** | Iniciante |
| **Uso diário** | ⭐⭐⭐☆☆ |

---

## Exemplo

```bash
cd PastaInexistente || echo "Diretório não encontrado"
```

Como a pasta não existe, o Terminal exibirá:

```text
Diretório não encontrado
```

---

# Comparando os operadores

| Operador | O que faz? |
|----------|------------|
| `;` | Executa todos os comandos. |
| `&&` | Executa o próximo apenas se o anterior funcionar. |
| `||` | Executa o próximo apenas se o anterior falhar. |

---

# Vamos praticar

Execute:

```bash
pwd ; ls ; date
```

Depois:

```bash
cd Documentos && pwd
```

Agora:

```bash
cd PastaInexistente || echo "Não foi possível acessar o diretório."
```

Observe cuidadosamente o comportamento de cada operador.

---

# Explore

Experimente alterar a ordem dos comandos.

Por exemplo:

```bash
date ; pwd ; ls
```

Depois tente:

```bash
pwd && ls && whoami
```

Perceba como o Terminal executa os comandos exatamente na ordem em que foram escritos.

---

# Resumo rápido

| Situação | Operador |
|----------|----------|
| Executar tudo | `;` |
| Executar somente em caso de sucesso | `&&` |
| Executar somente em caso de erro | `||` |

---

# Erros comuns

- Pensar que `&&` sempre executa o segundo comando.
- Confundir `;` com `&&`.
- Esquecer que `||` depende de um erro no comando anterior.

---

# Curiosidade

Esses operadores são muito utilizados em scripts Bash e em automações.

Você os verá com frequência em tutoriais, documentação e pipelines de integração contínua (CI/CD).

---

# Referências

- GNU Bash Manual
- Ubuntu Documentation

---

# Conclusão

Neste capítulo você aprendeu três formas de executar comandos em sequência.

Também compreendeu que alguns operadores dependem do sucesso ou da falha do comando anterior.

Esse conhecimento será muito útil quando começarmos a escrever scripts Bash.

---

# Prepare-se para o próximo passo

🎉 Parabéns!

Você concluiu o Módulo 02 — Terminal.

Agora já é capaz de:

- interpretar o Prompt;
- executar comandos;
- navegar entre diretórios;
- listar arquivos;
- consultar a documentação;
- utilizar atalhos de produtividade;
- executar comandos em sequência.

No próximo módulo começaremos a explorar a estrutura do sistema de arquivos Linux, entendendo a função dos principais diretórios do sistema.
