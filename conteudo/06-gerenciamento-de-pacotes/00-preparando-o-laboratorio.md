# Capítulo 00 — Preparando o Laboratório

## 📖 Introdução

Antes de aprender a instalar, atualizar e remover programas, vamos preparar um ambiente adequado para os experimentos deste módulo.

Durante as próximas aulas utilizaremos ferramentas que modificam o sistema operacional, como a instalação de novos pacotes, atualização de repositórios e remoção de softwares.

Embora os comandos apresentados sejam seguros, é uma boa prática realizar os estudos em um ambiente dedicado, evitando impactos em uma máquina utilizada para trabalho ou produção.

Neste capítulo você preparará esse ambiente e verificará se o sistema está pronto para acompanhar os exercícios.

---

# 🎯 Objetivos

Ao concluir este capítulo você será capaz de:

- compreender a importância de um ambiente de testes;
- verificar a versão da distribuição Linux;
- identificar o gerenciador de pacotes utilizado pelo sistema;
- validar a conectividade com a Internet;
- confirmar se possui privilégios administrativos;
- preparar o sistema para os próximos capítulos.

---

# 🧪 Requisitos

Antes de continuar, certifique-se de possuir:

- uma distribuição Linux instalada (Ubuntu ou derivada é recomendada);
- acesso ao Terminal;
- conexão com a Internet;
- um usuário com permissão para utilizar `sudo`.

---

# 🔍 Conhecendo o ambiente

Primeiro, descubra qual distribuição está utilizando.

```bash
cat /etc/os-release
```

Exemplo de saída:

```text
NAME="Ubuntu"
VERSION="24.04 LTS"
ID=ubuntu
```

Essas informações serão úteis durante todo o módulo.

---

# 🔍 Verificando a versão do Kernel

Execute:

```bash
uname -r
```

Exemplo:

```text
6.8.0-64-generic
```

O kernel influencia diretamente na compatibilidade de alguns pacotes.

---

# 🌐 Testando a conexão com a Internet

Grande parte dos pacotes será baixada da Internet.

Verifique a conectividade:

```bash
ping -c 4 google.com
```

Se houver resposta, a conexão está funcionando corretamente.

---

# 👤 Verificando privilégios administrativos

Grande parte das operações deste módulo exigirá permissões administrativas.

Teste o comando:

```bash
sudo -v
```

Caso seja solicitada a senha, informe-a.

Se nenhuma mensagem de erro for exibida, o ambiente está pronto.

---

# 📦 Descobrindo o gerenciador de pacotes

Cada distribuição Linux utiliza um gerenciador de pacotes.

Verifique quais estão disponíveis:

```bash
which apt
```

```bash
which dnf
```

```bash
which yum
```

```bash
which pacman
```

```bash
which zypper
```

O comando que retornar um caminho indica o gerenciador utilizado pelo sistema.

Exemplo:

```text
/usr/bin/apt
```

---

# 📁 Preparando o Linux Explorer Lab

Durante este módulo continuaremos utilizando o ambiente de laboratório criado ao longo do curso.

Caso ainda não exista, crie a pasta do módulo:

```bash
mkdir -p ~/linux-explorer-lab/06-gerenciamento-de-pacotes
```

Entre nela:

```bash
cd ~/linux-explorer-lab/06-gerenciamento-de-pacotes
```

Confira sua localização:

```bash
pwd
```

Resultado esperado:

```text
/home/seu-usuario/linux-explorer-lab/06-gerenciamento-de-pacotes
```

Você poderá utilizar essa pasta para armazenar anotações, listas de pacotes e arquivos utilizados durante os exercícios.

---

# 📝 Informações do ambiente

Antes de iniciar os estudos, registre as informações do seu ambiente.

| Item | Valor |
|------|-------|
| Distribuição | |
| Versão | |
| Kernel | |
| Gerenciador de Pacotes | |
| Usuário | |
| Data do laboratório | |

---

# 💡 Boas práticas

Durante este módulo:

- leia atentamente a saída dos comandos antes de confirmar operações;
- não execute comandos desconhecidos copiados da Internet;
- prefira instalar programas pelos repositórios oficiais;
- mantenha o sistema atualizado;
- utilize privilégios administrativos apenas quando necessário.

---

# ✅ Checklist

Antes de prosseguir, confirme:

- [ ] A distribuição foi identificada.
- [ ] O kernel foi verificado.
- [ ] A conexão com a Internet está funcionando.
- [ ] O comando `sudo` foi validado.
- [ ] O gerenciador de pacotes foi identificado.
- [ ] A pasta do laboratório foi criada.
- [ ] As informações do ambiente foram registradas.

---

# 🎯 Conclusão

Seu ambiente de estudos está preparado para iniciar o módulo de Gerenciamento de Pacotes.

Nos próximos capítulos você aprenderá como os programas são distribuídos nas distribuições Linux, como funcionam os gerenciadores de pacotes e como instalar, atualizar e remover softwares de maneira segura e profissional.
