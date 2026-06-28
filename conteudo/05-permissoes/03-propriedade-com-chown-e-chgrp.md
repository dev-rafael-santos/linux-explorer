# 03. Propriedade com chown e chgrp

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 55 minutos

**Pré-requisitos:**

- Capítulo 00 — Preparando o Laboratório de Segurança
- Capítulo 01 — Entendendo Permissões
- Capítulo 02 — Alterando Permissões com chmod

────────────────────────────────────────────

# Visão Geral

No capítulo anterior você aprendeu a controlar o que cada usuário pode fazer utilizando o comando `chmod`.

Agora chegou o momento de entender outro conceito fundamental do Linux:

**propriedade dos arquivos.**

Todo arquivo possui:

- um proprietário (owner);
- um grupo (group).

Neste capítulo você aprenderá como visualizar essas informações e alterá-las utilizando os comandos `chown` e `chgrp`.

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

Liste os arquivos:

```bash
ls -l
```

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

- Identificar o proprietário de um arquivo.
- Identificar o grupo associado.
- Alterar proprietário utilizando `chown`.
- Alterar grupo utilizando `chgrp`.
- Alterar proprietário e grupo simultaneamente.

---

# Por que isso é importante?

Em ambientes Linux é muito comum que diferentes usuários compartilhem o mesmo servidor.

Cada usuário deve possuir acesso apenas aos arquivos pelos quais é responsável.

Os comandos `chown` e `chgrp` permitem administrar essa propriedade de forma segura.

---

# Quando você usará isso?

Você utilizará esses comandos para:

- configurar servidores;
- organizar projetos compartilhados;
- corrigir permissões incorretas;
- preparar ambientes de desenvolvimento;
- administrar múltiplos usuários.

---

# Você vai conhecer

| Comando | Finalidade |
|----------|------------|
| `chown` | Alterar proprietário |
| `chgrp` | Alterar grupo |
| `ls -l` | Visualizar proprietário e grupo |

---

# Visualizando proprietário e grupo

Execute:

```bash
ls -l
```

Saída semelhante:

```text
-rwxr-xr-x 1 rafa rafa 35 jun 28 10:30 backup.sh
```

Observe estas colunas:

```text
-rwxr-xr-x
        │
        ▼
     proprietário

-rwxr-xr-x 1 rafa rafa
             │     │
             ▼     ▼
      proprietário grupo
```

---

# O comando chown

O comando `chown` altera o proprietário de um arquivo.

Sintaxe:

```bash
chown usuario arquivo
```

Exemplo:

```bash
sudo chown maria documentos/relatorio.txt
```

Após executar o comando, o usuário **maria** passará a ser a proprietária do arquivo.

---

# Alterando proprietário e grupo

Também é possível alterar os dois ao mesmo tempo.

Exemplo:

```bash
sudo chown maria:financeiro documentos/relatorio.txt
```

Resultado:

- Proprietário: `maria`
- Grupo: `financeiro`

---

# O comando chgrp

Caso seja necessário alterar apenas o grupo:

```bash
sudo chgrp financeiro documentos/relatorio.txt
```

O proprietário permanecerá o mesmo.

---

# Alterando diretórios inteiros

Utilizando a opção recursiva:

```bash
sudo chown -R maria:financeiro projetos
```

Todo o diretório será atualizado.

Essa opção deve ser utilizada com atenção.

---

# 🧠 Como o Linux enxerga isso?

O Linux registra, para cada arquivo:

- proprietário;
- grupo;
- permissões.

Sempre que alguém tenta acessar um arquivo, o sistema verifica:

1. É o proprietário?
2. Pertence ao grupo?
3. É outro usuário?

Somente depois dessa verificação as permissões são aplicadas.

---

# O que normalmente você encontrará aqui?

Durante sua rotina profissional verá comandos como:

```bash
sudo chown www-data:www-data /var/www/html
```

```bash
sudo chown -R usuario:usuario projeto
```

```bash
sudo chgrp developers projeto
```

Esses comandos são muito comuns na administração de servidores Linux.

---

# Comparando com Windows

| Windows | Linux |
|----------|--------|
| Proprietário do arquivo | `chown` |
| Grupo de usuários | `chgrp` |
| Propriedades → Segurança | `ls -l` + `chown` |

---

# 🛠️ Ferramentas que utilizam `chown` e `chgrp`

Os comandos `chown` e `chgrp` são utilizados diariamente por administradores de sistemas e por diversas aplicações, como:

* Apache
* Nginx
* Docker
* Kubernetes
* PostgreSQL
* MySQL
* OpenSSH
* Git
* Jenkins

Sempre que um serviço precisa acessar arquivos corretamente, a propriedade e o grupo devem estar configurados de forma adequada.

---

# Pratique

Entre no laboratório:

```bash
cd ~/linux-explorer-lab/seguranca
```

Visualize os detalhes dos arquivos:

```bash
ls -l documentos
```

Agora visualize o proprietário e o grupo do script:

```bash
ls -l scripts/backup.sh
```

Observe atentamente as colunas correspondentes ao proprietário e ao grupo.

Caso você possua permissões administrativas e tenha outros usuários cadastrados no sistema, experimente alterar o proprietário:

```bash
sudo chown usuario scripts/backup.sh
```

Confira o resultado:

```bash
ls -l scripts/backup.sh
```

---

# 🧪 Experimento

> **Observação:** este experimento exige permissões administrativas (`sudo`) e a existência de outro usuário no sistema. Caso você esteja utilizando uma máquina onde isso não seja possível, acompanhe os comandos e compreenda seu funcionamento.

Visualize as permissões atuais:

```bash
ls -l documentos/relatorio.txt
```

Agora altere apenas o grupo:

```bash
sudo chgrp grupo documentos/relatorio.txt
```

Confira novamente:

```bash
ls -l documentos/relatorio.txt
```

Agora altere proprietário e grupo simultaneamente:

```bash
sudo chown usuario:grupo documentos/relatorio.txt
```

Visualize mais uma vez:

```bash
ls -l documentos/relatorio.txt
```

Compare as mudanças observando apenas as colunas de proprietário e grupo.

---

# Explore

Caso exista mais de um usuário em seu sistema, experimente criar um arquivo de teste e alterar seu proprietário.

Depois tente acessá-lo utilizando outro usuário.

Observe como as permissões estudadas no capítulo anterior continuam sendo respeitadas.

Esse exercício demonstra como propriedade e permissões trabalham em conjunto.

---

# 💼 Exemplos do mundo real

Após instalar um servidor Web, é comum que os arquivos do site pertençam ao usuário responsável pelo serviço.

Exemplo:

```bash
sudo chown -R www-data:www-data /var/www/html
```

Outro caso comum ocorre quando um projeto é copiado de outro computador.

O administrador ajusta a propriedade utilizando:

```bash
sudo chown -R usuario:usuario projeto
```

Isso garante que o proprietário correto possa modificar os arquivos.

---

# ⚠️ Pode alterar?

| Item                    | Pode alterar? | Observação                                                         |
| ----------------------- | ------------- | ------------------------------------------------------------------ |
| Arquivos do laboratório | ✅ Sim         | Utilize-os para compreender o funcionamento dos comandos.          |
| Arquivos do sistema     | ⚠️ Não        | Evite alterar propriedades fora do laboratório durante os estudos. |

---

# 💡 Dica profissional

Sempre verifique o proprietário antes de alterar permissões.

Execute:

```bash
ls -l
```

Muitas vezes o problema não está nas permissões (`chmod`), mas sim na propriedade (`chown`).

---

# 🧠 Mentalidade Linux

Permissões e propriedade trabalham juntas.

Primeiro o Linux identifica **quem está tentando acessar o arquivo**.

Somente depois verifica **quais permissões esse usuário possui**.

Compreender essa sequência facilita muito a solução de problemas relacionados a acesso.

---

# Você sabia?

Ao copiar arquivos entre sistemas diferentes, é comum que o proprietário original não exista na máquina de destino.

Nesses casos, ajustar a propriedade utilizando `chown` costuma ser uma das primeiras tarefas realizadas pelo administrador.

---

# 🏁 Estado esperado do laboratório

Ao concluir este capítulo, a estrutura do laboratório continuará a mesma.

As alterações ocorrerão apenas nos metadados dos arquivos, caso você tenha executado os comandos com `sudo`.

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

| Comando                        | Finalidade                      |
| ------------------------------ | ------------------------------- |
| `ls -l`                        | Visualizar proprietário e grupo |
| `chown usuario arquivo`        | Alterar proprietário            |
| `chown usuario:grupo arquivo`  | Alterar proprietário e grupo    |
| `chgrp grupo arquivo`          | Alterar apenas o grupo          |
| `chown -R usuario:grupo pasta` | Alterar recursivamente          |

---

# Erros comuns

* Alterar permissões quando o problema é a propriedade do arquivo.
* Utilizar `chown -R` sem verificar o diretório informado.
* Esquecer que `chown` normalmente exige privilégios administrativos.
* Confundir proprietário com grupo.

---

# Referências

* GNU Coreutils
* Linux Foundation
* Ubuntu Documentation

---

# Conclusão

Neste capítulo você aprendeu como visualizar e alterar o proprietário e o grupo de arquivos utilizando os comandos `chown` e `chgrp`.

Também compreendeu que a propriedade faz parte do modelo de segurança do Linux e trabalha em conjunto com as permissões para controlar o acesso aos recursos do sistema.

---

# 🔗 Revisite este conceito

Nos capítulos anteriores você aprendeu a interpretar e modificar permissões.

Agora completou o modelo básico de segurança do Linux, entendendo também quem é o proprietário de cada arquivo e a qual grupo ele pertence.

Esses conceitos são fundamentais para administrar servidores e ambientes multiusuário.

---

# Prepare-se para o próximo capítulo

Agora que você domina permissões tradicionais e propriedade de arquivos, conheceremos recursos especiais do sistema de arquivos Linux.

No próximo capítulo estudaremos:

* **SUID (Set User ID)**
* **SGID (Set Group ID)**
* **Sticky Bit**

Essas permissões especiais são amplamente utilizadas em sistemas Linux e ajudam a controlar cenários específicos de execução e compartilhamento de arquivos.

---

# 📈 Evolução do Laboratório de Segurança

## Competências conquistadas

Até este momento você já domina:

* ✅ Preparar o Laboratório de Segurança.
* ✅ Interpretar permissões de arquivos e diretórios.
* ✅ Alterar permissões utilizando `chmod`.
* ✅ Utilizar permissões simbólicas e octais.
* ✅ Identificar o proprietário de um arquivo.
* ✅ Identificar o grupo associado.
* ✅ Alterar proprietário com `chown`.
* ✅ Alterar grupo com `chgrp`.
* ✅ Compreender como permissões e propriedade trabalham em conjunto.

Seu Laboratório de Segurança está pronto para explorar as permissões especiais do Linux, tema do próximo capítulo.

