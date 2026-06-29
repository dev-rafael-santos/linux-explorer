# Capítulo 03 — Instalando e Removendo Pacotes

## 📖 Introdução

Agora que você já compreende o que são pacotes e conhece os principais gerenciadores utilizados pelas distribuições Linux, chegou o momento de aprender como instalar e remover softwares.

Neste capítulo utilizaremos o **APT**, gerenciador de pacotes presente nas distribuições baseadas em Debian, como Ubuntu e Linux Mint.

Mesmo que você utilize outra distribuição, os conceitos apresentados aqui continuam válidos. O que muda é apenas a sintaxe dos comandos.

---

# 🎯 Objetivos

Ao concluir este capítulo você será capaz de:

- pesquisar pacotes disponíveis;
- instalar programas;
- remover programas;
- remover dependências não utilizadas;
- consultar informações sobre um pacote;
- listar pacotes instalados.

---

# Como pesquisar um pacote

Antes de instalar um programa, normalmente pesquisamos sua disponibilidade.

Utilize:

```bash
apt search nome-do-pacote
```

Exemplo:

```bash
apt search vlc
```

O sistema exibirá todos os pacotes relacionados ao termo pesquisado.

---

# Como obter informações sobre um pacote

Caso queira conhecer um pacote antes da instalação:

```bash
apt show nome-do-pacote
```

Exemplo:

```bash
apt show git
```

Entre as informações exibidas estão:

- versão;
- descrição;
- dependências;
- tamanho;
- mantenedor.

---

# Instalando um pacote

Para instalar um programa:

```bash
sudo apt install nome-do-pacote
```

Exemplo:

```bash
sudo apt install git
```

Durante a instalação o APT poderá solicitar confirmação.

Digite:

```text
Y
```

ou

```text
S
```

dependendo do idioma configurado.

---

# Instalando vários pacotes

Também é possível instalar diversos programas de uma única vez.

Exemplo:

```bash
sudo apt install git curl wget
```

O APT resolverá automaticamente as dependências necessárias.

---

# Listando pacotes instalados

Para verificar os pacotes já instalados:

```bash
apt list --installed
```

Caso deseje localizar um programa específico:

```bash
apt list --installed | grep git
```

---

# Removendo um pacote

Para remover um software:

```bash
sudo apt remove nome-do-pacote
```

Exemplo:

```bash
sudo apt remove git
```

Essa operação remove o programa, mas preserva arquivos de configuração.

---

# Removendo completamente

Caso queira remover também os arquivos de configuração:

```bash
sudo apt purge nome-do-pacote
```

Exemplo:

```bash
sudo apt purge git
```

---

# Limpando dependências desnecessárias

Após remover programas, algumas bibliotecas podem deixar de ser utilizadas.

Para removê-las:

```bash
sudo apt autoremove
```

Esse comando ajuda a manter o sistema limpo.

---

# A sequência mais comum

Na prática, administradores Linux costumam seguir este fluxo:

```text
Pesquisar
      │
      ▼
Obter informações
      │
      ▼
Instalar
      │
      ▼
Utilizar
      │
      ▼
Remover (quando necessário)
      │
      ▼
Executar autoremove
```

---

# Comparando com outros gerenciadores

Embora a sintaxe seja diferente, a ideia permanece a mesma.

| Ação | APT | DNF | Pacman |
|------|-----|-----|---------|
| Pesquisar | `apt search` | `dnf search` | `pacman -Ss` |
| Instalar | `apt install` | `dnf install` | `pacman -S` |
| Remover | `apt remove` | `dnf remove` | `pacman -R` |

O conceito é praticamente idêntico.

---

# 💼 Aplicação no mercado

Esses comandos fazem parte da rotina de administradores Linux.

São utilizados diariamente para:

- instalar ferramentas de desenvolvimento;
- configurar servidores;
- instalar bancos de dados;
- atualizar ambientes de produção;
- remover softwares obsoletos.

Dominar essas operações é uma habilidade essencial para qualquer profissional que trabalhe com Linux.

---

# ⚠️ Erros comuns

Evite:

- instalar programas sem verificar sua origem;
- remover pacotes importantes sem entender suas dependências;
- utilizar `sudo` sem necessidade;
- interromper instalações em andamento.

---

# 🧪 Laboratório

Pesquise três programas disponíveis no repositório:

```bash
apt search git

apt search curl

apt search htop
```

Escolha um programa simples e visualize suas informações:

```bash
apt show htop
```

Depois liste os pacotes instalados:

```bash
apt list --installed | grep htop
```

Caso o pacote esteja instalado, observe as informações apresentadas.

> **Observação:** neste capítulo o objetivo é aprender os comandos. A instalação e remoção de programas será praticada de forma mais aprofundada nos próximos capítulos.

---

# 🧠 Você consegue explicar?

Sem consultar o material, tente responder:

1. Qual a diferença entre `apt search` e `apt show`?
2. Quando utilizar `remove` e quando utilizar `purge`?
3. Para que serve o `autoremove`?
4. Por que o APT instala dependências automaticamente?

Se conseguir responder essas perguntas, você assimilou os conceitos mais importantes deste capítulo.

---

# 📝 Resumo

Neste capítulo você aprendeu a:

- pesquisar pacotes;
- consultar informações;
- instalar programas;
- remover programas;
- remover arquivos de configuração;
- limpar dependências não utilizadas.

No próximo capítulo você aprenderá como manter o sistema atualizado de forma segura e compreenderá por que atualizar um sistema Linux vai muito além de instalar novas versões de programas.
