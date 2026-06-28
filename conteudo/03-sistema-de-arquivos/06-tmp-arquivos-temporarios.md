# 06. `/tmp` — Arquivos temporários

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 30 minutos

**Pré-requisitos:**

- Módulo 01 — Fundamentos do Linux
- Módulo 02 — Terminal
- Capítulos anteriores deste módulo

────────────────────────────────────────────

# Visão Geral

Imagine que você está editando um documento muito grande.

Enquanto trabalha, o editor pode criar arquivos temporários para evitar perda de dados caso o computador desligue inesperadamente.

Esses arquivos não precisam existir para sempre.

Eles existem apenas enquanto são necessários.

É exatamente essa a função do diretório **`/tmp`**.

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

- Entender a finalidade do diretório `/tmp`.
- Saber quais tipos de arquivos ficam armazenados nele.
- Compreender por que seu conteúdo pode ser removido automaticamente.
- Explorar esse diretório com segurança.

---

# Por que isso é importante?

Quase todos os programas modernos utilizam arquivos temporários.

Instaladores, navegadores, editores de texto, compiladores e diversas outras aplicações dependem do diretório `/tmp`.

Conhecer seu funcionamento ajuda a compreender melhor como o Linux gerencia informações temporárias.

---

# Quando você usará isso?

Você encontrará o diretório `/tmp` em situações como:

- Instalação de programas.
- Atualizações do sistema.
- Navegação na internet.
- Compilação de código.
- Descompactação de arquivos.
- Execução de scripts.
- Desenvolvimento de software.

---

# Você vai conhecer

| Item | Informação |
|------|------------|
| Diretório | `/tmp` |
| Categoria | Arquivos temporários |
| Importância | ⭐⭐⭐⭐☆ |
| Utilizado diariamente? | ✅ Sim |
| Pode alterar? | ⚠️ Com cuidado |
| Equivalente no Windows | Pasta **Temp** (`%TEMP%`) |

---

# O que é o diretório `/tmp`?

O diretório `/tmp` é utilizado para armazenar arquivos temporários criados pelo sistema operacional e por aplicações.

Esses arquivos existem apenas enquanto são necessários.

Em muitas distribuições Linux, o conteúdo de `/tmp` é removido automaticamente durante a inicialização do sistema ou após determinado período.

Por isso, nunca utilize esse diretório para armazenar arquivos importantes.

---

# Como funciona

Imagine um bloco de anotações utilizado durante uma reunião.

Após o término da reunião, ele pode ser descartado.

O `/tmp` funciona de maneira semelhante.

Programas criam arquivos temporários, utilizam essas informações durante sua execução e depois os removem quando não são mais necessários.

---

# Estrutura

O conteúdo varia bastante conforme os programas em execução.

Exemplo:

```text
/tmp
│
├── arquivo.tmp
├── vscode-12345
├── chrome-cache
├── pip-install
└── sessão-usuario
```

Cada aplicação pode criar seus próprios arquivos temporários.

---

# O que normalmente você encontrará aqui?

| Tipo de conteúdo | Exemplos |
|------------------|----------|
| Arquivos temporários | `arquivo.tmp` |
| Cache temporário | Navegadores e instaladores |
| Arquivos de instalação | Pacotes sendo descompactados |
| Sessões temporárias | Dados de aplicações em execução |

---

# Comparando com o Windows

| Windows | Linux |
|----------|--------|
| `%TEMP%` | `/tmp` |
| Arquivos temporários | Arquivos temporários |
| Cache de instalação | Cache temporário |

O conceito é semelhante, embora a forma de gerenciamento possa variar.

---

# 🛠️ Ferramentas que utilizam este diretório

Diversas aplicações utilizam `/tmp`, entre elas:

- Google Chrome
- Firefox
- VS Code
- Python (pip)
- apt
- unzip
- tar
- gcc

---

# Pratique

Entre no diretório:

```bash
cd /tmp
```

Confira sua localização:

```bash
pwd
```

Liste o conteúdo:

```bash
ls
```

Agora crie um arquivo temporário:

```bash
touch teste.tmp
```

Verifique se ele foi criado:

```bash
ls
```

Por fim, remova o arquivo:

```bash
rm teste.tmp
```

---

# Explore

Conte quantos arquivos existem atualmente:

```bash
ls | wc -l
```

Observe que o número pode variar conforme os programas que estiverem em execução.

---

# 💼 Exemplos do mundo real

Durante uma atualização do Ubuntu, diversos arquivos são armazenados temporariamente em `/tmp`.

Ao instalar um pacote Python utilizando o `pip`, arquivos temporários também podem ser criados durante o processo.

Editores de código como o VS Code utilizam arquivos temporários para recuperação automática e funcionamento interno.

---

# ⚠️ Pode alterar?

| Diretório | Pode alterar? | Observação |
|-----------|---------------|------------|
| `/tmp` | ✅ Sim, com cuidado | Evite remover arquivos utilizados por programas em execução. |

---

# 💡 Dica profissional

Antes de apagar arquivos em `/tmp`, verifique se eles não pertencem a alguma aplicação em execução.

Em servidores de produção, excluir arquivos temporários sem planejamento pode interromper processos importantes.

---

# Você sabia?

Em muitas distribuições modernas, o diretório `/tmp` pode ser armazenado diretamente na memória RAM por meio do **tmpfs**.

Isso torna o acesso muito rápido, mas faz com que seu conteúdo seja perdido ao reiniciar o computador.

---

# Resumo rápido

| Situação | Comando |
|----------|----------|
| Entrar em `/tmp` | `cd /tmp` |
| Criar arquivo | `touch teste.tmp` |
| Listar arquivos | `ls` |
| Remover arquivo | `rm teste.tmp` |

---

# Erros comuns

- Armazenar arquivos importantes em `/tmp`.
- Excluir arquivos temporários sem verificar se estão em uso.
- Utilizar `/tmp` como diretório permanente.

---

# Referências

- Filesystem Hierarchy Standard (FHS)
- Ubuntu Documentation
- Linux Foundation

---

# Conclusão

Neste capítulo você conheceu o diretório `/tmp`, responsável por armazenar arquivos temporários utilizados pelo sistema e pelas aplicações.

Também aprendeu que seu conteúdo pode ser removido automaticamente e que ele não deve ser utilizado para armazenar informações importantes.

---

# Prepare-se para o próximo capítulo

Até agora vimos onde ficam:

- usuários (`/home`);
- configurações (`/etc`);
- programas (`/usr`);
- dados variáveis (`/var`);
- arquivos temporários (`/tmp`).

No próximo capítulo conheceremos um diretório pequeno, mas fundamental para o funcionamento do Linux:

**`/boot`**, onde estão os arquivos utilizados durante a inicialização do sistema.
