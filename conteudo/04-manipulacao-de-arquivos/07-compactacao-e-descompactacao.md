# 07. Compactação e Descompactação de Arquivos

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 55 minutos

**Pré-requisitos:**

- Capítulo 00 — Preparando o Linux Explorer Lab
- Capítulos anteriores deste módulo

────────────────────────────────────────────

# Visão Geral

Arquivos compactados fazem parte do dia a dia de qualquer usuário Linux.

Projetos, backups, códigos-fonte, bancos de dados e documentos são frequentemente distribuídos em formatos compactados.

Neste capítulo você aprenderá os principais comandos utilizados para compactar e descompactar arquivos diretamente pelo Terminal.

---

# Estado atual do laboratório

Entre no laboratório:

```bash
cd ~/linux-explorer-lab
```

Confira sua localização:

```bash
pwd
```

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

- Compactar arquivos.
- Compactar diretórios.
- Descompactar arquivos.
- Trabalhar com os formatos mais utilizados no Linux.
- Escolher a ferramenta adequada para cada situação.

---

# Por que isso é importante?

Compactar arquivos reduz espaço em disco e facilita o compartilhamento de informações.

Além disso, muitos programas distribuídos para Linux utilizam arquivos compactados.

Saber trabalhar com esses formatos é uma habilidade indispensável.

---

# Quando você usará isso?

Você utilizará esses comandos para:

- criar backups;
- compartilhar projetos;
- baixar programas;
- armazenar documentos;
- distribuir aplicações.

---

# Você vai conhecer

| Comando | Finalidade |
|----------|------------|
| `tar` | Criar e extrair arquivos TAR |
| `gzip` | Compactar arquivos |
| `gunzip` | Descompactar arquivos GZIP |
| `zip` | Criar arquivos ZIP |
| `unzip` | Extrair arquivos ZIP |

---

# O comando `tar`

O comando `tar` é utilizado para agrupar vários arquivos em um único arquivo.

Exemplo:

```bash
tar -cvf backup.tar documentos
```

Onde:

| Opção | Significado |
|--------|-------------|
| `c` | Criar arquivo |
| `v` | Exibir detalhes durante a execução |
| `f` | Informar o nome do arquivo |

---

# Extraindo um arquivo TAR

Para extrair:

```bash
tar -xvf backup.tar
```

Onde:

| Opção | Significado |
|--------|-------------|
| `x` | Extrair |
| `v` | Exibir detalhes |
| `f` | Arquivo informado |

---

# Compactando com gzip

O comando `gzip` compacta arquivos.

Exemplo:

```bash
gzip relatorio.txt
```

Resultado:

```text
relatorio.txt.gz
```

O arquivo original será substituído pela versão compactada.

---

# Descompactando

Utilize:

```bash
gunzip relatorio.txt.gz
```

O arquivo original será restaurado.

---

# Trabalhando com ZIP

Criando:

```bash
zip documentos.zip documentos/*
```

Extraindo:

```bash
unzip documentos.zip
```

O formato ZIP é amplamente utilizado para compartilhamento de arquivos entre diferentes sistemas operacionais.

---

# 🧠 Como o Linux enxerga isso?

É importante compreender que **compactar** e **agrupar** são operações diferentes.

O formato TAR apenas reúne vários arquivos em um único arquivo.

Já ferramentas como GZIP realizam efetivamente a compressão dos dados.

Por isso é muito comum encontrar arquivos com extensões como:

```text
arquivo.tar.gz
```

Nesse caso:

- o TAR agrupou os arquivos;
- o GZIP compactou o resultado.

---

# O que normalmente você encontrará aqui?

Durante este capítulo você trabalhará com:

- backups;
- projetos compactados;
- arquivos `.tar`;
- arquivos `.tar.gz`;
- arquivos `.zip`.

Esses formatos são amplamente utilizados no ecossistema Linux.

---

# Comparando com Windows

| Windows | Linux |
|----------|--------|
| Enviar para → Pasta Compactada | `zip` |
| Extrair Tudo | `unzip` |
| Arquivo ZIP | `zip` |
| Arquivo TAR | `tar` |
| Arquivo GZIP | `gzip` |


---

# 🛠️ Ferramentas que utilizam esses comandos

Os formatos de compactação apresentados neste capítulo são utilizados diariamente por diversas ferramentas e serviços, como:

* GitHub (downloads de projetos)
* Docker
* Kubernetes
* Distribuições Linux
* Sistemas de Backup
* Bancos de Dados
* Ferramentas de Deploy

Sempre que você baixar um projeto Open Source ou realizar um backup, provavelmente encontrará um desses formatos.

---

# Pratique

Entre no laboratório:

```bash
cd ~/linux-explorer-lab
```

Crie um arquivo TAR com a pasta `documentos`:

```bash
tar -cvf compactados/documentos.tar documentos
```

Liste o conteúdo da pasta `compactados`:

```bash
ls -lh compactados
```

Agora extraia o arquivo:

```bash
tar -xvf compactados/documentos.tar
```

---

Compacte um arquivo utilizando GZIP:

```bash
gzip documentos/relatorio.txt
```

Confira:

```bash
ls documentos
```

Agora restaure o arquivo:

```bash
gunzip documentos/relatorio.txt.gz
```

---

Crie um arquivo ZIP:

```bash
zip -r compactados/projetos.zip projetos
```

Confira:

```bash
ls compactados
```

Extraia o conteúdo:

```bash
unzip compactados/projetos.zip
```

---

# 🧪 Experimento

Agora vamos criar um backup compactado do laboratório.

Execute:

```bash
tar -czvf compactados/linux-explorer-lab.tar.gz .
```

Onde:

* `c` → criar;
* `z` → utilizar GZIP;
* `v` → modo detalhado;
* `f` → nome do arquivo.

Confira:

```bash
ls -lh compactados
```

Agora veja o conteúdo do arquivo compactado sem extraí-lo:

```bash
tar -tvf compactados/linux-explorer-lab.tar.gz
```

Observe que é possível visualizar a estrutura do arquivo antes da extração.

---

# Explore

Compare os tamanhos dos arquivos:

```bash
ls -lh documentos
```

Depois:

```bash
ls -lh compactados
```

Reflita:

* Qual arquivo ficou menor?
* Em quais situações a compactação traz maior benefício?
* Todos os tipos de arquivos compactam da mesma forma?

---

# 💼 Exemplos do mundo real

Imagine que você precisa enviar um projeto completo para outra equipe.

Em vez de enviar centenas de arquivos individualmente, basta criar:

```bash
tar -czvf projeto.tar.gz projeto
```

Outro exemplo é realizar backups periódicos de aplicações:

```bash
tar -czvf backup-$(date +%F).tar.gz /caminho/do/projeto
```

Essa prática é muito comum em servidores Linux.

---

# ⚠️ Pode alterar?

| Local         | Pode alterar? | Observação                                                                         |
| ------------- | ------------- | ---------------------------------------------------------------------------------- |
| `compactados` | ✅ Sim         | Utilize esta pasta para criar e testar arquivos compactados durante os exercícios. |

Evite compactar diretórios do sistema sem compreender exatamente seu conteúdo.

---

# 💡 Dica profissional

Antes de extrair um arquivo desconhecido, visualize seu conteúdo:

```bash
tar -tvf arquivo.tar
```

ou

```bash
unzip -l arquivo.zip
```

Esse hábito ajuda a evitar a extração de arquivos em locais inadequados.

---

# 🧠 Mentalidade Linux

No Linux, a compactação normalmente faz parte dos processos de backup, distribuição e automação.

Profissionais utilizam esses comandos não apenas para economizar espaço, mas também para facilitar a transferência e preservar a estrutura de diretórios.

---

# Você sabia?

Grande parte dos programas distribuídos para Linux utiliza o formato:

```text
.tar.gz
```

Isso acontece porque o TAR preserva toda a estrutura do projeto e o GZIP reduz significativamente o tamanho do arquivo.

É um dos formatos mais tradicionais do ecossistema Linux.

---

# 🏁 Estado esperado do laboratório

Ao concluir este capítulo, seu laboratório deverá conter uma pasta `compactados` semelhante a esta:

```text
compactados
├── documentos.tar
├── linux-explorer-lab.tar.gz
└── projetos.zip
```

Os demais diretórios do laboratório permanecerão organizados conforme os capítulos anteriores.

---

# Resumo rápido

| Comando                          | Finalidade                            |
| -------------------------------- | ------------------------------------- |
| `tar -cvf arquivo.tar pasta`     | Criar arquivo TAR                     |
| `tar -xvf arquivo.tar`           | Extrair arquivo TAR                   |
| `tar -czvf arquivo.tar.gz pasta` | Criar arquivo TAR compactado com GZIP |
| `tar -tvf arquivo.tar.gz`        | Listar conteúdo do arquivo compactado |
| `gzip arquivo`                   | Compactar arquivo                     |
| `gunzip arquivo.gz`              | Descompactar arquivo                  |
| `zip -r arquivo.zip pasta`       | Compactar em ZIP                      |
| `unzip arquivo.zip`              | Extrair arquivo ZIP                   |

---

# Erros comuns

* Confundir TAR com GZIP.
* Esquecer a opção `-r` ao compactar diretórios com `zip`.
* Extrair arquivos sem verificar o conteúdo.
* Compactar arquivos diretamente em diretórios incorretos.

---

# Referências

* GNU Tar Manual
* Gzip Documentation
* Info-ZIP Project
* Linux Foundation

---

# Conclusão

Neste capítulo você aprendeu a criar e extrair arquivos compactados utilizando os formatos mais comuns do Linux.

Também compreendeu a diferença entre agrupamento e compactação, conhecendo ferramentas utilizadas diariamente por profissionais para backup, distribuição e compartilhamento de arquivos.

---

# 🔗 Revisite este conceito

Lembre-se dos capítulos anteriores.

Você criou, organizou, moveu, removeu e localizou arquivos.

Agora também sabe agrupá-los e compactá-los, completando praticamente todo o ciclo de manipulação de arquivos no Linux.

---

# Prepare-se para o próximo capítulo

Chegamos ao último capítulo do módulo.

Nele faremos uma revisão prática dos comandos mais importantes relacionados à manipulação de arquivos e diretórios.

Será uma excelente oportunidade para consolidar todo o conhecimento adquirido até aqui.

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
* ✅ Criar Links Simbólicos e Hard Links.
* ✅ Compactar e descompactar arquivos utilizando `tar`, `gzip` e `zip`.

Falta apenas um capítulo para concluir o Módulo 04 e dominar as principais operações de manipulação de arquivos no Linux.

