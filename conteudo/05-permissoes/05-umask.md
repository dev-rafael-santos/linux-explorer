# 05. Umask — Permissões Padrão

────────────────────────────────────────────

**Nível:** Intermediário

**Tempo estimado:** 50 minutos

**Pré-requisitos:**

- Capítulo 01 — Entendendo Permissões
- Capítulo 02 — Alterando Permissões com chmod
- Capítulo 03 — Propriedade com chown e chgrp
- Capítulo 04 — Permissões Especiais

────────────────────────────────────────────

# Visão Geral

Até agora você aprendeu como alterar permissões utilizando o comando `chmod`.

Mas existe uma pergunta importante:

> Por que um arquivo recém-criado já possui permissões específicas?

A resposta está no **umask**.

O umask define quais permissões serão removidas automaticamente quando novos arquivos e diretórios forem criados.

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

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

- Entender o que é umask.
- Consultar o valor atual.
- Alterar temporariamente o umask.
- Compreender como o umask influencia novos arquivos.
- Calcular permissões padrão.

---

# Por que isso é importante?

Imagine um servidor onde todos os arquivos novos fossem criados com permissão total.

Qualquer usuário poderia alterá-los.

O umask evita exatamente esse tipo de problema.

Ele ajuda a tornar o sistema seguro desde a criação dos arquivos.

---

# Quando você usará isso?

Você utilizará o umask para:

- configurar servidores;
- preparar ambientes corporativos;
- definir políticas de segurança;
- automatizar criação de arquivos.

---

# Você vai conhecer

| Comando | Finalidade |
|----------|------------|
| `umask` | Mostrar configuração atual |
| `umask valor` | Alterar temporariamente |

---

# Consultando o umask

Execute:

```bash
umask
```

Resultado comum:

```text
0022
```

Esse número determina quais permissões serão removidas durante a criação de novos arquivos e diretórios.

---

# Como funciona?

O Linux parte das permissões máximas:

Arquivos:

```text
666
```

Diretórios:

```text
777
```

Depois aplica o valor do umask.

Exemplo:

```text
666
-022
----
644
```

Resultado:

```text
-rw-r--r--
```

Agora para diretórios:

```text
777
-022
----
755
```

Resultado:

```text
drwxr-xr-x
```

---

# Alterando temporariamente

Execute:

```bash
umask 077
```

Agora crie um arquivo:

```bash
touch testes/arquivo-privado.txt
```

Confira:

```bash
ls -l testes/arquivo-privado.txt
```

Resultado esperado:

```text
-rw-------
```

Observe que apenas o proprietário possui acesso.

---

# Restaurando

Retorne ao valor anterior:

```bash
umask 022
```

Agora crie outro arquivo:

```bash
touch testes/arquivo-publico.txt
```

Confira:

```bash
ls -l testes/arquivo-publico.txt
```

Resultado esperado:

```text
-rw-r--r--
```

---

# Entendendo o cálculo

Valores comuns:

| Umask | Arquivos | Diretórios |
|--------|----------|------------|
| 022 | 644 | 755 |
| 027 | 640 | 750 |
| 077 | 600 | 700 |

Esses são os valores encontrados com maior frequência em ambientes Linux.

---

# Antes e depois

Antes:

```bash
umask
```

```text
0022
```

Depois:

```bash
umask 077
```

Novo arquivo:

```text
-rw-------
```

Observe como apenas alterar o umask modifica automaticamente as permissões dos próximos arquivos criados.

---

# 🧠 Como o Linux enxerga isso?

O umask não altera arquivos existentes.

Ele apenas define quais permissões serão removidas quando um novo arquivo ou diretório for criado.

Por isso ele influencia apenas objetos criados após sua alteração.

---

# O que normalmente você encontrará aqui?

Durante sua rotina profissional verá valores como:

```text
022
027
077
```

Cada organização define o valor mais adequado conforme sua política de segurança.

---

# Comparando com Windows

| Windows | Linux |
|----------|--------|
| Modelo de segurança padrão | `umask` |
| Permissões iniciais | Permissões definidas pelo `umask` |

---

# 🛠️ Ferramentas que utilizam o `umask`

O `umask` é utilizado por praticamente todos os processos que criam arquivos e diretórios no Linux, incluindo:

* Shell (Bash, Zsh e outros)
* OpenSSH
* Apache
* Nginx
* Docker
* Kubernetes
* Scripts Shell
* Aplicações desenvolvidas em Python, Java, PHP, Node.js e outras linguagens

Sempre que um arquivo ou diretório é criado, o sistema considera o valor atual do `umask`.

---

# Pratique

Entre no laboratório:

```bash id="8y6kgq"
cd ~/linux-explorer-lab/seguranca
```

Verifique o valor atual:

```bash id="uqhm5d"
umask
```

Crie um arquivo:

```bash id="zn9n0y"
touch testes/exemplo-umask.txt
```

Confira suas permissões:

```bash id="jupk7r"
ls -l testes/exemplo-umask.txt
```

Agora crie um diretório:

```bash id="hm0vye"
mkdir testes/diretorio-umask
```

Confira:

```bash id="1gvlwz"
ls -ld testes/diretorio-umask
```

Compare as permissões entre o arquivo e o diretório.

---

# 🧪 Experimento

Altere temporariamente o `umask`:

```bash id="r5lhb9"
umask 077
```

Crie um novo arquivo:

```bash id="a7w3jr"
touch testes/arquivo-restrito.txt
```

Agora um diretório:

```bash id="3n0htz"
mkdir testes/diretorio-restrito
```

Confira:

```bash id="v6d0fi"
ls -l testes/arquivo-restrito.txt
```

```bash id="k6jafl"
ls -ld testes/diretorio-restrito
```

Depois restaure o valor original:

```bash id="vuw1qk"
umask 022
```

---

# 📊 Como calcular o umask

O Linux parte sempre das permissões máximas.

Para arquivos:

```text id="4b4o0t"
666
```

Para diretórios:

```text id="hzcc4x"
777
```

Depois subtrai o valor do `umask`.

### Exemplo com `022`

Arquivos:

```text id="hjgq8m"
666
-022
----
644
```

Diretórios:

```text id="t0r0ol"
777
-022
----
755
```

### Exemplo com `077`

Arquivos:

```text id="lypxte"
666
-077
----
600
```

Diretórios:

```text id="xr2hxs"
777
-077
----
700
```

---

# Explore

Experimente responder antes de calcular.

Qual será a permissão de um novo arquivo se o `umask` for:

```text id="65ts9u"
027
```

E de um diretório?

Depois utilize a tabela anterior para conferir sua resposta.

Esse exercício ajuda a compreender o cálculo sem decorar resultados.

---

# 💼 Exemplos do mundo real

Em servidores corporativos é comum utilizar:

```text id="fllwqg"
027
```

Assim, novos arquivos ficam acessíveis apenas ao proprietário e ao grupo.

Já servidores com informações altamente sensíveis costumam utilizar:

```text id="qefbr2"
077
```

Nesse cenário, apenas o proprietário possui acesso aos novos arquivos.

---

# ⚠️ Pode alterar?

| Item                    | Pode alterar? | Observação                                               |
| ----------------------- | ------------- | -------------------------------------------------------- |
| `umask` da sessão atual | ✅ Sim         | A alteração vale apenas para a sessão atual do Terminal. |
| Arquivos do laboratório | ✅ Sim         | Utilize-os livremente para os testes.                    |

Evite alterar arquivos de configuração do sistema relacionados ao `umask` durante os estudos.

---

# 💡 Dica profissional

Sempre que precisar entender por que um arquivo nasceu com determinada permissão, verifique primeiro:

```bash id="hq4gkk"
umask
```

Em muitos casos, a resposta estará ali.

---

# 🧠 Mentalidade Linux

O `umask` não concede permissões.

Ele **remove** permissões das configurações máximas padrão.

Essa diferença de interpretação é fundamental para compreender corretamente seu funcionamento.

---

# Você sabia?

O valor configurado com `umask` normalmente vale apenas para a sessão atual do Terminal.

Para torná-lo permanente, costuma-se configurá-lo em arquivos como:

```text id="x0o4ks"
~/.bashrc
```

ou

```text id="jw4nqu"
/etc/profile
```

dependendo da distribuição Linux e da política adotada.

---

# 🏁 Estado esperado do laboratório

Ao concluir este capítulo, o Laboratório de Segurança deverá conter novos arquivos e diretórios criados durante os experimentos.

Exemplo:

```text id="rkox8r"
linux-explorer-lab
│
└── seguranca
    └── testes
        ├── arquivo-privado.txt
        ├── arquivo-publico.txt
        ├── exemplo-umask.txt
        ├── arquivo-restrito.txt
        ├── diretorio-umask
        └── diretorio-restrito
```

---

# ⚡ Valores de umask mais comuns

| Umask | Arquivos | Diretórios | Cenário                      |
| ----: | :------: | :--------: | ---------------------------- |
| `022` |   `644`  |    `755`   | Uso geral                    |
| `027` |   `640`  |    `750`   | Ambientes corporativos       |
| `077` |   `600`  |    `700`   | Ambientes com alta restrição |

---

# Resumo rápido

| Comando     | Finalidade                             |
| ----------- | -------------------------------------- |
| `umask`     | Exibir valor atual                     |
| `umask 022` | Definir permissões padrão comuns       |
| `umask 027` | Restringir acesso aos outros usuários  |
| `umask 077` | Permitir acesso apenas ao proprietário |

---

# Erros comuns

* Pensar que o `umask` altera arquivos já existentes.
* Esquecer de restaurar o valor original após os testes.
* Confundir o cálculo das permissões de arquivos com o de diretórios.
* Interpretar o `umask` como permissões concedidas, quando na verdade ele remove permissões.

---

# Referências

* GNU Coreutils
* Linux Foundation
* Bash Manual
* Ubuntu Documentation

---

# Conclusão

Neste capítulo você aprendeu como o `umask` influencia as permissões atribuídas automaticamente a novos arquivos e diretórios.

Também compreendeu como calcular essas permissões e como alterar temporariamente o comportamento do sistema durante uma sessão.

---

# 🔗 Revisite este conceito

Até aqui você aprendeu:

* interpretar permissões;
* alterar permissões;
* alterar proprietário e grupo;
* utilizar permissões especiais;
* definir permissões padrão com `umask`.

Você já domina praticamente todo o modelo clássico de permissões do Linux.

---

# Prepare-se para o próximo capítulo

Agora avançaremos para um recurso mais moderno e flexível:

* **ACL (Access Control Lists)**

As ACLs permitem conceder permissões específicas para usuários e grupos sem alterar o proprietário do arquivo nem depender apenas das permissões tradicionais.

---

# 📈 Evolução do Laboratório de Segurança

## Competências conquistadas

Até este momento você já domina:

* ✅ Interpretar permissões de arquivos e diretórios.
* ✅ Alterar permissões com `chmod`.
* ✅ Alterar proprietário e grupo.
* ✅ Aplicar permissões especiais.
* ✅ Compreender o funcionamento do `umask`.
* ✅ Calcular permissões padrão para novos arquivos e diretórios.
* ✅ Configurar temporariamente o `umask` durante uma sessão.

Seu Laboratório de Segurança agora cobre praticamente todos os mecanismos clássicos de controle de acesso disponíveis no Linux.

