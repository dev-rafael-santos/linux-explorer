# Capítulo 05 — Repositórios de Software

## 📖 Introdução

Sempre que instalamos ou atualizamos um programa utilizando um gerenciador de pacotes, os arquivos precisam ser obtidos de algum lugar.

Esse local é chamado de **repositório de software**.

Os repositórios armazenam milhares de pacotes organizados e assinados digitalmente, permitindo que o sistema instale programas de forma segura e confiável.

Neste capítulo você entenderá como eles funcionam e por que são tão importantes para a segurança do Linux.

---

# 🎯 Objetivos

Ao concluir este capítulo você será capaz de:

- compreender o conceito de repositório;
- entender como o Linux localiza pacotes;
- visualizar os repositórios configurados;
- conhecer repositórios oficiais e de terceiros;
- identificar boas práticas ao adicionar novas fontes de software.

---

# 🤔 O que é um repositório?

Um repositório é um servidor que armazena pacotes de software organizados por distribuição e versão.

Quando você instala um programa, o gerenciador de pacotes consulta esses servidores para localizar a versão correta.

Podemos imaginar um repositório como uma grande biblioteca de programas.

---

# 🧠 Uma analogia

Imagine uma livraria online.

Você procura um livro.

A loja informa:

- se ele existe;
- qual a versão mais recente;
- quem é o autor;
- faz o download.

O gerenciador de pacotes faz exatamente esse trabalho com softwares.

---

# Como funciona?

O processo normalmente acontece desta forma:

```text
Usuário
      │
      ▼
APT
      │
      ▼
Lista de Repositórios
      │
      ▼
Servidor Oficial
      │
      ▼
Download do Pacote
      │
      ▼
Instalação
```

Todo esse processo acontece automaticamente.

---

# Onde ficam os repositórios?

No Ubuntu e em outras distribuições baseadas em Debian, os repositórios são configurados em:

```text
/etc/apt/sources.list
```

e também em:

```text
/etc/apt/sources.list.d/
```

Esses arquivos informam ao APT onde procurar os pacotes.

---

# Visualizando os repositórios

Para visualizar o arquivo principal:

```bash
cat /etc/apt/sources.list
```

Em versões mais recentes do Ubuntu, boa parte da configuração pode estar em:

```bash
ls /etc/apt/sources.list.d
```

Você verá arquivos contendo os repositórios adicionais configurados.

---

# Repositórios oficiais

Os repositórios oficiais são mantidos pela própria distribuição.

Eles oferecem:

- pacotes testados;
- atualizações de segurança;
- correções de bugs;
- assinaturas digitais.

Sempre que possível, utilize os repositórios oficiais.

---

# Repositórios de terceiros

Alguns desenvolvedores disponibilizam seus próprios repositórios.

Exemplos comuns:

- Docker
- Google Chrome
- Microsoft
- Visual Studio Code

Eles permitem instalar versões mais recentes de determinados programas.

---

# Cuidados ao adicionar novos repositórios

Antes de adicionar um novo repositório, verifique:

- quem é o mantenedor;
- se o endereço é oficial;
- se utiliza assinatura GPG;
- se realmente é necessário.

Adicionar repositórios desconhecidos pode comprometer a segurança do sistema.

---

# Como o APT sabe que existe uma atualização?

Quando executamos:

```bash
sudo apt update
```

O APT consulta todos os repositórios configurados.

Ele baixa apenas os índices dos pacotes.

Nenhum programa é instalado nessa etapa.

Somente depois, ao executar:

```bash
sudo apt upgrade
```

os pacotes são efetivamente baixados e atualizados.

---

# 🔍 Curiosidade Técnica

O comando:

```bash
sudo apt update
```

não baixa programas.

Ele atualiza apenas uma lista contendo informações como:

- nome do pacote;
- versão disponível;
- tamanho;
- dependências;
- localização no servidor.

Essa lista permite que o APT saiba exatamente quais versões podem ser instaladas.

---

# 💼 Aplicação no mercado

Empresas frequentemente mantêm seus próprios repositórios internos.

Isso permite:

- distribuir softwares corporativos;
- controlar versões;
- reduzir consumo de Internet;
- garantir que todos os servidores utilizem os mesmos pacotes.

Essa prática é bastante comum em grandes organizações.

---

# ⚠️ Erros comuns

Evite:

- adicionar repositórios sem conhecer sua origem;
- misturar repositórios de versões diferentes da distribuição;
- remover repositórios oficiais;
- ignorar avisos sobre assinaturas digitais.

---

# 🧪 Laboratório

Liste os repositórios configurados:

```bash
cat /etc/apt/sources.list
```

Agora liste os arquivos adicionais:

```bash
ls -l /etc/apt/sources.list.d
```

Caso existam arquivos nesse diretório, visualize um deles:

```bash
cat /etc/apt/sources.list.d/*.sources
```

Observe:

- URLs utilizadas;
- distribuição configurada;
- componentes disponíveis.

---

# 🧠 Você consegue explicar?

Sem consultar o material, tente responder:

1. O que é um repositório?
2. Qual a diferença entre um repositório oficial e um de terceiros?
3. Onde o Ubuntu armazena a configuração dos repositórios?
4. O que acontece quando executamos `apt update`?

Se conseguir responder essas perguntas, você compreendeu como o Linux localiza e distribui softwares.

---

# 📝 Resumo

Neste capítulo você aprendeu que:

- os repositórios armazenam pacotes de software;
- o APT consulta esses servidores antes de instalar programas;
- os repositórios oficiais são os mais seguros;
- `apt update` atualiza apenas os índices dos pacotes;
- empresas podem manter repositórios próprios para controlar seus ambientes.

No próximo capítulo conheceremos três tecnologias muito utilizadas atualmente para distribuição de aplicações: **Snap, Flatpak e AppImage**, entendendo suas diferenças, vantagens e quando utilizar cada uma.
