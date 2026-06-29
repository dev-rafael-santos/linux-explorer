# Capítulo 08 — Desafio Prático

## 📖 Cenário

Parabéns!

Você acaba de ser contratado como Analista de Infraestrutura Linux em uma empresa de desenvolvimento de software.

Sua primeira tarefa é preparar uma estação de trabalho para um novo desenvolvedor.

Antes de instalar as ferramentas necessárias, você deverá verificar o ambiente, atualizar o sistema, pesquisar pacotes e instalar alguns programas utilizados pela equipe.

Todo o procedimento deve seguir as boas práticas aprendidas neste módulo.

---

# 🎯 Objetivos

Neste desafio você deverá:

- identificar a distribuição Linux;
- identificar o gerenciador de pacotes;
- atualizar o sistema;
- pesquisar softwares;
- instalar aplicações;
- remover um programa;
- limpar dependências desnecessárias;
- verificar as versões instaladas.

---

# 📋 Missão 01 — Conhecendo o ambiente

Descubra qual distribuição está sendo utilizada.

```bash
cat /etc/os-release
```

Verifique também o Kernel.

```bash
uname -r
```

Descubra qual gerenciador de pacotes existe na máquina.

```bash
which apt
```

---

# 📋 Missão 02 — Atualizando o sistema

Atualize a lista de pacotes.

```bash
sudo apt update
```

Atualize os programas instalados.

```bash
sudo apt upgrade
```

---

# 📋 Missão 03 — Pesquisando softwares

Pesquise os seguintes programas:

- git
- curl
- htop

Exemplo:

```bash
apt search git
```

Visualize as informações de um deles.

```bash
apt show git
```

---

# 📋 Missão 04 — Instalando programas

Instale os seguintes pacotes:

```text
git
curl
htop
```

Utilize:

```bash
sudo apt install git curl htop
```

Após a instalação, confirme:

```bash
git --version

curl --version

htop --version
```

---

# 📋 Missão 05 — Removendo um programa

Remova o pacote:

```text
htop
```

```bash
sudo apt remove htop
```

Agora remova possíveis dependências não utilizadas.

```bash
sudo apt autoremove
```

---

# 📋 Missão 06 — Explorando os repositórios

Visualize os repositórios configurados.

```bash
cat /etc/apt/sources.list
```

Liste os arquivos adicionais.

```bash
ls /etc/apt/sources.list.d
```

---

# 📋 Missão 07 — Explorando outras tecnologias

Caso estejam disponíveis no seu sistema, execute:

```bash
snap list
```

```bash
flatpak list
```

Anote:

- quais tecnologias estão instaladas;
- quais aplicações utilizam cada tecnologia.

---

# 🧠 Perguntas para reflexão

Responda sem consultar o material.

1. Qual a diferença entre `apt update` e `apt upgrade`?
2. O que é um pacote?
3. O que é um repositório?
4. Quando utilizar Snap?
5. Quando utilizar Flatpak?
6. Quando um AppImage pode ser vantajoso?
7. Qual a função do comando `autoremove`?

---

# 💼 Situação do mercado

Imagine que um colega instalou um mesmo programa utilizando:

- APT;
- Snap;
- Flatpak.

Quais problemas isso pode causar?

Como você organizaria esse ambiente?

Explique sua resposta.

---

# ✅ Checklist

Antes de concluir este módulo, confirme:

- [ ] Identifiquei minha distribuição Linux.
- [ ] Descobri qual gerenciador de pacotes utilizo.
- [ ] Atualizei a lista de pacotes.
- [ ] Atualizei os programas instalados.
- [ ] Pesquisei softwares.
- [ ] Instalei programas.
- [ ] Removi um programa.
- [ ] Executei o `autoremove`.
- [ ] Consultei os repositórios.
- [ ] Identifiquei Snap e Flatpak (quando disponíveis).

---

# 🏆 Parabéns!

Você concluiu o Módulo 06 do Linux Explorer.

Agora você já é capaz de:

- compreender como os softwares são distribuídos no Linux;
- instalar programas com segurança;
- remover aplicações corretamente;
- manter o sistema atualizado;
- entender o funcionamento dos repositórios;
- utilizar tecnologias modernas como Snap, Flatpak e AppImage;
- aplicar boas práticas utilizadas por administradores Linux.

No próximo módulo você aprenderá a administrar **processos**, entendendo como o Linux executa programas, gerencia recursos e controla tudo o que acontece em tempo real no sistema operacional.
