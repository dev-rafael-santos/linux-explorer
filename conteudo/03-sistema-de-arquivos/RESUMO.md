# Resumo — Sistema de Arquivos Linux

Este resumo reúne os principais conceitos estudados no **Módulo 03**.

Seu objetivo é ajudar na revisão rápida antes de avançar para o próximo módulo.

---

# Mapa mental

```text
Sistema de Arquivos Linux
│
├── /
│   ├── home
│   ├── etc
│   ├── usr
│   ├── var
│   ├── tmp
│   ├── boot
│   ├── dev
│   ├── proc
│   ├── sys
│   └── opt
```

Todos esses diretórios fazem parte de uma única árvore de arquivos.

---

# O conceito mais importante

No Linux existe apenas uma árvore de diretórios.

Tudo começa em:

```text
/
```

Diferentemente do Windows, onde existem várias unidades (`C:`, `D:`, `E:`...), o Linux organiza todos os arquivos dentro da mesma estrutura.

---

# Resumo dos principais diretórios

## `/`

É o diretório raiz.

Todo o sistema parte dele.

---

## `/home`

Armazena os arquivos pessoais dos usuários.

Exemplos:

- Documentos
- Downloads
- Imagens
- Vídeos
- Configurações pessoais

---

## `/etc`

Armazena configurações do sistema.

Exemplos:

- hostname
- hosts
- passwd
- group
- fstab

---

## `/usr`

Armazena:

- programas;
- bibliotecas;
- documentação;
- recursos compartilhados.

Grande parte dos comandos utilizados diariamente encontra-se nesse diretório.

---

## `/var`

Armazena dados que mudam constantemente.

Exemplos:

- logs;
- cache;
- bancos de dados;
- filas;
- arquivos temporários de serviços.

---

## `/tmp`

Utilizado para arquivos temporários.

Seu conteúdo pode ser removido automaticamente pelo sistema.

Nunca utilize esse diretório para armazenar arquivos importantes.

---

## `/boot`

Contém os arquivos utilizados durante a inicialização do Linux.

Entre eles:

- Kernel;
- initramfs;
- GRUB.

---

## `/dev`

Representa dispositivos como arquivos.

Exemplos:

```text
/dev/sda
/dev/null
/dev/random
```

Essa é uma das características mais marcantes do Linux.

---

## `/proc`

Disponibiliza informações do Kernel e dos processos em tempo real.

Os arquivos existentes nesse diretório são gerados dinamicamente.

---

## `/sys`

Disponibiliza informações sobre hardware e dispositivos.

Assim como `/proc`, faz parte de um sistema de arquivos virtual.

---

## `/opt`

Armazena aplicações opcionais instaladas manualmente ou distribuídas por terceiros.

---

# Comparação com Windows

| Windows | Linux |
|----------|--------|
| `C:\Users` | `/home` |
| Registro | `/etc` |
| Program Files | `/usr` |
| Program Files (instalações manuais) | `/opt` |
| Pasta Temp | `/tmp` |
| Gerenciador de Dispositivos | `/dev` (conceitualmente) |
| Informações do Sistema | `/proc` e `/sys` |

---

# Fluxo de organização

```text
/
│
├── Usuários
│      │
│      └── /home
│
├── Configurações
│      │
│      └── /etc
│
├── Programas
│      │
│      ├── /usr
│      └── /opt
│
├── Dados variáveis
│      │
│      ├── /var
│      └── /tmp
│
└── Sistema
       │
       ├── /boot
       ├── /dev
       ├── /proc
       └── /sys
```

---

# O que vale a pena memorizar?

Mais do que decorar os diretórios, memorize suas responsabilidades.

| Diretório | Responsabilidade |
|------------|------------------|
| `/` | Início da árvore |
| `/home` | Usuários |
| `/etc` | Configurações |
| `/usr` | Programas |
| `/var` | Dados variáveis |
| `/tmp` | Arquivos temporários |
| `/boot` | Inicialização |
| `/dev` | Dispositivos |
| `/proc` | Informações do Kernel |
| `/sys` | Informações do hardware |
| `/opt` | Aplicações opcionais |

---

# O que você já é capaz de fazer?

Após concluir este módulo, você já consegue:

- compreender a organização do sistema de arquivos Linux;
- localizar configurações do sistema;
- identificar onde ficam programas instalados;
- entender onde estão os arquivos dos usuários;
- localizar logs do sistema;
- reconhecer dispositivos representados como arquivos;
- compreender a função de `/proc` e `/sys`;
- diferenciar aplicações instaladas em `/usr` e `/opt`.

---

# Erros comuns

Evite estes erros:

- Confundir `/` com `/home`.
- Alterar arquivos em `/etc` sem saber sua função.
- Salvar arquivos importantes em `/tmp`.
- Alterar arquivos em `/boot`.
- Utilizar comandos destrutivos em dispositivos dentro de `/dev`.
- Pensar que `/proc` e `/sys` armazenam arquivos reais.

---

# Dicas para continuar aprendendo

Antes de avançar para o próximo módulo:

- navegue pelos diretórios utilizando o Terminal;
- repita os laboratórios;
- execute novamente os experimentos;
- consulte o `CHEATSHEET.md`;
- tente explicar a função de cada diretório sem consultar o material.

Se conseguir fazer isso, você construiu uma excelente base para os próximos módulos.

---

# Conclusão

O sistema de arquivos Linux foi projetado para ser organizado, previsível e consistente.

Cada diretório possui uma responsabilidade específica.

Quando você compreende essa organização, deixa de procurar arquivos "por tentativa e erro" e passa a entender a lógica utilizada pelo sistema operacional.

Essa mudança de perspectiva é um dos passos mais importantes para evoluir de usuário para profissional Linux.
