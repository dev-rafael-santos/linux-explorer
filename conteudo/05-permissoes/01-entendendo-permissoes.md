# 01. Entendendo Permissões no Linux

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 45 minutos

**Pré-requisitos:**

* Capítulo 00 — Preparando o Laboratório de Segurança
* Módulo 04 — Manipulação de Arquivos

────────────────────────────────────────────

# Visão Geral

No Linux, nem todo usuário pode fazer tudo.

Cada arquivo e diretório possui regras que definem quem pode ler, modificar ou executar aquele recurso.

Essas regras são chamadas de **permissões**.

Neste capítulo você aprenderá a interpretar permissões como:

```text
-rwxr-xr--
```

À primeira vista, essa sequência parece confusa.

Mas, depois deste capítulo, ela começará a fazer sentido.

---

# Estado atual do laboratório

Entre no laboratório:

```bash
cd ~/linux-explorer-lab/seguranca
```

Confira sua localização:

```bash
pwd
```

Visualize a estrutura:

```bash
tree
```

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

* Entender o que são permissões no Linux.
* Identificar permissões de leitura, escrita e execução.
* Diferenciar permissões de usuário, grupo e outros.
* Interpretar a saída do comando `ls -l`.
* Entender a diferença entre permissões de arquivos e diretórios.

---

# Por que isso é importante?

Permissões são uma das bases da segurança no Linux.

Elas definem quem pode acessar arquivos, modificar dados, executar scripts e administrar recursos do sistema.

Sem entender permissões, comandos como `chmod`, `chown` e `chgrp` parecem apenas decoração.

Com esse entendimento, eles passam a fazer sentido.

---

# Quando você usará isso?

Você usará permissões para:

* proteger arquivos importantes;
* liberar acesso a outros usuários;
* executar scripts;
* configurar servidores;
* corrigir erros de acesso negado;
* administrar sistemas Linux com segurança.

---

# Você vai conhecer

| Conceito | Significado                |
| -------- | -------------------------- |
| `r`      | Leitura                    |
| `w`      | Escrita                    |
| `x`      | Execução                   |
| Usuário  | Dono do arquivo            |
| Grupo    | Grupo associado ao arquivo |
| Outros   | Demais usuários do sistema |

---

# O que são permissões?

Permissões são regras que controlam o que pode ser feito com arquivos e diretórios.

No Linux, as três permissões básicas são:

| Permissão | Letra | Significado                 |
| --------- | ----- | --------------------------- |
| Leitura   | `r`   | Permite visualizar conteúdo |
| Escrita   | `w`   | Permite modificar conteúdo  |
| Execução  | `x`   | Permite executar ou acessar |

Essas permissões são aplicadas a três categorias:

| Categoria | Significado                |
| --------- | -------------------------- |
| Usuário   | Dono do arquivo            |
| Grupo     | Grupo associado ao arquivo |
| Outros    | Todos os demais usuários   |

---

# Visualizando permissões

Execute:

```bash
ls -l
```

Você verá uma saída semelhante a:

```text
-rw-r--r-- 1 rafa rafa 0 jun 28 10:00 publicos/manual.txt
```

A primeira parte é a permissão:

```text
-rw-r--r--
```

Vamos entender isso por partes.

---

# A primeira posição

O primeiro caractere indica o tipo do arquivo.

```text
-
```

significa arquivo comum.

```text
d
```

significa diretório.

Exemplos:

```text
-rw-r--r-- arquivo.txt
drwxr-xr-x documentos
```

---

# Dividindo as permissões

A sequência:

```text
-rwxr-xr--
```

pode ser dividida assim:

```text
- rwx r-x r--
│  │   │   │
│  │   │   └── outros
│  │   └────── grupo
│  └────────── usuário
└───────────── tipo
```

Ou seja:

| Parte | Significado           |
| ----- | --------------------- |
| `-`   | Tipo do arquivo       |
| `rwx` | Permissões do usuário |
| `r-x` | Permissões do grupo   |
| `r--` | Permissões de outros  |

---

# Permissão de leitura

A permissão `r` permite ler o conteúdo.

Em arquivos, significa visualizar o conteúdo.

Em diretórios, significa listar o conteúdo.

Exemplo:

```text
r--
```

indica permissão de leitura.

---

# Permissão de escrita

A permissão `w` permite alterar.

Em arquivos, significa modificar o conteúdo.

Em diretórios, significa criar, renomear ou remover arquivos dentro dele.

Exemplo:

```text
-w-
```

indica permissão de escrita.

---

# Permissão de execução

A permissão `x` permite executar.

Em arquivos, significa executar o arquivo como programa ou script.

Em diretórios, significa entrar no diretório com `cd`.

Exemplo:

```text
--x
```

indica permissão de execução.

---

# Permissões em arquivos

Em arquivos, as permissões significam:

| Permissão | Em arquivos                   |
| --------- | ----------------------------- |
| `r`       | Ler o conteúdo                |
| `w`       | Alterar o conteúdo            |
| `x`       | Executar como programa/script |

---

# Permissões em diretórios

Em diretórios, as permissões possuem outro comportamento:

| Permissão | Em diretórios                       |
| --------- | ----------------------------------- |
| `r`       | Listar arquivos                     |
| `w`       | Criar, remover ou renomear arquivos |
| `x`       | Entrar no diretório                 |

Esse detalhe é muito importante.

Um diretório precisa da permissão `x` para ser acessado com `cd`.

---

# 🧠 Como o Linux enxerga isso?

Para o Linux, cada arquivo possui metadados.

Esses metadados informam:

* tipo do arquivo;
* dono;
* grupo;
* permissões;
* tamanho;
* datas;
* nome.

Quando você tenta acessar um arquivo, o sistema verifica essas informações antes de permitir ou negar a ação.

---

# O que normalmente você encontrará aqui?

Durante este módulo você verá permissões como:

```text
-rw-r--r--
-rwxr-xr-x
drwxr-xr-x
drwx------
```

Cada uma delas representa um conjunto diferente de regras de acesso.

---

# Comparando com Windows

| Windows                     | Linux               |
| --------------------------- | ------------------- |
| Propriedades do arquivo     | `ls -l`             |
| Aba Segurança               | Permissões `rwx`    |
| Usuários e grupos           | Dono e grupo        |
| Executar como administrador | Permissões e `sudo` |

---

# 🛠️ Ferramentas que utilizam esse conceito

O sistema de permissões do Linux é utilizado por praticamente todos os serviços e aplicações do sistema operacional, incluindo:

* Apache
* Nginx
* Docker
* Kubernetes
* OpenSSH
* PostgreSQL
* MySQL
* Git
* Shell Scripts

Sempre que um programa tenta acessar um arquivo, o Linux verifica suas permissões antes de permitir a operação.

---

# Pratique

Entre no laboratório:

```bash
cd ~/linux-explorer-lab/seguranca
```

Liste os arquivos com detalhes:

```bash
ls -l
```

Agora liste um diretório específico:

```bash
ls -l publicos
```

Depois:

```bash
ls -l privados
```

Observe cuidadosamente a primeira coluna da saída.

Identifique:

* o tipo do arquivo;
* as permissões do usuário;
* as permissões do grupo;
* as permissões dos outros usuários.

---

# 🧪 Experimento

Liste os arquivos utilizando:

```bash
ls -lh
```

Agora utilize:

```bash
ls -la
```

Compare os resultados.

Depois execute:

```bash
ls -ld publicos
```

Agora:

```bash
ls -ld scripts
```

Observe que agora você está visualizando as permissões do diretório, e não dos arquivos que estão dentro dele.

Esse detalhe costuma gerar dúvidas entre iniciantes.

---

# Explore

Analise cada uma das permissões abaixo e tente responder o que elas significam antes de consultar a explicação.

```text
-rw-r--r--
```

```text
-rwx------
```

```text
drwxr-xr-x
```

```text
drwx------
```

Depois compare com a tabela apresentada anteriormente.

Esse exercício ajuda a desenvolver a leitura das permissões sem depender de memorização.

---

# 💼 Exemplos do mundo real

Imagine um servidor Web.

Os arquivos do site normalmente possuem permissão para leitura pelos usuários responsáveis pelo serviço, mas não para escrita por qualquer usuário.

Outro exemplo são scripts administrativos.

Eles frequentemente possuem permissão de execução apenas para administradores.

Essas configurações ajudam a proteger o sistema contra alterações indevidas.

---

# ⚠️ Pode alterar?

| Item                    | Pode alterar? | Observação                                                       |
| ----------------------- | ------------- | ---------------------------------------------------------------- |
| Arquivos do laboratório | ✅ Sim         | Utilize-os livremente para estudar permissões.                   |
| Arquivos do sistema     | ⚠️ Não        | Evite alterar permissões fora do laboratório durante os estudos. |

---

# 💡 Dica profissional

Sempre que um programa apresentar a mensagem:

```text
Permission denied
```

o primeiro passo deve ser verificar as permissões utilizando:

```bash
ls -l
```

Em muitos casos, o problema está relacionado às permissões do arquivo ou diretório.

---

# 🧠 Mentalidade Linux

O Linux adota o princípio do **menor privilégio**.

Isso significa que um usuário deve possuir apenas as permissões necessárias para realizar seu trabalho.

Essa abordagem reduz riscos e aumenta a segurança do sistema.

---

# Você sabia?

Mesmo o usuário proprietário de um arquivo pode encontrar restrições dependendo da configuração do sistema e das permissões aplicadas.

Além disso, o usuário **root** possui privilégios especiais e normalmente consegue acessar arquivos independentemente das permissões convencionais.

Nos próximos capítulos entenderemos como isso funciona na prática.

---

# 🏁 Estado esperado do laboratório

Ao concluir este capítulo, a estrutura do laboratório permanecerá inalterada.

O objetivo deste capítulo foi compreender a leitura das permissões, sem realizar modificações.

```text
linux-explorer-lab
│
└── seguranca
    ├── compartilhados
    ├── documentos
    ├── grupos
    ├── privados
    ├── publicos
    ├── scripts
    └── testes
```

---

# Resumo rápido

| Elemento | Significado     |
| -------- | --------------- |
| `r`      | Leitura         |
| `w`      | Escrita         |
| `x`      | Execução        |
| Usuário  | Dono do arquivo |
| Grupo    | Grupo associado |
| Outros   | Demais usuários |
| `-`      | Arquivo comum   |
| `d`      | Diretório       |

---

# Erros comuns

* Confundir permissões de arquivos com permissões de diretórios.
* Ler as permissões da esquerda para a direita sem separá-las em grupos.
* Esquecer que diretórios utilizam as permissões de forma diferente dos arquivos.
* Pensar que `rwx` significa a mesma coisa para arquivos e diretórios.

---

# Referências

* Linux Foundation
* GNU Coreutils
* Ubuntu Documentation

---

# Conclusão

Neste capítulo você aprendeu a interpretar as permissões do Linux.

Agora já consegue identificar quem pode ler, escrever ou executar um arquivo apenas observando a saída do comando `ls -l`.

Esse conhecimento servirá de base para alterar permissões utilizando o comando `chmod`, assunto do próximo capítulo.

---

# 🔗 Revisite este conceito

Lembre-se do **Módulo 03 — Sistema de Arquivos Linux**.

Naquele momento você aprendeu onde os arquivos ficam armazenados.

Agora está aprendendo quem pode acessá-los e de que maneira.

Esses dois conhecimentos se complementam e formam a base da administração de arquivos no Linux.

---

# Prepare-se para o próximo capítulo

Agora que você já consegue interpretar permissões como:

```text
-rwxr-xr--
```

chegou o momento de modificá-las.

No próximo capítulo aprenderemos a utilizar o comando:

```bash
chmod
```

tanto no modo simbólico quanto no modo numérico (octal).

---

# 📈 Evolução do Laboratório de Segurança

## Competências conquistadas

Até este momento você já domina:

* ✅ Preparar o Laboratório de Segurança.
* ✅ Interpretar permissões de arquivos.
* ✅ Interpretar permissões de diretórios.
* ✅ Identificar usuário, grupo e outros.
* ✅ Ler corretamente a saída do comando `ls -l`.
* ✅ Compreender como o Linux controla o acesso aos arquivos.

Nos próximos capítulos você começará a modificar essas permissões, entendendo na prática como o Linux aplica seu modelo de segurança.
