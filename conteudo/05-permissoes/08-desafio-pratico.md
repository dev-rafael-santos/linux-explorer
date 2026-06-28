# 08. Desafio Prático — Administrando Permissões em um Servidor Linux

────────────────────────────────────────────

**Nível:** Intermediário / Avançado

**Tempo estimado:** 90 minutos

**Pré-requisitos:**

- Conclusão de todos os capítulos deste módulo.

────────────────────────────────────────────

# Missão

Parabéns!

Você acaba de ser contratado como Administrador Linux da empresa **Linux Explorer Solutions**.

Sua primeira tarefa é organizar um pequeno servidor utilizado por diferentes equipes.

Cada departamento possui necessidades específicas de acesso.

Sua missão será configurar corretamente permissões, proprietários, grupos e políticas de segurança.

Durante este desafio você utilizará praticamente tudo o que aprendeu neste módulo.

---

# Objetivos

Ao concluir este desafio você será capaz de:

- interpretar permissões;
- utilizar chmod;
- utilizar chown;
- utilizar chgrp;
- aplicar permissões especiais;
- utilizar umask;
- utilizar ACLs;
- escolher a configuração mais segura para cada situação.

---

# Cenário

A empresa possui a seguinte estrutura:

```text
empresa
│
├── financeiro
│   ├── folha-pagamento.xlsx
│   └── impostos.xlsx
│
├── desenvolvimento
│   ├── api.py
│   ├── backend.js
│   └── README.md
│
├── scripts
│   ├── backup.sh
│   └── deploy.sh
│
├── compartilhado
│
├── temporarios
│
└── chaves
    └── id_rsa
```

Seu trabalho será preparar esse ambiente.

---

# Preparando o laboratório

Entre no Laboratório de Segurança:

```bash
cd ~/linux-explorer-lab/seguranca
```

Crie toda a estrutura:

```bash
mkdir -p empresa/{financeiro,desenvolvimento,scripts,compartilhado,temporarios,chaves}
```

Crie os arquivos:

```bash
touch empresa/financeiro/folha-pagamento.xlsx

touch empresa/financeiro/impostos.xlsx

touch empresa/desenvolvimento/api.py

touch empresa/desenvolvimento/backend.js

touch empresa/desenvolvimento/README.md

touch empresa/scripts/backup.sh

touch empresa/scripts/deploy.sh

touch empresa/chaves/id_rsa
```

Confira:

```bash
tree empresa
```

---

# Como funcionará o desafio?

O desafio será dividido em quatro fases.

Cada fase aumenta um pouco a dificuldade.

Sempre tente resolver sozinho.

Caso tenha dificuldade, consulte a dica.

Somente depois veja a solução comentada.

O objetivo não é acertar de primeira.

O objetivo é aprender a pensar como um administrador Linux.

---

# Fase 1 — Primeiros ajustes

## Situação

Os scripts da empresa precisam ser executáveis.

Atualmente eles são apenas arquivos comuns.

---

## Objetivo

Configure os dois scripts para que possam ser executados normalmente.

Arquivos:

```text
empresa/scripts/backup.sh

empresa/scripts/deploy.sh
```

---

## Dica

Pergunte a si mesmo:

> Qual comando adiciona permissão de execução?

> Essa permissão deve ser concedida apenas ao proprietário ou também ao grupo?

Tente resolver antes de continuar.

---

## ✋ Pare aqui

Resolva sozinho.

Somente depois avance para a solução.

---

# ✅ Solução comentada

Os scripts precisam ser executáveis.

Uma configuração bastante comum para esse cenário é:

```bash
chmod 755 empresa/scripts/*.sh
```

Confira o resultado:

```bash
ls -l empresa/scripts
```

Resultado esperado:

```text
-rwxr-xr-x backup.sh
-rwxr-xr-x deploy.sh
```

### Por que utilizar 755?

| Permissão | Motivo |
|-----------|--------|
| Usuário | Pode ler, alterar e executar |
| Grupo | Pode ler e executar |
| Outros | Pode ler e executar |

Essa é uma configuração bastante utilizada para scripts que podem ser executados por outros usuários, mas modificados apenas pelo proprietário.

---

# Fase 2 — Protegendo informações confidenciais

## Situação

O diretório **chaves** contém uma chave SSH privada.

Esse arquivo nunca deve ficar acessível para outros usuários.

Arquivo:

```text
empresa/chaves/id_rsa
```

---

## Objetivo

Configure a permissão mais adequada para esse arquivo.

---

## Dica

Lembre-se:

Uma chave privada deve ser acessível apenas pelo proprietário.

Qual permissão estudamos para esse caso?

---

## ✋ Pare aqui

Resolva sozinho antes de continuar.

---

# ✅ Solução comentada

```bash
chmod 600 empresa/chaves/id_rsa
```

Confira:

```bash
ls -l empresa/chaves
```

Resultado esperado:

```text
-rw-------
```

### Por que 600?

O proprietário pode:

- Ler
- Alterar

Grupo:

- Nenhum acesso

Outros:

- Nenhum acesso

Esse é o padrão recomendado para chaves SSH privadas.

---

# Fase 3 — Diretório Compartilhado

## Situação

A equipe de desenvolvimento trabalha em conjunto.

Todos os arquivos criados no diretório:

```text
empresa/compartilhado
```

devem pertencer automaticamente ao mesmo grupo.

---

## Objetivo

Configure o diretório para herdar automaticamente o grupo.

---

## Dica

Qual permissão especial faz isso?

- SUID?
- SGID?
- Sticky Bit?

---

## ✋ Pare aqui

Tente resolver antes de continuar.

---

# ✅ Solução comentada

```bash
chmod g+s empresa/compartilhado
```

Confira:

```bash
ls -ld empresa/compartilhado
```

Resultado esperado:

```text
drwxrwsr-x
```

### O que aconteceu?

Todo arquivo criado dentro desse diretório herdará automaticamente o grupo do diretório.

Essa configuração é muito utilizada em equipes de desenvolvimento.

---

# 📈 Sua evolução até aqui

Você já conseguiu resolver problemas envolvendo:

- scripts executáveis;
- proteção de arquivos sensíveis;
- diretórios compartilhados.

Agora vem a missão final.

Até aqui você recebeu ajuda.

Na próxima etapa você resolverá praticamente sozinho.

Boa sorte! 

---

# 🏢 Missão Final — Você é o Administrador Linux

Agora é com você.

Imagine que o ambiente da empresa acabou de ser criado.

Seu gerente deixou as seguintes instruções:

## Requisitos

Configure o ambiente para atender às seguintes regras:

### 1. Scripts

Os arquivos:

```text
empresa/scripts/backup.sh

empresa/scripts/deploy.sh
```

devem ser executáveis.

---

### 2. Chave SSH

O arquivo:

```text
empresa/chaves/id_rsa
```

deve ser acessível apenas pelo proprietário.

---

### 3. Diretório Compartilhado

O diretório:

```text
empresa/compartilhado
```

deve herdar automaticamente o grupo dos novos arquivos.

---

### 4. Diretório Temporário

O diretório:

```text
empresa/temporarios
```

deve permitir que vários usuários criem arquivos, mas cada usuário só poderá remover seus próprios arquivos.

---

### 5. Relatório Financeiro

O arquivo:

```text
empresa/financeiro/folha-pagamento.xlsx
```

deve permitir leitura apenas ao proprietário e ao grupo.

---

### 6. README

O arquivo:

```text
empresa/desenvolvimento/README.md
```

deve ser somente leitura para grupo e outros usuários.

---

### 7. ACL

Caso exista outro usuário no sistema, conceda apenas leitura ao usuário para o arquivo:

```text
empresa/financeiro/impostos.xlsx
```

utilizando ACL.

---

# ✋ Pare aqui

Resolva toda a missão sozinho.

Não continue até terminar.

O objetivo é utilizar apenas aquilo que você aprendeu durante o módulo.

---

# ✅ Checklist

Antes de consultar a solução, responda:

- [ ] Os scripts executam?
- [ ] A chave SSH está protegida?
- [ ] O diretório compartilhado utiliza SGID?
- [ ] O diretório temporário utiliza Sticky Bit?
- [ ] O relatório financeiro possui permissão adequada?
- [ ] O README está protegido?
- [ ] A ACL foi criada corretamente?
- [ ] Você conferiu todas as permissões utilizando `ls -l` ou `getfacl`?

Se respondeu "sim" para todas, ótimo!

Agora compare com a solução.

---

# ✅ Solução comentada

## Scripts

```bash
chmod 755 empresa/scripts/*.sh
```

Permite execução para todos e escrita apenas para o proprietário.

---

## Chave SSH

```bash
chmod 600 empresa/chaves/id_rsa
```

Somente o proprietário pode ler e modificar.

---

## Diretório Compartilhado

```bash
chmod g+s empresa/compartilhado
```

Novos arquivos herdarão automaticamente o grupo.

---

## Diretório Temporário

```bash
chmod 1777 empresa/temporarios
```

Ou:

```bash
chmod +t empresa/temporarios
chmod 777 empresa/temporarios
```

O Sticky Bit impede que um usuário exclua arquivos pertencentes a outro.

---

## Relatório Financeiro

```bash
chmod 640 empresa/financeiro/folha-pagamento.xlsx
```

Permite:

- proprietário: leitura e escrita;
- grupo: leitura;
- outros: nenhum acesso.

---

## README

```bash
chmod 644 empresa/desenvolvimento/README.md
```

Arquivo comum para documentação.

---

## ACL

Exemplo:

```bash
sudo setfacl -m u:usuario:r empresa/financeiro/impostos.xlsx
```

Confira:

```bash
getfacl empresa/financeiro/impostos.xlsx
```

---

# 💼 Como isso aparece em entrevistas?

É comum que entrevistadores façam perguntas como:

### Qual a diferença entre `755` e `700`?

**Resposta esperada:**

- `755`: proprietário possui controle total; grupo e outros podem ler e executar.
- `700`: apenas o proprietário possui acesso.

---

### Quando utilizar `chmod 600`?

Em arquivos confidenciais, como:

- chaves SSH;
- certificados privados;
- arquivos contendo credenciais.

---

### Quando utilizar ACL em vez de grupos?

Quando apenas alguns usuários específicos precisam de acesso, sem alterar o proprietário ou o grupo principal do arquivo.

---

### Por que evitar `chmod 777`?

Porque concede leitura, escrita e execução para qualquer usuário, aumentando significativamente os riscos de segurança.

---

# 🧠 O que você aprendeu neste módulo?

Agora você domina:

- interpretação de permissões;
- `chmod`;
- `chown`;
- `chgrp`;
- permissões especiais;
- `umask`;
- ACLs;
- boas práticas de segurança;
- aplicação prática em cenários reais.

Você já possui conhecimentos suficientes para administrar permissões em servidores Linux de pequeno e médio porte.

---

# 🏆 Parabéns!

Você concluiu o **Módulo 05 — Permissões**.

Este é um dos módulos mais importantes de todo o Linux Explorer.

Grande parte da administração de sistemas Linux depende diretamente dos conceitos estudados aqui.

Nos próximos módulos você utilizará esse conhecimento constantemente.

---

# 📈 Evolução do Laboratório de Segurança

Ao concluir este desafio, seu laboratório representa um ambiente corporativo simplificado contendo:

- arquivos públicos;
- arquivos privados;
- scripts executáveis;
- diretórios compartilhados;
- permissões especiais;
- ACLs;
- boas práticas de segurança.

Você agora possui um ambiente completo para revisar todos os conceitos deste módulo sempre que desejar.

---

# Próximos passos

Antes de seguir para o próximo módulo:

- Refaça este desafio sem consultar a solução.
- Explique para outra pessoa por que escolheu cada permissão.
- Consulte o `CHEATSHEET.md` quando tiver dúvidas.
- Revise o `RESUMO.md` antes de avançar.

Quanto mais você praticar, mais natural será interpretar e configurar permissões no Linux.


