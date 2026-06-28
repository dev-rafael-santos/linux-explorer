# Cheat Sheet — Módulo 02: Terminal

────────────────────────────────────────────

**Objetivo:** Servir como material de consulta rápida para os comandos estudados no Módulo 02.

> **Importante:** Este arquivo não substitui os capítulos do módulo. Utilize-o como referência rápida durante os estudos e no dia a dia.

────────────────────────────────────────────

# Navegação

| Comando                | Descrição                                           |
| ---------------------- | --------------------------------------------------- |
| `pwd`                  | Exibe o diretório atual.                            |
| `cd`                   | Vai para o diretório Home do usuário.               |
| `cd ~`                 | Vai para o diretório Home do usuário.               |
| `cd ..`                | Volta um nível na árvore de diretórios.             |
| `cd nome_da_pasta`     | Entra em um diretório.                              |
| `cd /caminho/completo` | Acessa um diretório utilizando um caminho absoluto. |

---

# Listagem

| Comando  | Descrição                                   |
| -------- | ------------------------------------------- |
| `ls`     | Lista arquivos e diretórios.                |
| `ls -l`  | Lista em formato detalhado.                 |
| `ls -a`  | Exibe arquivos ocultos.                     |
| `ls -la` | Lista detalhada incluindo arquivos ocultos. |

---

# Informações do sistema

| Comando  | Descrição                              |
| -------- | -------------------------------------- |
| `whoami` | Mostra o usuário atualmente conectado. |
| `date`   | Exibe a data e hora do sistema.        |

---

# Ajuda

| Comando          | Descrição                             |
| ---------------- | ------------------------------------- |
| `man comando`    | Abre o manual completo de um comando. |
| `comando --help` | Exibe uma ajuda resumida.             |

---

# Produtividade

| Comando   | Descrição                                 |
| --------- | ----------------------------------------- |
| `history` | Exibe o histórico de comandos executados. |
| `clear`   | Limpa a tela do Terminal.                 |

---

# Atalhos do Terminal

| Atalho   | Função                                         |
| -------- | ---------------------------------------------- |
| ↑        | Comando anterior.                              |
| ↓        | Próximo comando do histórico.                  |
| TAB      | Autocompleta nomes de arquivos e diretórios.   |
| Ctrl + C | Interrompe o comando em execução.              |
| Ctrl + L | Limpa a tela (equivalente ao comando `clear`). |

---

# Execução de múltiplos comandos

| Operador | Função                                                                    |   |                                                        |
| -------- | ------------------------------------------------------------------------- | - | ------------------------------------------------------ |
| `;`      | Executa todos os comandos em sequência.                                   |   |                                                        |
| `&&`     | Executa o próximo comando apenas se o anterior for executado com sucesso. |   |                                                        |
| `        |                                                                           | ` | Executa o próximo comando apenas se o anterior falhar. |

---

# Estrutura básica de um comando

```text
comando [opções] [argumentos]
```

Exemplo:

```bash
ls -la Documentos
```

Onde:

* `ls` → comando;
* `-la` → opções;
* `Documentos` → argumento.

---

# Fluxo de execução de um comando

```text
Você
 │
 ▼
Digita um comando
 │
 ▼
Pressiona Enter
 │
 ▼
Shell interpreta
 │
 ▼
Kernel executa
 │
 ▼
Resultado é exibido
 │
 ▼
Prompt retorna
```

---

# Resumo dos comandos estudados

| Comando   | Categoria     | Uso diário |
| --------- | ------------- | ---------- |
| `pwd`     | Navegação     | ⭐⭐⭐⭐⭐      |
| `cd`      | Navegação     | ⭐⭐⭐⭐⭐      |
| `ls`      | Navegação     | ⭐⭐⭐⭐⭐      |
| `whoami`  | Sistema       | ⭐⭐⭐⭐☆      |
| `date`    | Sistema       | ⭐⭐⭐☆☆      |
| `man`     | Ajuda         | ⭐⭐⭐⭐⭐      |
| `history` | Produtividade | ⭐⭐⭐⭐⭐      |
| `clear`   | Produtividade | ⭐⭐⭐⭐☆      |

---

# Dicas rápidas

* Sempre utilize **TAB** para completar nomes.
* Consulte o **man** sempre que tiver dúvidas.
* Utilize **history** para reaproveitar comandos.
* Observe sempre o **Prompt** antes de executar qualquer comando.
* O Linux diferencia letras maiúsculas e minúsculas.

---

# Próximo módulo

No Módulo 03 você aprenderá a estrutura do sistema de arquivos Linux e entenderá o propósito dos principais diretórios do sistema, como:

* `/`
* `/home`
* `/etc`
* `/usr`
* `/var`
* `/tmp`
