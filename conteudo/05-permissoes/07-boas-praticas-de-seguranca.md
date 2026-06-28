# 07. Boas Práticas de Segurança

────────────────────────────────────────────

**Nível:** Intermediário

**Tempo estimado:** 50 minutos

**Pré-requisitos:**

- Capítulos anteriores deste módulo

────────────────────────────────────────────

# Visão Geral

Saber utilizar comandos como `chmod`, `chown` e `setfacl` é apenas parte do trabalho.

O mais importante é utilizá-los corretamente.

Neste capítulo você conhecerá boas práticas adotadas por administradores de sistemas para proteger arquivos, diretórios e servidores Linux.

Essas recomendações ajudam a reduzir riscos e evitar problemas de segurança.

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

- Aplicar o princípio do menor privilégio.
- Evitar permissões excessivas.
- Identificar configurações inseguras.
- Proteger arquivos sensíveis.
- Adotar boas práticas utilizadas em ambientes profissionais.

---

# Por que isso é importante?

Grande parte dos incidentes de segurança ocorre por configurações incorretas.

Muitas vezes o problema não está em uma vulnerabilidade do sistema, mas em permissões concedidas além do necessário.

Conhecer boas práticas ajuda a evitar esse tipo de situação.

---

# Quando você usará isso?

Você aplicará essas recomendações ao:

- configurar servidores;
- criar scripts;
- administrar usuários;
- compartilhar diretórios;
- publicar aplicações.

---

# Princípio do Menor Privilégio

A regra mais importante da segurança em sistemas Linux é:

> Cada usuário deve possuir apenas as permissões necessárias para executar seu trabalho.

Evite conceder permissões além do necessário.

---

# Evite utilizar `777`

Uma das práticas mais desaconselhadas é utilizar:

```bash
chmod 777 arquivo
```

Essa configuração permite:

- leitura;
- escrita;
- execução;

para qualquer usuário.

Na maioria dos casos, isso representa um risco desnecessário.

---

# Utilize permissões apropriadas

Exemplos comuns:

| Situação | Permissão |
|----------|-----------|
| Arquivo comum | `644` |
| Script executável | `755` |
| Arquivo confidencial | `600` |
| Diretório privado | `700` |

Esses valores atendem à maioria dos cenários.

---

# Proteja arquivos sensíveis

Arquivos contendo:

- senhas;
- chaves SSH;
- certificados;
- tokens;
- credenciais;

devem possuir permissões restritas.

Exemplo:

```bash
chmod 600 id_rsa
```

---

# Revise permissões periodicamente

Em servidores é recomendável revisar permissões regularmente.

Alguns comandos úteis:

```bash
ls -l
```

```bash
find . -perm -777
```

```bash
find . -type f
```

Essas verificações ajudam a identificar configurações inadequadas.

---

# Evite utilizar o usuário root

Sempre que possível:

- utilize usuários comuns;
- utilize `sudo` apenas quando necessário.

Isso reduz significativamente os riscos de alterações acidentais.

---

# Utilize grupos

Quando vários usuários precisam acessar os mesmos arquivos, prefira criar grupos.

Isso torna a administração mais simples do que conceder permissões individualmente.

---

# ACLs apenas quando necessário

ACLs são excelentes ferramentas.

Mas também aumentam a complexidade.

Sempre pergunte:

> O modelo tradicional resolve este problema?

Se sim, normalmente não há necessidade de utilizar ACL.

---

# 🧠 Como o Linux enxerga isso?

O Linux não sabe o que é um arquivo importante.

Ele apenas aplica as regras configuradas.

Se as permissões forem excessivas, o sistema permitirá o acesso.

Se forem restritas, o acesso será negado.

A responsabilidade pela configuração correta é do administrador.

---

# O que normalmente você encontrará aqui?

Em ambientes profissionais é comum encontrar:

- permissões mínimas;
- uso intensivo de grupos;
- poucos arquivos utilizando ACL;
- quase nenhum arquivo com permissão `777`.

---

# Comparando com Windows

| Windows | Linux |
|----------|--------|
| Políticas de segurança | Boas práticas de permissões |
| Controle de acesso | `chmod`, `chown`, ACL |
| Administração segura | Menor privilégio |

---

# 🛠️ Ferramentas que seguem essas boas práticas

As recomendações apresentadas neste capítulo são adotadas por diversas ferramentas e serviços amplamente utilizados no ecossistema Linux, como:

* OpenSSH
* Apache
* Nginx
* Docker
* Kubernetes
* PostgreSQL
* MySQL
* Git
* Ansible
* Jenkins

Essas aplicações dependem de permissões corretamente configuradas para funcionar com segurança.

---

# Pratique

Entre no laboratório:

```bash id="0h6vkt"
cd ~/linux-explorer-lab/seguranca
```

Liste os arquivos com detalhes:

```bash id="hr6fqe"
ls -lR
```

Analise cada arquivo e responda:

* Existe algum arquivo com permissão de escrita para todos?
* Algum script deveria possuir permissão de execução?
* Algum arquivo privado deveria utilizar `600`?

Agora verifique os diretórios:

```bash id="3aqg7y"
find . -type d -exec ls -ld {} \;
```

Observe as permissões e reflita se fazem sentido para o objetivo de cada diretório.

---

# 🧪 Experimento

Vamos simular uma situação comum.

Primeiro torne um arquivo excessivamente permissivo:

```bash id="gx4jpn"
chmod 777 documentos/relatorio.txt
```

Confira:

```bash id="8f3u2x"
ls -l documentos/relatorio.txt
```

Agora pense:

* Essa configuração realmente é necessária?
* Quais riscos ela pode trazer?

Corrija a permissão:

```bash id="pj9kzs"
chmod 644 documentos/relatorio.txt
```

Confira novamente:

```bash id="p5fjhy"
ls -l documentos/relatorio.txt
```

Esse exercício demonstra que permissões excessivas quase sempre podem ser substituídas por configurações mais seguras.

---

# Explore

Analise os seguintes cenários e tente escolher a permissão mais adequada antes de consultar a resposta.

| Situação                | Permissão sugerida |
| ----------------------- | ------------------ |
| Documento comum         | ?                  |
| Script executável       | ?                  |
| Chave SSH privada       | ?                  |
| Diretório pessoal       | ?                  |
| Diretório compartilhado | ?                  |

Depois compare com a tabela apresentada anteriormente.

---

# 💼 Exemplos do mundo real

Uma chave SSH privada normalmente utiliza:

```text id="k2s4nt"
600
```

Um script utilizado por vários usuários costuma utilizar:

```text id="s6w0da"
755
```

Um diretório de projetos compartilhados pode utilizar:

```text id="5v3hn9"
775
```

Essas configurações representam boas práticas encontradas em ambientes profissionais.

---

# ⚠️ Situações que devem ser evitadas

Evite práticas como:

* utilizar `777` sem necessidade;
* executar tarefas diárias como `root`;
* alterar permissões sem verificar o resultado;
* utilizar ACLs quando grupos resolveriam o problema;
* conceder permissões permanentes para testes temporários.

Esses comportamentos aumentam os riscos de segurança.

---

# 💡 Dica profissional

Antes de alterar qualquer permissão, faça estas perguntas:

1. Quem realmente precisa acessar este arquivo?
2. Esse usuário precisa apenas ler ou também modificar?
3. Existe uma alternativa mais restritiva?

Na maioria dos casos, a configuração mais segura é também a mais simples.

---

# 🧠 Mentalidade Linux

Segurança não consiste em bloquear tudo.

Também não consiste em liberar tudo.

Segurança significa conceder **apenas o acesso necessário**, pelo menor tempo possível e para as pessoas corretas.

Esse princípio orienta praticamente todas as boas práticas de administração Linux.

---

# Você sabia?

Diversas distribuições Linux e ferramentas de auditoria conseguem identificar automaticamente permissões consideradas inseguras.

Por isso, manter boas práticas facilita auditorias, reduz alertas de segurança e melhora a confiabilidade do ambiente.

---

# 🏁 Estado esperado do laboratório

Ao concluir este capítulo, a estrutura do Laboratório de Segurança permanecerá organizada.

As permissões dos arquivos utilizados nos experimentos deverão ter sido restauradas para valores apropriados após os testes.

---

# ⚡ Checklist de segurança

Antes de considerar um ambiente pronto para produção, verifique:

* ✅ Arquivos privados utilizam `600`.
* ✅ Scripts executáveis utilizam `755` quando necessário.
* ✅ Diretórios privados utilizam `700`.
* ✅ Não existem arquivos com `777` sem justificativa.
* ✅ Proprietários e grupos estão corretos.
* ✅ ACLs são utilizadas apenas quando realmente necessárias.
* ✅ O princípio do menor privilégio foi respeitado.

---

# Resumo rápido

| Boa prática                            | Benefício                      |
| -------------------------------------- | ------------------------------ |
| Utilizar o menor privilégio possível   | Reduz riscos                   |
| Evitar `777`                           | Aumenta a segurança            |
| Utilizar grupos                        | Simplifica a administração     |
| Revisar permissões periodicamente      | Evita configurações incorretas |
| Utilizar ACLs apenas quando necessário | Reduz complexidade             |

---

# Erros comuns

* Conceder permissões além do necessário.
* Esquecer de revisar permissões após alterações.
* Utilizar `root` para tarefas comuns.
* Ignorar a propriedade dos arquivos.
* Configurar permissões pensando apenas no funcionamento e não na segurança.

---

# Referências

* Linux Foundation
* CIS Benchmarks for Linux
* GNU Coreutils
* Ubuntu Security Documentation
* Red Hat Security Guide

---

# Conclusão

Neste capítulo você conheceu práticas recomendadas para administrar permissões de forma segura.

Mais do que aprender comandos, você desenvolveu critérios para decidir quando e como utilizá-los, reduzindo riscos e aumentando a segurança dos ambientes Linux.

---

# 🔗 Revisite este conceito

Ao longo deste módulo você estudou:

* Permissões tradicionais (`rwx`)
* `chmod`
* `chown` e `chgrp`
* Permissões especiais
* `umask`
* ACLs
* Boas práticas de segurança

Agora você possui uma visão completa do modelo de controle de acesso do Linux.

---

# Prepare-se para o próximo capítulo

Chegou o momento de reunir tudo o que foi aprendido.

No próximo capítulo você enfrentará um **Desafio Prático**, resolvendo situações semelhantes às encontradas por administradores Linux no dia a dia.

Será uma oportunidade para aplicar todos os conceitos deste módulo em um único laboratório.

---

# 📈 Evolução do Laboratório de Segurança

## Competências conquistadas

Até este momento você já domina:

* ✅ Interpretar permissões.
* ✅ Alterar permissões com `chmod`.
* ✅ Administrar proprietário e grupo.
* ✅ Utilizar permissões especiais.
* ✅ Configurar o `umask`.
* ✅ Aplicar ACLs.
* ✅ Adotar boas práticas de segurança.
* ✅ Avaliar criticamente configurações de permissões antes de aplicá-las.

Seu Laboratório de Segurança agora representa um ambiente de treinamento completo para administração de permissões e controle de acesso em Linux.

