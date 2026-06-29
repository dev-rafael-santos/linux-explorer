# Capítulo 04 — Atualizando o Sistema

## 📖 Introdução

Manter um sistema Linux atualizado é uma das tarefas mais importantes de qualquer administrador.

As atualizações não servem apenas para adicionar novos recursos. Elas também corrigem vulnerabilidades de segurança, resolvem problemas de estabilidade e melhoram o desempenho dos programas instalados.

Neste capítulo você aprenderá como funciona o processo de atualização e quais comandos utilizar para manter seu sistema sempre em boas condições.

---

# 🎯 Objetivos

Ao concluir este capítulo você será capaz de:

- compreender a diferença entre atualizar a lista de pacotes e atualizar programas;
- atualizar o sistema de forma segura;
- remover pacotes desnecessários;
- entender boas práticas de atualização;
- identificar riscos durante o processo.

---

# 🤔 Como funciona uma atualização?

Antes de instalar novas versões de programas, o gerenciador de pacotes precisa consultar os repositórios para descobrir quais atualizações estão disponíveis.

O processo normalmente acontece em duas etapas:

```text
Atualizar lista de pacotes
          │
          ▼
Atualizar os programas instalados
```

Essa separação evita que o sistema tente instalar versões desatualizadas.

---

# Atualizando a lista de pacotes

Execute:

```bash
sudo apt update
```

Esse comando **não instala nenhuma atualização**.

Ele apenas sincroniza a lista de pacotes disponíveis com os repositórios configurados.

---

# Atualizando os programas

Depois da atualização da lista, execute:

```bash
sudo apt upgrade
```

Agora sim os pacotes instalados serão atualizados para suas versões mais recentes.

Durante o processo, o sistema poderá solicitar confirmação.

---

# Atualizando tudo automaticamente

Em alguns casos é necessário permitir que novos pacotes sejam instalados ou antigos sejam removidos.

Para isso existe:

```bash
sudo apt full-upgrade
```

Esse comando realiza uma atualização mais completa.

Utilize-o com atenção.

---

# Limpando pacotes desnecessários

Após diversas atualizações, algumas dependências deixam de ser utilizadas.

Para removê-las:

```bash
sudo apt autoremove
```

Também é possível limpar o cache de pacotes baixados:

```bash
sudo apt clean
```

Esses comandos ajudam a manter o sistema organizado.

---

# Fluxo recomendado

Na prática, um administrador costuma seguir esta sequência:

```bash
sudo apt update

sudo apt upgrade

sudo apt autoremove

sudo apt clean
```

Esse fluxo mantém o sistema atualizado e remove arquivos desnecessários.

---

# Comparando com outros gerenciadores

| Ação | APT | DNF | Pacman |
|------|-----|-----|---------|
| Atualizar lista | `apt update` | `dnf check-update` | `pacman -Sy` |
| Atualizar sistema | `apt upgrade` | `dnf upgrade` | `pacman -Syu` |

Embora os comandos sejam diferentes, o objetivo é o mesmo.

---

# 💼 Aplicação no mercado

Atualizações fazem parte da rotina de qualquer administrador Linux.

Elas são utilizadas para:

- corrigir falhas de segurança;
- atualizar servidores;
- instalar novas versões de bibliotecas;
- manter aplicações compatíveis;
- reduzir riscos de ataques.

Em ambientes corporativos, atualizações normalmente seguem um processo controlado, com testes antes da implantação em produção.

---

# ⚠️ Erros comuns

Evite:

- desligar o computador durante uma atualização;
- executar `apt upgrade` sem antes utilizar `apt update`;
- instalar atualizações sem verificar mensagens de erro;
- atualizar servidores de produção sem planejamento.

---

# 🧪 Laboratório

Atualize apenas a lista de pacotes:

```bash
sudo apt update
```

Observe:

- quantidade de repositórios consultados;
- velocidade da sincronização;
- mensagens exibidas.

Depois verifique quais pacotes possuem atualização disponível:

```bash
apt list --upgradable
```

Caso existam atualizações, apenas observe a lista.

Neste momento não é obrigatório instalá-las.

---

# 🧠 Você consegue explicar?

Sem consultar o material, tente responder:

1. Qual a diferença entre `apt update` e `apt upgrade`?
2. Quando utilizar `full-upgrade`?
3. Para que serve `autoremove`?
4. O que faz o comando `clean`?

Se conseguir responder essas perguntas, você compreendeu o processo de atualização do sistema.

---

# 📝 Resumo

Neste capítulo você aprendeu que:

- `apt update` sincroniza a lista de pacotes;
- `apt upgrade` instala as atualizações disponíveis;
- `full-upgrade` realiza uma atualização mais completa;
- `autoremove` remove dependências desnecessárias;
- `clean` limpa o cache de pacotes.

No próximo capítulo você aprenderá como funcionam os repositórios de software, de onde os pacotes são obtidos e por que eles são essenciais para a segurança e manutenção do sistema.
