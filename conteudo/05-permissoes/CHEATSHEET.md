# Cheat Sheet — Permissões e Segurança no Linux

Este material reúne os principais comandos e conceitos estudados no **Módulo 05**.

Utilize este arquivo como referência rápida durante seus estudos ou no dia a dia.

---

# Visualizando permissões

Listar arquivos com detalhes:

```bash
ls -l
```

Listar diretórios:

```bash
ls -ld diretorio
```

---

# Estrutura das permissões

```text
-rwxr-xr--
││││││││││
││││││││└── Outros
││││└────── Grupo
│└───────── Proprietário
└────────── Tipo
```

Tipos:

| Símbolo | Significado |
|----------|-------------|
| `-` | Arquivo |
| `d` | Diretório |
| `l` | Link simbólico |

---

# Permissões

| Letra | Valor | Significado |
|-------|------:|-------------|
| `r` | 4 | Leitura |
| `w` | 2 | Escrita |
| `x` | 1 | Execução |

---

# chmod (modo simbólico)

Adicionar execução:

```bash
chmod u+x arquivo
```

Remover execução:

```bash
chmod u-x arquivo
```

Adicionar leitura para todos:

```bash
chmod a+r arquivo
```

---

# chmod (modo octal)

```bash
chmod 644 arquivo
```

```bash
chmod 755 arquivo
```

```bash
chmod 700 arquivo
```

```bash
chmod 600 arquivo
```

---

# Valores octais

| Valor | Permissão |
|-------:|-----------|
| 7 | rwx |
| 6 | rw- |
| 5 | r-x |
| 4 | r-- |
| 0 | --- |

---

# chown

Alterar proprietário:

```bash
sudo chown usuario arquivo
```

Alterar proprietário e grupo:

```bash
sudo chown usuario:grupo arquivo
```

Alterar recursivamente:

```bash
sudo chown -R usuario:grupo diretorio
```

---

# chgrp

Alterar grupo:

```bash
sudo chgrp grupo arquivo
```

---

# Permissões especiais

## SUID

Adicionar:

```bash
chmod u+s arquivo
```

Remover:

```bash
chmod u-s arquivo
```

---

## SGID

Adicionar:

```bash
chmod g+s diretorio
```

Remover:

```bash
chmod g-s diretorio
```

---

## Sticky Bit

Adicionar:

```bash
chmod +t diretorio
```

Remover:

```bash
chmod -t diretorio
```

---

# umask

Consultar:

```bash
umask
```

Alterar:

```bash
umask 022
```

```bash
umask 027
```

```bash
umask 077
```

---

# ACL

Visualizar:

```bash
getfacl arquivo
```

Adicionar ACL:

```bash
setfacl -m u:usuario:r arquivo
```

Adicionar ACL para grupo:

```bash
setfacl -m g:grupo:rw arquivo
```

Remover ACL:

```bash
setfacl -x u:usuario arquivo
```

ACL padrão:

```bash
setfacl -d -m g:grupo:rwx diretorio
```

---

# Permissões mais utilizadas

| Cenário | Permissão |
|----------|-----------|
| Arquivo comum | 644 |
| Script executável | 755 |
| Arquivo privado | 600 |
| Diretório privado | 700 |
| Diretório compartilhado | 775 |

---

# Permissões especiais mais comuns

| Situação | Permissão |
|----------|-----------|
| Programa `passwd` | SUID |
| Diretório compartilhado | SGID |
| Diretório `/tmp` | Sticky Bit |

---

# Valores de umask

| Umask | Arquivos | Diretórios |
|-------:|:---------:|:----------:|
| 022 | 644 | 755 |
| 027 | 640 | 750 |
| 077 | 600 | 700 |

---

# Fluxo de administração

```text
Criar arquivo
      │
      ▼
Verificar proprietário
      │
      ▼
Verificar grupo
      │
      ▼
Definir permissões
      │
      ▼
Aplicar permissões especiais (se necessário)
      │
      ▼
Aplicar ACL (quando necessário)
      │
      ▼
Validar com ls -l e getfacl
```

---

# Checklist rápido

Antes de finalizar uma configuração:

- ✅ Proprietário correto
- ✅ Grupo correto
- ✅ Permissões corretas
- ✅ Evitou `777`
- ✅ Aplicou o menor privilégio
- ✅ ACL apenas quando necessária
- ✅ Conferiu o resultado com `ls -l`

---

# Erros comuns

❌ Utilizar `777` sem necessidade.

❌ Alterar permissões sem verificar o resultado.

❌ Utilizar ACL quando grupos resolvem o problema.

❌ Executar tarefas comuns como `root`.

❌ Esquecer de revisar o proprietário (`chown`).

---

# Dica profissional

Sempre valide suas alterações utilizando:

```bash
ls -l
```

E, quando houver ACLs:

```bash
getfacl arquivo
```

Esses dois comandos resolvem a maioria dos problemas relacionados a permissões.
