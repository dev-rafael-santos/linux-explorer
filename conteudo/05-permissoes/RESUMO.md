# Resumo — Permissões e Segurança no Linux

Este resumo reúne os principais conceitos estudados no **Módulo 05**.

Seu objetivo é consolidar os conhecimentos adquiridos e servir como material de revisão rápida antes de avançar para o próximo módulo.

---

# Mapa mental

```text
Permissões e Segurança
│
├── Permissões
│   ├── r
│   ├── w
│   └── x
│
├── chmod
│   ├── Simbólico
│   └── Octal
│
├── Propriedade
│   ├── chown
│   └── chgrp
│
├── Permissões Especiais
│   ├── SUID
│   ├── SGID
│   └── Sticky Bit
│
├── Umask
│
├── ACL
│
└── Boas Práticas
```

---

# O conceito mais importante

A segurança no Linux é baseada em três pilares:

- Proprietário
- Grupo
- Permissões

Sempre que um usuário tenta acessar um arquivo, o sistema verifica:

1. Quem é o proprietário?
2. O usuário pertence ao grupo?
3. Quais permissões existem para outros usuários?
4. Existem ACLs configuradas?

Somente depois dessa análise o acesso é permitido ou negado.

---

# O modelo tradicional

Cada arquivo possui permissões para:

```text
Usuário
Grupo
Outros
```

Cada categoria pode possuir:

```text
r → leitura
w → escrita
x → execução
```

---

# Interpretando permissões

Exemplo:

```text
-rwxr-xr--
```

Separando:

```text
-
rwx
r-x
r--
```

| Parte | Significado |
|--------|-------------|
| `-` | Arquivo comum |
| `rwx` | Proprietário |
| `r-x` | Grupo |
| `r--` | Outros |

---

# chmod

Permite alterar permissões.

Modo simbólico:

```bash
chmod u+x arquivo
```

Modo octal:

```bash
chmod 755 arquivo
```

---

# Permissões octais

| Número | Permissão |
|---------|-----------|
| 7 | rwx |
| 6 | rw- |
| 5 | r-x |
| 4 | r-- |
| 0 | --- |

As permissões mais utilizadas são:

| Permissão | Uso |
|-----------|-----|
| 644 | Arquivos comuns |
| 755 | Scripts e diretórios |
| 600 | Arquivos privados |
| 700 | Diretórios privados |

---

# chown e chgrp

Alterar proprietário:

```bash
sudo chown usuario arquivo
```

Alterar grupo:

```bash
sudo chgrp grupo arquivo
```

Alterar proprietário e grupo:

```bash
sudo chown usuario:grupo arquivo
```

---

# Permissões Especiais

## SUID

Executa um programa utilizando o proprietário do arquivo.

Representação:

```text
-rwsr-xr-x
```

---

## SGID

Em diretórios, faz com que novos arquivos herdem automaticamente o grupo.

Representação:

```text
drwxrwsr-x
```

---

## Sticky Bit

Utilizado em diretórios compartilhados.

Impede que usuários removam arquivos de outros usuários.

Representação:

```text
drwxrwxrwt
```

---

# Umask

O `umask` define as permissões padrão para novos arquivos e diretórios.

Valores comuns:

| Umask | Arquivos | Diretórios |
|-------:|:---------:|:----------:|
| 022 | 644 | 755 |
| 027 | 640 | 750 |
| 077 | 600 | 700 |

Importante:

O `umask` **remove permissões**, ele não adiciona.

---

# ACL

As ACLs permitem conceder permissões específicas para usuários ou grupos.

Comandos principais:

```bash
getfacl arquivo
```

```bash
setfacl -m u:usuario:r arquivo
```

```bash
setfacl -x u:usuario arquivo
```

Use ACLs apenas quando o modelo tradicional não for suficiente.

---

# Fluxo de decisão

Sempre que precisar configurar permissões, siga este fluxo:

```text
Arquivo criado
      │
      ▼
Quem será o proprietário?
      │
      ▼
Qual será o grupo?
      │
      ▼
Quais permissões são necessárias?
      │
      ▼
Existe necessidade de SUID, SGID ou Sticky Bit?
      │
      ▼
Existe necessidade de ACL?
      │
      ▼
Validar configuração
```

---

# O que você já é capaz de fazer?

Ao concluir este módulo você consegue:

- interpretar permissões (`rwx`);
- utilizar `chmod` nos modos simbólico e octal;
- alterar proprietário e grupo;
- utilizar `chown` e `chgrp`;
- aplicar SUID, SGID e Sticky Bit;
- configurar o `umask`;
- utilizar ACLs;
- proteger arquivos sensíveis;
- aplicar boas práticas de segurança;
- resolver problemas comuns de permissões.

Essas competências fazem parte da rotina de administradores Linux e profissionais de DevOps.

---

# Erros comuns

Evite:

- utilizar `777` sem necessidade;
- alterar permissões sem conferi-las;
- executar tarefas comuns como `root`;
- utilizar ACL quando grupos resolvem o problema;
- esquecer de revisar proprietário e grupo.

---

# Dicas para continuar praticando

Antes de avançar para o próximo módulo:

- Refaça o Desafio Prático.
- Crie novos cenários no Laboratório de Segurança.
- Teste diferentes valores de `chmod`.
- Experimente alterar o `umask`.
- Utilize `getfacl` e `setfacl`.
- Revise o `CHEATSHEET.md`.

Quanto mais você praticar, mais natural será administrar permissões no Linux.

---

# Conclusão

Neste módulo você aprendeu como o Linux controla o acesso a arquivos e diretórios.

Você conheceu o modelo tradicional de permissões, aprendeu a modificar permissões e propriedades, utilizou permissões especiais, compreendeu o funcionamento do `umask`, explorou ACLs e aplicou boas práticas de segurança.

Esses conhecimentos serão utilizados constantemente nos próximos módulos, especialmente na administração de processos, serviços, usuários e servidores Linux.
