# 05. Obtendo ajuda no Linux

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 25 minutos

**Pré-requisitos:**

- Módulo 01 — Fundamentos do Linux
- 01. Conhecendo o Prompt
- 02. Executando comandos no Terminal
- 03. Navegando entre diretórios
- 04. Listando arquivos e diretórios

────────────────────────────────────────────

# Visão Geral

É impossível memorizar todos os comandos e opções disponíveis no Linux.

Mesmo profissionais experientes consultam a documentação diariamente.

A boa notícia é que o próprio Linux oferece ferramentas para encontrar respostas sem precisar sair do Terminal.

Neste capítulo você aprenderá a utilizar essas ferramentas e descobrirá como consultar a documentação oficial dos comandos.

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

- Utilizar o comando `man`.
- Consultar a ajuda rápida de um comando.
- Entender quando utilizar `man` e `--help`.
- Encontrar informações sem depender da internet.

---

# Por que isso é importante?

Imagine um mecânico que conhece todas as ferramentas da oficina, mas nunca consulta o manual de um equipamento novo.

Provavelmente ele cometerá erros desnecessários.

No Linux acontece o mesmo.

Saber onde encontrar ajuda é muito mais importante do que decorar centenas de comandos.

---

# O comando `man`

## O que é?

O comando `man` exibe o manual de um programa ou comando.

Seu nome vem da palavra inglesa:

**Manual**

---

# 📋 Ficha do comando

| Item | Descrição |
|------|-----------|
| **Nome** | `man` |
| **Significado** | Manual |
| **Categoria** | Ajuda |
| **Nível** | Iniciante |
| **Uso diário** | ⭐⭐⭐⭐⭐ |
| **Pode alterar arquivos?** | Não |
| **Requer permissões administrativas?** | Não |

---

# Quando utilizar?

Sempre que você quiser aprender como um comando funciona ou conhecer todas as suas opções.

---

# Exemplo

Digite:

```bash
man ls
```

Será exibido o manual completo do comando `ls`.

---

# Como navegar no manual

Depois de abrir um manual, utilize:

| Tecla | Função |
|--------|--------|
| ↓ | Próxima linha |
| ↑ | Linha anterior |
| Page Down | Próxima página |
| Page Up | Página anterior |
| `/texto` | Pesquisar uma palavra |
| `n` | Próxima ocorrência |
| `q` | Sair do manual |

---

# O parâmetro `--help`

Nem sempre você precisa consultar um manual completo.

Muitos comandos oferecem uma ajuda resumida.

---

# 📋 Ficha do recurso

| Item | Descrição |
|------|-----------|
| **Nome** | `--help` |
| **Categoria** | Ajuda |
| **Nível** | Iniciante |
| **Uso diário** | ⭐⭐⭐⭐⭐ |

---

# Exemplo

Digite:

```bash
ls --help
```

Você verá uma lista resumida das principais opções disponíveis para o comando.

---

# Quando utilizar `man` ou `--help`?

Use `man` quando:

- desejar uma explicação detalhada;
- precisar entender todas as opções;
- quiser consultar exemplos e informações completas.

Use `--help` quando:

- precisar de uma resposta rápida;
- quiser lembrar o nome de uma opção;
- desejar apenas um resumo do comando.

---

# Vamos praticar

Execute:

```bash
man pwd
```

Leia algumas linhas do manual.

Depois pressione:

```text
q
```

para sair.

Agora execute:

```bash
pwd --help
```

Compare os dois resultados.

---

# Explore

Experimente consultar outros comandos estudados:

```bash
man cd
```

```bash
man whoami
```

```bash
man date
```

Caso algum comando não possua manual próprio, observe a mensagem exibida pelo sistema.

---

# Resumo rápido

| Situação | Comando |
|----------|----------|
| Abrir o manual | `man comando` |
| Ajuda rápida | `comando --help` |
| Pesquisar no manual | `/texto` |
| Próxima ocorrência | `n` |
| Sair do manual | `q` |

---

# Erros comuns

- Fechar o Terminal pensando que ficou preso no manual.
- Esquecer de pressionar `q` para sair.
- Confundir `man` com `--help`.

---

# Curiosidade

Grande parte da documentação utilizada por administradores Linux vem diretamente das páginas de manual (`man pages`).

Elas fazem parte da cultura Unix há décadas e continuam sendo uma das principais fontes de consulta para profissionais.

---

# Referências

- GNU Manuals
- Ubuntu Documentation
- Linux Foundation

---

# Conclusão

Neste capítulo você aprendeu a utilizar o comando `man` e o parâmetro `--help` para consultar a documentação dos comandos diretamente pelo Terminal.

Mais importante do que decorar comandos é saber onde encontrar informações confiáveis quando surgir uma dúvida.

Esse hábito tornará seu aprendizado muito mais eficiente.

---

# Prepare-se para o próximo passo

Agora que você sabe encontrar ajuda, chegou o momento de aprender recursos que aumentam sua produtividade no Terminal.

No próximo capítulo conheceremos o histórico de comandos, atalhos de teclado e recursos de autocompletar que tornam o trabalho no Linux muito mais rápido.
