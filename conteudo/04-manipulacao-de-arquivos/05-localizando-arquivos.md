# 05. Localizando Arquivos

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 50 minutos

**Pré-requisitos:**

* Capítulo 00 — Preparando o Linux Explorer Lab
* Capítulos anteriores deste módulo

────────────────────────────────────────────

# Visão Geral

À medida que um sistema Linux cresce, a quantidade de arquivos também aumenta.

Projetos, documentos, scripts, imagens, logs e programas passam a ocupar centenas ou até milhares de diretórios.

Nessas situações, navegar manualmente pela estrutura do sistema deixa de ser eficiente.

Neste capítulo você aprenderá os principais comandos para localizar arquivos, diretórios e programas utilizando o Terminal.

---

# Estado atual do laboratório

Antes de começar, entre no laboratório:

```bash
cd ~/linux-explorer-lab
```

Confira onde está:

```bash
pwd
```

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

* Localizar arquivos pelo nome.
* Localizar diretórios.
* Encontrar programas instalados.
* Descobrir onde um comando está localizado.
* Pesquisar rapidamente dentro do sistema.

---

# Por que isso é importante?

Um profissional Linux dificilmente sabe de memória onde todos os arquivos estão.

Em vez disso, ele sabe **como encontrá-los rapidamente**.

Esses comandos economizam muito tempo durante manutenção, desenvolvimento e administração de sistemas.

---

# Quando você usará isso?

Você utilizará esses comandos para:

* localizar documentos;
* encontrar scripts;
* descobrir onde programas estão instalados;
* procurar arquivos de configuração;
* localizar logs.

---

# Você vai conhecer

| Comando   | Finalidade                                  |
| --------- | ------------------------------------------- |
| `find`    | Procurar arquivos e diretórios              |
| `locate`  | Pesquisa rápida em banco de dados           |
| `which`   | Localizar comandos executáveis              |
| `whereis` | Localizar programas, manuais e código-fonte |

---

# O comando `find`

O comando `find` percorre diretórios procurando arquivos.

Sintaxe:

```bash
find caminho opções
```

Exemplo:

```bash
find . -name "clientes.txt"
```

O ponto (`.`) indica que a busca começará no diretório atual.

---

# Procurando diretórios

Também é possível localizar apenas diretórios:

```bash
find . -type d
```

O parâmetro `-type d` informa ao Linux que apenas diretórios devem ser exibidos.

---

# Procurando arquivos

Para listar apenas arquivos:

```bash
find . -type f
```

---

# Pesquisando por extensão

Exemplo:

```bash
find . -name "*.txt"
```

Serão exibidos todos os arquivos com extensão `.txt`.

---

# O comando `locate`

O comando `locate` realiza pesquisas muito rápidas.

Exemplo:

```bash
locate clientes.txt
```

Diferentemente do `find`, ele consulta um banco de dados previamente criado.

Em algumas distribuições pode ser necessário atualizar esse banco utilizando:

```bash
sudo updatedb
```

---

# O comando `which`

O comando `which` informa onde um programa executável está localizado.

Exemplo:

```bash
which python3
```

Outro exemplo:

```bash
which git
```

Resultado esperado:

```text
/usr/bin/git
```

---

# O comando `whereis`

O comando `whereis` apresenta mais informações.

Exemplo:

```bash
whereis python3
```

Além do executável, ele pode mostrar:

* documentação;
* páginas de manual;
* código-fonte (quando disponível).

---

# 🧠 Como o Linux enxerga isso?

Quando você executa um comando como:

```bash
git
```

o Linux procura esse programa nos diretórios definidos na variável de ambiente `PATH`.

Comandos como `which` ajudam justamente a descobrir onde esse executável foi encontrado.

---

# O que normalmente você encontrará aqui?

Durante este capítulo você localizará:

* arquivos;
* diretórios;
* programas;
* executáveis;
* arquivos de configuração.

Essas pesquisas fazem parte da rotina diária de qualquer administrador Linux.

---

# Comparando com Windows

| Windows              | Linux     |
| -------------------- | --------- |
| Pesquisa do Explorer | `find`    |
| Pesquisar programas  | `which`   |
| Localizar instalação | `whereis` |
| Busca indexada       | `locate`  |

---

# 🛠️ Ferramentas que utilizam esses comandos

Os comandos apresentados neste capítulo são utilizados por diversas ferramentas e profissionais, entre eles:

* Administradores de Sistemas
* DevOps
* Engenheiros de Dados
* Desenvolvedores
* Shell Scripts
* Ferramentas de Backup
* Docker
* Kubernetes

Sempre que um arquivo ou programa precisa ser localizado rapidamente, esses comandos entram em ação.

---

# Pratique

Entre no laboratório:

```bash
cd ~/linux-explorer-lab
```

Localize todos os arquivos `.txt`:

```bash
find . -name "*.txt"
```

Agora liste apenas os diretórios:

```bash
find . -type d
```

Liste apenas os arquivos:

```bash
find . -type f
```

Descubra onde está o Git:

```bash
which git
```

Agora localize o Python:

```bash
which python3
```

Veja mais informações sobre o Git:

```bash
whereis git
```

---

# 🧪 Experimento

Vamos criar novos arquivos para testar as pesquisas.

Execute:

```bash
touch documentos/relatorio.txt
touch documentos/clientes.csv
touch projetos/api/config.json
touch projetos/site/style.css
```

Agora execute:

```bash
find . -name "*.txt"
```

Depois:

```bash
find . -name "*.csv"
```

Agora:

```bash
find . -name "*.json"
```

Por fim:

```bash
find . -name "*.css"
```

Observe como o `find` consegue localizar arquivos utilizando padrões diferentes.

---

# Explore

Experimente pesquisar apenas diretórios chamados **backup**:

```bash
find . -type d -name "backup"
```

Agora procure tudo que contenha a palavra **cliente**:

```bash
find . -name "*cliente*"
```

Faça outras pesquisas alterando o nome ou a extensão dos arquivos.

Esse tipo de exploração ajuda a entender o potencial do comando `find`.

---

# 💼 Exemplos do mundo real

Imagine que você precisa localizar um arquivo de configuração chamado `config.json`, mas não sabe onde ele está.

Em vez de procurar manualmente, basta executar:

```bash
find . -name "config.json"
```

Outro exemplo é descobrir rapidamente onde o sistema instalou o Git:

```bash
which git
```

Ou encontrar todas as imagens PNG de um projeto:

```bash
find . -name "*.png"
```

Esses comandos economizam muito tempo durante o desenvolvimento e a administração de sistemas.

---

# ⚠️ Pode alterar?

| Comando   | Altera arquivos? |
| --------- | ---------------- |
| `find`    | ❌ Não            |
| `locate`  | ❌ Não            |
| `which`   | ❌ Não            |
| `whereis` | ❌ Não            |

Todos os comandos apresentados neste capítulo realizam apenas consultas.

---

# 💡 Dica profissional

Sempre que possível, restrinja a pesquisa ao menor diretório necessário.

Por exemplo, pesquisar dentro de um projeto específico é muito mais rápido do que pesquisar em todo o sistema.

---

# 🧠 Mentalidade Linux

Um bom profissional não tenta memorizar onde todos os arquivos estão.

Ele domina as ferramentas que permitem encontrá-los rapidamente.

Essa habilidade aumenta muito a produtividade e reduz o tempo gasto procurando arquivos manualmente.

---

# Você sabia?

O comando `find` é extremamente poderoso.

Além de localizar arquivos, ele pode executar ações automaticamente sobre os resultados encontrados.

Esse recurso será muito útil quando você começar a trabalhar com Shell Script e automação.

---

# 🏁 Estado esperado do laboratório

Ao concluir este capítulo, seu laboratório deverá estar semelhante a este:

```text
linux-explorer-lab
│
├── backup
├── compactados
├── documentos
│   ├── arquivados
│   │   └── fornecedores-antigos.txt
│   ├── clientes.csv
│   ├── clientes.txt
│   ├── meu-primeiro-arquivo.txt
│   └── relatorio.txt
│
├── downloads
│   └── produtos.txt
│
├── imagens
│
├── projetos
│   ├── api
│   │   ├── app.py
│   │   └── config.json
│   │
│   ├── app-mobile
│   ├── ecommerce
│   └── site
│       ├── index.html
│       └── style.css
│
├── temporarios
└── testes
```

---

# Resumo rápido

| Comando                | Finalidade                                      |
| ---------------------- | ----------------------------------------------- |
| `find . -name "*.txt"` | Localizar arquivos por nome                     |
| `find . -type f`       | Localizar arquivos                              |
| `find . -type d`       | Localizar diretórios                            |
| `which git`            | Encontrar o executável de um programa           |
| `whereis git`          | Localizar executável, manuais e outros arquivos |
| `locate arquivo`       | Pesquisa rápida utilizando banco de dados       |

---

# Erros comuns

* Pesquisar a partir do diretório errado.
* Esquecer de utilizar aspas em padrões como `"*.txt"`.
* Esperar que `locate` encontre arquivos recém-criados sem atualizar seu banco de dados.
* Confundir `which` com `whereis`.

---

# Referências

* GNU Findutils
* Linux Foundation
* Ubuntu Documentation

---

# Conclusão

Neste capítulo você aprendeu a localizar arquivos, diretórios e programas utilizando os comandos `find`, `locate`, `which` e `whereis`.

Essas ferramentas fazem parte do conjunto de comandos mais utilizados por profissionais Linux e serão extremamente úteis durante toda a sua jornada.

---

# 🔗 Revisite este conceito

Lembre-se do **Módulo 03 — Sistema de Arquivos Linux**.

Agora que você conhece a estrutura dos diretórios, localizar arquivos dentro dessa estrutura tornou-se muito mais simples utilizando as ferramentas apresentadas neste capítulo.

---

# Prepare-se para o próximo capítulo

Até aqui você aprendeu a criar, organizar, remover, visualizar e localizar arquivos.

No próximo capítulo conheceremos um recurso muito importante do Linux:

* Links simbólicos (*Symbolic Links*)
* Hard Links

Você entenderá como criar atalhos, compartilhar arquivos e compreender um dos conceitos mais elegantes do sistema de arquivos Linux.

---

# 📈 Evolução do Linux Explorer Lab

## Competências conquistadas

Até este momento você já domina:

* ✅ Preparar um ambiente seguro para estudos.
* ✅ Criar arquivos e diretórios.
* ✅ Copiar arquivos e diretórios.
* ✅ Mover e renomear arquivos.
* ✅ Excluir arquivos e diretórios com segurança.
* ✅ Visualizar arquivos com `cat`, `less`, `head` e `tail`.
* ✅ Acompanhar arquivos em tempo real com `tail -f`.
* ✅ Localizar arquivos utilizando `find`.
* ✅ Descobrir onde programas estão instalados com `which`.
* ✅ Obter informações adicionais com `whereis`.
* ✅ Realizar pesquisas rápidas com `locate`.

Seu **Linux Explorer Lab** continua evoluindo e, a esta altura do módulo, você já domina praticamente todas as operações fundamentais de manipulação de arquivos no Linux.

