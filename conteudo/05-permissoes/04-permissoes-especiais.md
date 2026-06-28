# 04. Permissões Especiais

────────────────────────────────────────────

**Nível:** Intermediário

**Tempo estimado:** 60 minutos

**Pré-requisitos:**

- Capítulo 01 — Entendendo Permissões
- Capítulo 02 — Alterando Permissões com chmod
- Capítulo 03 — Propriedade com chown e chgrp

────────────────────────────────────────────

# Visão Geral

Até agora você conheceu as permissões tradicionais do Linux:

- leitura (`r`);
- escrita (`w`);
- execução (`x`).

Entretanto, o Linux possui três permissões especiais que ampliam esse modelo.

São elas:

- SUID (Set User ID)
- SGID (Set Group ID)
- Sticky Bit

Essas permissões são muito utilizadas em ambientes profissionais e ajudam a controlar situações específicas de segurança e compartilhamento de arquivos.

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

Visualize as permissões atuais:

```bash
ls -l scripts
```

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

- Identificar permissões especiais.
- Aplicar SUID.
- Aplicar SGID.
- Aplicar Sticky Bit.
- Interpretar a saída do comando `ls -l`.

---

# Por que isso é importante?

As permissões especiais resolvem situações que não podem ser tratadas apenas com `r`, `w` e `x`.

Elas permitem controlar a execução de programas e o compartilhamento seguro de diretórios.

Por isso são amplamente utilizadas em servidores Linux.

---

# Quando você usará isso?

Você encontrará essas permissões em:

- servidores Linux;
- diretórios compartilhados;
- scripts administrativos;
- programas do sistema;
- ambientes multiusuário.

---

# Você vai conhecer

| Permissão | Finalidade |
|-----------|------------|
| SUID | Executar como proprietário |
| SGID | Executar ou herdar grupo |
| Sticky Bit | Restringir exclusão em diretórios compartilhados |

---

# O que é SUID?

SUID significa:

```text
Set User ID
```

Quando aplicado a um programa executável, ele será executado utilizando as permissões do proprietário do arquivo.

Exemplo:

```text
-rwsr-xr-x
```

Observe que o `x` do proprietário foi substituído por:

```text
s
```

---

# O que é SGID?

SGID significa:

```text
Set Group ID
```

Em arquivos executáveis, o programa será executado utilizando o grupo proprietário.

Em diretórios, novos arquivos herdarão automaticamente o grupo daquele diretório.

Exemplo:

```text
drwxrwsr-x
```

Novamente observe a letra:

```text
s
```

Agora ela aparece na posição do grupo.

---

# O que é Sticky Bit?

O Sticky Bit é utilizado principalmente em diretórios compartilhados.

Exemplo clássico:

```text
drwxrwxrwt
```

Observe a letra:

```text
t
```

Ela indica que, mesmo existindo permissão de escrita para todos, cada usuário poderá remover apenas os próprios arquivos.

---

# Como visualizar?

Execute:

```bash
ls -l
```

Alguns exemplos:

```text
-rwsr-xr-x
```

```text
drwxrwsr-x
```

```text
drwxrwxrwt
```

Essas letras substituem a permissão de execução correspondente.

---

# Antes e depois

Arquivo comum:

```text
-rwxr-xr-x
```

Aplicando SUID:

```text
-rwsr-xr-x
```

---

Diretório comum:

```text
drwxrwxr-x
```

Aplicando SGID:

```text
drwxrwsr-x
```

---

Diretório compartilhado:

```text
drwxrwxrwx
```

Aplicando Sticky Bit:

```text
drwxrwxrwt
```

Observe como apenas uma letra muda, mas o comportamento do sistema muda completamente.

---

# 🧠 Como o Linux enxerga isso?

As permissões especiais fazem parte dos metadados do arquivo.

Assim como as permissões tradicionais, elas são verificadas pelo Kernel antes da execução de programas ou do acesso aos diretórios.

Elas não substituem o modelo tradicional de permissões, mas o complementam.

---

# O que normalmente você encontrará aqui?

Durante sua rotina profissional verá situações como:

- `/usr/bin/passwd` utilizando SUID;
- diretórios compartilhados utilizando Sticky Bit;
- projetos colaborativos utilizando SGID.

Esses casos são muito comuns em servidores Linux.

---

# Comparando com Windows

| Windows | Linux |
|----------|--------|
| (Sem equivalente direto) | SUID |
| (Sem equivalente direto) | SGID |
| Pasta compartilhada protegida | Sticky Bit |

---

# 🛠️ Ferramentas que utilizam permissões especiais

As permissões especiais são utilizadas por diversos componentes do sistema operacional e aplicações, entre eles:

* OpenSSH
* Apache
* Nginx
* Docker
* PostgreSQL
* MySQL
* Samba
* Programas do sistema Linux

Embora não sejam utilizadas diariamente por todos os usuários, elas são comuns em ambientes corporativos e servidores Linux.

---

# Pratique

Entre no laboratório:

```bash id="b7pr8x"
cd ~/linux-explorer-lab/seguranca
```

Visualize as permissões atuais do script:

```bash id="1uk9ep"
ls -l scripts/backup.sh
```

Agora aplique o SUID:

```bash id="v5fwh7"
chmod u+s scripts/backup.sh
```

Confira:

```bash id="fwyu0m"
ls -l scripts/backup.sh
```

Resultado esperado:

```text id="ewtk1j"
-rwsr-xr-x
```

Agora remova o SUID:

```bash id="sq9l31"
chmod u-s scripts/backup.sh
```

Confira novamente:

```bash id="jmywtx"
ls -l scripts/backup.sh
```

---

# 🧪 Experimento

Crie um diretório compartilhado:

```bash id="8ey0tt"
mkdir testes/compartilhado
```

Visualize:

```bash id="5d8vvf"
ls -ld testes/compartilhado
```

Agora aplique o SGID:

```bash id="3zb3ii"
chmod g+s testes/compartilhado
```

Confira:

```bash id="9pqg3r"
ls -ld testes/compartilhado
```

Resultado esperado:

```text id="bwx0kw"
drwxrwsr-x
```

Agora aplique o Sticky Bit:

```bash id="jlwm3n"
chmod +t testes/compartilhado
```

Confira novamente:

```bash id="cg64xt"
ls -ld testes/compartilhado
```

Resultado esperado:

```text id="1cbeov"
drwxrwsr-t
```

Observe atentamente como as letras **s** e **t** aparecem substituindo a permissão de execução.

---

# Explore

Experimente responder às perguntas antes de consultar a explicação.

* Em qual posição aparece o **SUID**?
* Em qual posição aparece o **SGID**?
* Em qual posição aparece o **Sticky Bit**?
* Por que o Linux utiliza letras `s` e `t` em vez de `x`?

Depois utilize:

```bash id="ljlwm6"
ls -l scripts
```

e

```bash id="94onm4"
ls -ld testes/compartilhado
```

Tente identificar as permissões especiais apenas observando a saída.

---

# 💼 Exemplos do mundo real

O comando:

```text id="2j9rzn"
/usr/bin/passwd
```

normalmente possui SUID.

Isso permite que um usuário altere sua própria senha, mesmo que o arquivo de senhas pertença ao usuário `root`.

Outro exemplo é o diretório:

```text id="o16gh7"
/tmp
```

Normalmente ele possui Sticky Bit.

Isso impede que um usuário remova arquivos criados por outros usuários.

Projetos compartilhados frequentemente utilizam SGID para que novos arquivos pertençam automaticamente ao grupo correto.

---

# ⚠️ Pode alterar?

| Item                     | Pode alterar? | Observação                                                              |
| ------------------------ | ------------- | ----------------------------------------------------------------------- |
| Laboratório de Segurança | ✅ Sim         | Utilize livremente para experimentar.                                   |
| Diretórios do sistema    | ⚠️ Não        | Não altere permissões especiais fora do laboratório durante os estudos. |

---

# 💡 Dica profissional

Sempre utilize:

```bash id="g2f8lh"
ls -l
```

ou

```bash id="g6ghow"
ls -ld diretorio
```

após aplicar permissões especiais.

Isso permite verificar imediatamente se o resultado foi o esperado.

---

# 🧠 Mentalidade Linux

As permissões especiais existem para resolver situações muito específicas.

Na maioria dos casos, permissões tradicionais (`rwx`) são suficientes.

Quando você encontrar SUID, SGID ou Sticky Bit, pergunte primeiro:

> **Qual problema essa permissão está resolvendo?**

Essa forma de pensar ajuda a compreender sua finalidade e evita configurações desnecessárias.

---

# Você sabia?

O diretório:

```text id="9sm1zl"
/tmp
```

está presente em praticamente todas as distribuições Linux e normalmente utiliza Sticky Bit.

Ele permite que diversos usuários criem arquivos temporários no mesmo local, mas impede que um usuário exclua arquivos pertencentes a outro.

É um excelente exemplo de aplicação prática dessa permissão especial.

---

# 🏁 Estado esperado do laboratório

Ao concluir este capítulo, o Laboratório de Segurança deverá conter o diretório de testes criado durante os experimentos.

Exemplo:

```text id="c5n0lr"
linux-explorer-lab
│
└── seguranca
    ├── compartilhados
    ├── documentos
    ├── grupos
    ├── privados
    ├── publicos
    ├── scripts
    │   └── backup.sh
    └── testes
        └── compartilhado
```

As permissões poderão variar de acordo com os comandos executados durante os exercícios.

---

# ⚡ Permissões especiais mais comuns

| Cenário                              | Permissão  |
| ------------------------------------ | ---------- |
| Programa `passwd`                    | SUID       |
| Diretório de projetos compartilhados | SGID       |
| Diretório `/tmp`                     | Sticky Bit |

---

# Resumo rápido

| Comando               | Finalidade         |
| --------------------- | ------------------ |
| `chmod u+s arquivo`   | Aplicar SUID       |
| `chmod u-s arquivo`   | Remover SUID       |
| `chmod g+s diretorio` | Aplicar SGID       |
| `chmod g-s diretorio` | Remover SGID       |
| `chmod +t diretorio`  | Aplicar Sticky Bit |
| `chmod -t diretorio`  | Remover Sticky Bit |

---

# Erros comuns

* Aplicar SUID em arquivos que não são executáveis.
* Utilizar permissões especiais sem compreender sua finalidade.
* Alterar permissões especiais em diretórios do sistema durante os estudos.
* Confundir SUID com SGID.

---

# Referências

* GNU Coreutils
* Linux Foundation
* Ubuntu Documentation
* FHS (Filesystem Hierarchy Standard)

---

# Conclusão

Neste capítulo você conheceu as permissões especiais do Linux: **SUID**, **SGID** e **Sticky Bit**.

Também aprendeu onde elas são utilizadas, como identificá-las e em quais situações fazem sentido. Embora sejam menos frequentes que as permissões tradicionais, elas desempenham um papel importante na administração de sistemas Linux.

---

# 🔗 Revisite este conceito

Agora você domina praticamente todo o modelo clássico de permissões do Linux:

* Permissões (`rwx`)
* Propriedade (`chown` e `chgrp`)
* Permissões especiais (SUID, SGID e Sticky Bit)

No próximo capítulo conheceremos o **umask**, responsável por definir as permissões padrão atribuídas a novos arquivos e diretórios.

---

# 📈 Evolução do Laboratório de Segurança

## Competências conquistadas

Até este momento você já domina:

* ✅ Interpretar permissões de arquivos e diretórios.
* ✅ Alterar permissões com `chmod`.
* ✅ Alterar proprietário e grupo.
* ✅ Aplicar permissões especiais (SUID, SGID e Sticky Bit).
* ✅ Identificar permissões especiais utilizando `ls -l`.
* ✅ Compreender cenários reais de utilização dessas permissões.

Seu Laboratório de Segurança agora reproduz diversos cenários encontrados em servidores Linux reais.

