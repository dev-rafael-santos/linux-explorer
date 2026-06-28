# 06. ACLs — Controle de Acesso Avançado

────────────────────────────────────────────

**Nível:** Avançado

**Tempo estimado:** 60 minutos

**Pré-requisitos:**

- Capítulo 01 — Entendendo Permissões
- Capítulo 02 — Alterando Permissões com chmod
- Capítulo 03 — Propriedade com chown e chgrp
- Capítulo 04 — Permissões Especiais
- Capítulo 05 — Umask

────────────────────────────────────────────

# Visão Geral

O modelo tradicional de permissões do Linux funciona muito bem na maioria dos casos.

Entretanto, existem situações em que ele não oferece flexibilidade suficiente.

Imagine que um arquivo pertença ao usuário **rafa** e ao grupo **financeiro**.

Agora imagine que apenas o usuário **joao** também precise acessar esse arquivo.

Você poderia alterar o grupo?

Poderia mudar o proprietário?

Talvez isso não seja desejável.

É justamente para resolver esse tipo de situação que existem as **ACLs (Access Control Lists)**.

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
ls -l documentos
```

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

- Compreender o conceito de ACL.
- Visualizar ACLs existentes.
- Criar permissões específicas para usuários.
- Criar permissões específicas para grupos.
- Remover ACLs.
- Configurar ACLs padrão em diretórios.

---

# Por que isso é importante?

As ACLs permitem criar regras muito mais específicas do que o modelo tradicional.

Em vez de trabalhar apenas com:

- proprietário;
- grupo;
- outros;

você poderá conceder acesso individual para usuários e grupos específicos.

Isso aumenta bastante a flexibilidade do sistema.

---

# Quando você usará isso?

ACLs são muito utilizadas em:

- servidores de arquivos;
- ambientes corporativos;
- diretórios compartilhados;
- projetos colaborativos;
- universidades;
- empresas com muitos usuários.

---

# Você vai conhecer

| Comando | Finalidade |
|----------|------------|
| `getfacl` | Visualizar ACLs |
| `setfacl` | Criar ou alterar ACLs |

---

# O que é uma ACL?

ACL significa:

```text
Access Control List
```

Ela permite adicionar permissões específicas para usuários ou grupos sem modificar o proprietário do arquivo.

Visualmente:

```text
Arquivo
│
├── Proprietário
├── Grupo
├── Outros
└── ACL
     ├── João
     ├── Maria
     └── Equipe TI
```

---

# Verificando ACLs

Execute:

```bash
getfacl documentos/relatorio.txt
```

Resultado semelhante:

```text
# file: relatorio.txt
# owner: rafa
# group: rafa

user::rw-
group::r--
other::r--
```

Inicialmente o arquivo possui apenas as permissões tradicionais.

---

# Adicionando uma ACL

Exemplo:

```bash
sudo setfacl -m u:joao:r documentos/relatorio.txt
```

Significado:

| Opção | Função |
|--------|---------|
| `-m` | Modificar ACL |
| `u` | Usuário |
| `joao` | Nome do usuário |
| `r` | Permissão concedida |

---

# Visualizando novamente

Execute:

```bash
getfacl documentos/relatorio.txt
```

Agora aparecerá algo semelhante:

```text
user:joao:r--
```

Observe que apenas o usuário informado recebeu essa permissão adicional.

---

# ACL para grupos

Também é possível conceder permissões para grupos.

Exemplo:

```bash
sudo setfacl -m g:financeiro:rw documentos/relatorio.txt
```

Assim, todos os integrantes do grupo **financeiro** receberão essas permissões.

---

# Removendo ACLs

Para remover uma ACL específica:

```bash
sudo setfacl -x u:joao documentos/relatorio.txt
```

Depois confira novamente utilizando:

```bash
getfacl documentos/relatorio.txt
```

---

# ACL padrão

Também é possível definir ACLs que serão herdadas automaticamente por novos arquivos criados em um diretório.

Exemplo:

```bash
sudo setfacl -d -m g:financeiro:rwx compartilhados
```

Todo novo arquivo criado nesse diretório herdará essa ACL.

---

# 🧠 Como o Linux enxerga isso?

Quando um arquivo possui ACLs, o Kernel verifica:

1. Proprietário.
2. ACL específica do usuário.
3. Grupo.
4. ACL de grupos.
5. Outros.

Ou seja, as ACLs complementam o modelo tradicional de permissões.

---

# O que normalmente você encontrará aqui?

Durante sua rotina profissional verá comandos como:

```bash
getfacl arquivo
```

```bash
setfacl -m u:usuario:rw arquivo
```

```bash
setfacl -d -m g:grupo:rwx diretorio
```

Esses comandos são muito comuns em servidores de arquivos.

---

# Comparando com Windows

| Windows | Linux |
|----------|--------|
| Permissões avançadas | ACL |
| Usuários específicos | `setfacl` |
| Exibir permissões detalhadas | `getfacl` |

---

# 🛠️ Ferramentas que utilizam ACLs

As ACLs são amplamente utilizadas por aplicações e serviços que necessitam de controle refinado de acesso, como:

* Samba
* NFS
* Servidores de arquivos
* PostgreSQL
* Ambientes corporativos
* Universidades
* Diretórios compartilhados
* Sistemas de armazenamento em rede (NAS)

Sempre que diferentes usuários precisam acessar os mesmos arquivos com permissões distintas, as ACLs costumam ser a melhor solução.

---

# 📦 Verificando se as ACLs estão disponíveis

Em muitas distribuições Linux, os comandos `getfacl` e `setfacl` fazem parte do pacote **acl**.

Verifique se eles estão instalados:

```bash id="3r9z4f"
which getfacl
```

```bash id="7r1xuv"
which setfacl
```

Caso não estejam disponíveis, instale o pacote correspondente à sua distribuição.

Exemplos:

Ubuntu/Debian:

```bash id="3n5r2d"
sudo apt install acl
```

Fedora:

```bash id="m1p9sx"
sudo dnf install acl
```

Arch Linux:

```bash id="o3a7lc"
sudo pacman -S acl
```

---

# Pratique

Entre no laboratório:

```bash id="6xv2we"
cd ~/linux-explorer-lab/seguranca
```

Visualize as ACLs atuais:

```bash id="a9c4km"
getfacl documentos/relatorio.txt
```

Caso exista outro usuário em seu sistema, conceda permissão de leitura:

```bash id="6y2k7m"
sudo setfacl -m u:usuario:r documentos/relatorio.txt
```

Confira novamente:

```bash id="n7k5pq"
getfacl documentos/relatorio.txt
```

Observe a nova entrada adicionada à ACL.

---

# 🧪 Experimento

> **Observação:** este experimento exige a existência de outro usuário no sistema e permissões administrativas (`sudo`).

Adicione permissão de leitura e escrita:

```bash id="2p4k8r"
sudo setfacl -m u:usuario:rw documentos/relatorio.txt
```

Visualize:

```bash id="g4h8zf"
getfacl documentos/relatorio.txt
```

Agora remova a ACL:

```bash id="m9w3ta"
sudo setfacl -x u:usuario documentos/relatorio.txt
```

Confira novamente:

```bash id="t2j6qy"
getfacl documentos/relatorio.txt
```

Observe que apenas a entrada correspondente ao usuário foi removida.

---

# Explore

Caso seu ambiente possua múltiplos usuários, experimente:

* conceder acesso apenas para um usuário específico;
* conceder acesso para um grupo;
* remover as ACLs;
* comparar a saída do `ls -l` com a do `getfacl`.

Perceba que o `ls -l` continua mostrando apenas as permissões tradicionais, enquanto o `getfacl` apresenta as regras completas.

---

# 💼 Exemplos do mundo real

Imagine um departamento financeiro.

O diretório pertence ao grupo **financeiro**, mas o auditor externo precisa consultar apenas um relatório específico.

Em vez de alterar o grupo do arquivo ou conceder acesso para todos, basta criar uma ACL para esse usuário.

Outro exemplo ocorre em universidades, onde professores, monitores e alunos precisam de diferentes níveis de acesso ao mesmo diretório.

---

# ⚠️ Pode alterar?

| Item                    | Pode alterar? | Observação                                                 |
| ----------------------- | ------------- | ---------------------------------------------------------- |
| Arquivos do laboratório | ✅ Sim         | Utilize-os para experimentar ACLs.                         |
| Diretórios do sistema   | ⚠️ Não        | Evite alterar ACLs fora do laboratório durante os estudos. |

---

# 💡 Dica profissional

Quando um arquivo possuir ACLs, o comando:

```bash id="5k2n8v"
ls -l
```

normalmente exibirá um sinal de **`+`** ao final das permissões.

Exemplo:

```text id="c8m5yx"
-rw-r--r--+
```

Esse pequeno detalhe indica que existem permissões adicionais configuradas através de ACL.

---

# 🧠 Mentalidade Linux

As ACLs existem para resolver casos específicos.

Antes de utilizá-las, pergunte:

* As permissões tradicionais resolvem o problema?
* Basta alterar o grupo?
* A ACL realmente é necessária?

Na maioria dos casos simples, `chmod` e `chown` são suficientes.

As ACLs devem ser utilizadas quando há necessidade de um controle mais refinado.

---

# Você sabia?

As ACLs são compatíveis com diversos sistemas de arquivos modernos, como:

* ext4
* XFS
* Btrfs

Entretanto, alguns sistemas de arquivos antigos ou dispositivos montados com determinadas opções podem não oferecer suporte completo.

---

# 🏁 Estado esperado do laboratório

Ao concluir este capítulo, a estrutura do Laboratório de Segurança permanecerá a mesma.

As alterações ocorrerão apenas nas permissões estendidas dos arquivos utilizados durante os experimentos.

```text id="4z6k3q"
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

# ⚡ ACLs mais comuns

| Situação                   | Comando                               |
| -------------------------- | ------------------------------------- |
| Exibir ACL                 | `getfacl arquivo`                     |
| Adicionar ACL para usuário | `setfacl -m u:usuario:r arquivo`      |
| Adicionar ACL para grupo   | `setfacl -m g:grupo:rw arquivo`       |
| Remover ACL                | `setfacl -x u:usuario arquivo`        |
| ACL padrão em diretório    | `setfacl -d -m g:grupo:rwx diretorio` |

---

# Resumo rápido

| Comando                               | Finalidade                 |
| ------------------------------------- | -------------------------- |
| `getfacl arquivo`                     | Exibir ACL                 |
| `setfacl -m u:usuario:rw arquivo`     | Adicionar ACL para usuário |
| `setfacl -m g:grupo:r arquivo`        | Adicionar ACL para grupo   |
| `setfacl -x u:usuario arquivo`        | Remover ACL                |
| `setfacl -d -m g:grupo:rwx diretorio` | Definir ACL padrão         |

---

# Erros comuns

* Utilizar ACL quando as permissões tradicionais já resolvem o problema.
* Esquecer de verificar se o pacote `acl` está instalado.
* Alterar ACLs sem conferir o resultado com `getfacl`.
* Não perceber o sinal `+` exibido pelo `ls -l`.

---

# Referências

* Linux Foundation
* GNU Coreutils
* `man getfacl`
* `man setfacl`
* Ubuntu Documentation

---

# Conclusão

Neste capítulo você aprendeu a utilizar **ACLs (Access Control Lists)** para conceder permissões específicas a usuários e grupos, sem alterar o proprietário ou depender apenas das permissões tradicionais.

As ACLs complementam o modelo clássico de segurança do Linux e são muito utilizadas em ambientes corporativos e servidores de arquivos.

---

# 🔗 Revisite este conceito

Até aqui você estudou:

* Permissões tradicionais (`chmod`)
* Propriedade (`chown` e `chgrp`)
* Permissões especiais (SUID, SGID e Sticky Bit)
* `umask`
* ACLs

Agora você domina praticamente todos os mecanismos de controle de acesso disponíveis no Linux para arquivos e diretórios.

---

# Prepare-se para o próximo capítulo

No próximo capítulo reuniremos todo esse conhecimento para estudar **Boas Práticas de Segurança**.

Você aprenderá recomendações utilizadas por administradores de sistemas para evitar erros comuns, proteger arquivos importantes e configurar ambientes Linux de forma mais segura.

---

# 📈 Evolução do Laboratório de Segurança

## Competências conquistadas

Até este momento você já domina:

* ✅ Interpretar permissões tradicionais.
* ✅ Alterar permissões com `chmod`.
* ✅ Alterar proprietário e grupo.
* ✅ Aplicar permissões especiais.
* ✅ Configurar o `umask`.
* ✅ Utilizar ACLs para usuários e grupos específicos.
* ✅ Identificar arquivos com ACLs utilizando `ls -l` e `getfacl`.

Seu Laboratório de Segurança agora representa praticamente todos os mecanismos clássicos e avançados de controle de acesso encontrados em ambientes Linux profissionais.

