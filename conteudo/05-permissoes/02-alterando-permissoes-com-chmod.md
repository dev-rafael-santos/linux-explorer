# 02. Alterando Permissões com chmod

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 60 minutos

**Pré-requisitos:**

- Capítulo 00 — Preparando o Laboratório de Segurança
- Capítulo 01 — Entendendo Permissões

────────────────────────────────────────────

# Visão Geral

Agora que você já sabe interpretar permissões, chegou o momento de modificá-las.

No Linux isso é feito utilizando o comando:

```bash
chmod
```

Neste capítulo você aprenderá as duas formas mais utilizadas:

- modo simbólico;
- modo numérico (octal).

Esses conhecimentos fazem parte da rotina diária de qualquer administrador Linux.

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
ls -l scripts
```

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

- Alterar permissões utilizando letras.
- Alterar permissões utilizando números.
- Compreender o significado do modo octal.
- Tornar scripts executáveis.
- Aplicar permissões com segurança.

---

# Por que isso é importante?

Criar um script não significa que ele poderá ser executado.

Criar um arquivo não significa que qualquer usuário poderá alterá-lo.

É o comando `chmod` que permite controlar essas permissões.

---

# Quando você usará isso?

Você utilizará `chmod` para:

- tornar scripts executáveis;
- proteger arquivos;
- liberar acesso;
- restringir alterações;
- configurar servidores.

---

# Você vai conhecer

| Comando | Finalidade |
|----------|------------|
| `chmod` | Alterar permissões |
| `u` | Usuário |
| `g` | Grupo |
| `o` | Outros |
| `a` | Todos |

---

# O modo simbólico

No modo simbólico utilizamos letras.

Exemplo:

```bash
chmod u+x backup.sh
```

Significado:

| Elemento | Significado |
|----------|-------------|
| `u` | Usuário |
| `+` | Adicionar |
| `x` | Execução |

---

# Antes e depois

Antes:

```bash
ls -l scripts/backup.sh
```

Resultado:

```text
-rw-r--r--
```

Agora execute:

```bash
chmod u+x scripts/backup.sh
```

Confira novamente:

```bash
ls -l scripts/backup.sh
```

Resultado:

```text
-rwxr--r--
```

Observe que apenas a permissão de execução do usuário foi adicionada.

---

# Removendo permissões

Também é possível remover permissões.

Exemplo:

```bash
chmod u-x scripts/backup.sh
```

Antes:

```text
-rwxr--r--
```

Depois:

```text
-rw-r--r--
```

---

# Adicionando permissão para todos

Execute:

```bash
chmod a+r scripts/backup.sh
```

Agora todos poderão ler o arquivo.

---

# O modo numérico (octal)

Além das letras, o Linux permite utilizar números.

Cada permissão possui um valor.

| Permissão | Valor |
|-----------|------:|
| `r` | 4 |
| `w` | 2 |
| `x` | 1 |

Esses valores são somados.

Exemplos:

| Permissão | Valor |
|-----------|------:|
| `rwx` | 7 |
| `rw-` | 6 |
| `r-x` | 5 |
| `r--` | 4 |
| `---` | 0 |

---

# Interpretando o número

Quando utilizamos:

```bash
chmod 755 arquivo
```

estamos dizendo:

```text
7   5   5
│   │   │
│   │   └── Outros
│   └────── Grupo
└────────── Usuário
```

Ou seja:

| Categoria | Permissão |
|-----------|-----------|
| Usuário | `rwx` |
| Grupo | `r-x` |
| Outros | `r-x` |

---

# Exemplo com 644

Execute:

```bash
chmod 644 scripts/backup.sh
```

Confira:

```bash
ls -l scripts/backup.sh
```

Resultado esperado:

```text
-rw-r--r--
```

---

# Exemplo com 755

Execute:

```bash
chmod 755 scripts/backup.sh
```

Confira novamente:

```bash
ls -l scripts/backup.sh
```

Resultado:

```text
-rwxr-xr-x
```

Agora o script está preparado para ser executado.

---

# 🧠 Como o Linux enxerga isso?

Quando você utiliza `chmod`, o Linux altera apenas os metadados do arquivo relacionados às permissões.

O conteúdo do arquivo permanece exatamente o mesmo.

Apenas as regras de acesso são modificadas.

---

# O que normalmente você encontrará aqui?

Durante sua rotina profissional, as permissões mais comuns serão:

| Permissão | Uso comum |
|-----------|-----------|
| `644` | Arquivos de texto |
| `755` | Scripts e diretórios |
| `600` | Arquivos privados |
| `700` | Diretórios pessoais |

---

# Comparando com Windows

| Windows | Linux |
|----------|--------|
| Marcar como executável | `chmod +x` |
| Permissões avançadas | `chmod` |
| Segurança do arquivo | Permissões `rwx` |

---

# 🛠️ Ferramentas que utilizam o `chmod`

O comando `chmod` é utilizado por praticamente todos os administradores de sistemas e diversas ferramentas, entre elas:

* Docker
* Kubernetes
* Apache
* Nginx
* Git
* Shell Scripts
* Jenkins
* Ansible
* Cron

Sempre que um script precisa ser executado ou um arquivo precisa ter seu acesso controlado, o `chmod` está presente.

---

# Pratique

Entre no laboratório:

```bash
cd ~/linux-explorer-lab/seguranca
```

Visualize as permissões atuais do script:

```bash
ls -l scripts/backup.sh
```

Resultado esperado:

```text
-rw-r--r--
```

Agora torne o script executável:

```bash
chmod u+x scripts/backup.sh
```

Confira novamente:

```bash
ls -l scripts/backup.sh
```

Resultado esperado:

```text
-rwxr--r--
```

Agora permita execução para todos:

```bash
chmod +x scripts/backup.sh
```

Confira:

```bash
ls -l scripts/backup.sh
```

Resultado esperado:

```text
-rwxr-xr-x
```

---

# 🧪 Experimento

Vamos experimentar diferentes permissões.

Primeiro:

```bash
chmod 600 scripts/backup.sh
```

Confira:

```bash
ls -l scripts/backup.sh
```

Resultado:

```text
-rw-------
```

Agora altere para:

```bash
chmod 644 scripts/backup.sh
```

Resultado:

```text
-rw-r--r--
```

Depois:

```bash
chmod 700 scripts/backup.sh
```

Resultado:

```text
-rwx------
```

Por fim:

```bash
chmod 755 scripts/backup.sh
```

Resultado:

```text
-rwxr-xr-x
```

Observe como cada número modifica completamente as permissões do arquivo.

---

# Explore

Experimente responder às perguntas antes de executar os comandos.

O que acontecerá com:

```bash
chmod 777 scripts/backup.sh
```

Depois confira:

```bash
ls -l scripts/backup.sh
```

Agora faça:

```bash
chmod 640 scripts/backup.sh
```

Confira novamente.

Tente interpretar as permissões sem consultar a tabela.

Esse exercício ajuda a desenvolver rapidez na leitura do modo octal.

---

# 💼 Exemplos do mundo real

Um script de backup normalmente precisa ser executado.

Por isso é comum encontrar:

```bash
chmod 755 backup.sh
```

Já um arquivo contendo senhas ou chaves privadas costuma utilizar:

```bash
chmod 600 id_rsa
```

Assim, apenas o proprietário pode visualizar ou alterar o conteúdo.

Essas permissões são amplamente utilizadas em servidores Linux.

---

# ⚠️ Pode alterar?

| Arquivo                            | Pode alterar? | Observação                                                       |
| ---------------------------------- | ------------- | ---------------------------------------------------------------- |
| `~/linux-explorer-lab/seguranca/*` | ✅ Sim         | Ambiente criado para experimentação.                             |
| Arquivos do sistema                | ⚠️ Não        | Evite alterar permissões fora do laboratório durante os estudos. |

---

# 💡 Dica profissional

Sempre confira o resultado após utilizar o `chmod`.

Execute:

```bash
ls -l
```

Esse hábito evita configurações incorretas e facilita a identificação de erros.

---

# 🧠 Mentalidade Linux

Um profissional experiente raramente utiliza `777`.

O objetivo não é conceder todas as permissões, mas apenas as necessárias.

Esse conceito é conhecido como **Princípio do Menor Privilégio**, uma das bases da segurança em sistemas Linux.

---

# Você sabia?

O comando:

```bash
chmod +x arquivo.sh
```

é um dos mais utilizados por desenvolvedores.

Ele transforma um arquivo de texto contendo comandos em um script executável, desde que possua um interpretador válido, como:

```bash
#!/bin/bash
```

---

# 🏁 Estado esperado do laboratório

Ao concluir este capítulo, o arquivo `backup.sh` deverá estar configurado com permissão de execução.

Exemplo:

```text
linux-explorer-lab
└── seguranca
    └── scripts
        └── backup.sh
            -rwxr-xr-x
```

---

# Resumo rápido

| Comando             | Resultado                    |
| ------------------- | ---------------------------- |
| `chmod u+x arquivo` | Adiciona execução ao usuário |
| `chmod u-x arquivo` | Remove execução do usuário   |
| `chmod +x arquivo`  | Adiciona execução para todos |
| `chmod 644 arquivo` | `rw-r--r--`                  |
| `chmod 755 arquivo` | `rwxr-xr-x`                  |
| `chmod 700 arquivo` | `rwx------`                  |
| `chmod 600 arquivo` | `rw-------`                  |

---

# Erros comuns

* Utilizar `777` sem necessidade.
* Alterar permissões sem verificar o resultado.
* Confundir permissões simbólicas com octais.
* Esquecer que diretórios também possuem permissões.

---

# Referências

* GNU Coreutils
* Linux Foundation
* Ubuntu Documentation

---

# Conclusão

Neste capítulo você aprendeu a utilizar o comando `chmod` para modificar permissões utilizando tanto o modo simbólico quanto o modo numérico (octal).

Também compreendeu o significado das permissões mais utilizadas no dia a dia, como `644`, `700` e `755`, e percebeu como pequenas alterações impactam diretamente a segurança dos arquivos.

---

# 🔗 Revisite este conceito

No capítulo anterior você aprendeu a interpretar permissões.

Agora deu um passo além: passou a modificá-las conscientemente.

Essa combinação é essencial para administrar sistemas Linux com segurança.

---

# Prepare-se para o próximo capítulo

Agora que você já sabe controlar **o que** cada usuário pode fazer com um arquivo, chegou o momento de aprender **quem é o dono desse arquivo**.

No próximo capítulo conheceremos os comandos:

* `chown`
* `chgrp`

Eles permitem alterar o proprietário e o grupo de arquivos e diretórios, complementando o modelo de permissões do Linux.

---

# 📈 Evolução do Laboratório de Segurança

## Competências conquistadas

Até este momento você já domina:

* ✅ Preparar o Laboratório de Segurança.
* ✅ Interpretar permissões de arquivos e diretórios.
* ✅ Alterar permissões utilizando o modo simbólico.
* ✅ Alterar permissões utilizando o modo octal.
* ✅ Tornar scripts executáveis.
* ✅ Aplicar permissões comuns como `600`, `644`, `700` e `755`.
* ✅ Compreender a importância do Princípio do Menor Privilégio.

Seu Laboratório de Segurança agora está preparado para os próximos estudos sobre propriedade de arquivos e grupos.

