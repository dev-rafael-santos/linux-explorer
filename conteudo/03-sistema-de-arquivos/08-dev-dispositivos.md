# 08. `/dev` — Dispositivos do sistema

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 40 minutos

**Pré-requisitos:**

- Módulo 01 — Fundamentos do Linux
- Módulo 02 — Terminal
- Capítulos anteriores deste módulo

────────────────────────────────────────────

# Visão Geral

Imagine conectar um pendrive ao computador.

Ou um HD externo.

Ou uma webcam.

Como o Linux sabe que um novo dispositivo foi conectado?

A resposta está no diretório **`/dev`**.

Nesse diretório, dispositivos físicos e virtuais são representados como arquivos especiais.

Neste capítulo você conhecerá um dos conceitos mais elegantes do Linux: tratar dispositivos como arquivos.

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

- Entender a função do diretório `/dev`.
- Identificar alguns dos principais dispositivos do sistema.
- Compreender por que dispositivos aparecem como arquivos.
- Explorar esse diretório com segurança.

---

# Por que isso é importante?

Todo computador possui dispositivos de entrada e saída.

No Linux, acessar um HD, um teclado ou um pendrive segue praticamente a mesma lógica utilizada para acessar um arquivo.

Essa filosofia simplifica bastante o desenvolvimento de software e a administração do sistema.

---

# Quando você usará isso?

Você encontrará o diretório `/dev` em situações como:

- Identificar discos.
- Conectar pendrives.
- Configurar dispositivos USB.
- Trabalhar com máquinas virtuais.
- Administrar servidores.
- Recuperar discos.
- Instalar sistemas operacionais.

---

# Você vai conhecer

| Item | Informação |
|------|------------|
| Diretório | `/dev` |
| Categoria | Dispositivos |
| Importância | ⭐⭐⭐⭐⭐ |
| Utilizado diariamente? | ⚠️ Indiretamente |
| Pode alterar? | ❌ Evite |
| Equivalente no Windows | Gerenciador de Dispositivos (conceitualmente) |

---

# O que é o diretório `/dev`?

O diretório `/dev` contém arquivos especiais que representam dispositivos do computador.

Esses arquivos não armazenam documentos ou imagens.

Eles funcionam como uma interface entre o sistema operacional e o hardware.

---

# Como funciona

Quando um dispositivo é conectado, o Kernel cria um arquivo correspondente em `/dev`.

Exemplo:

```text
HD Principal
        │
        ▼
   /dev/sda
```

Outro exemplo:

```text
Pendrive
      │
      ▼
 /dev/sdb
```

---

# 🧠 Como o Linux enxerga isso?

No Linux, diversos dispositivos são acessados como arquivos.

Exemplos:

| Dispositivo | Arquivo |
|-------------|----------|
| HD principal | `/dev/sda` |
| Primeira partição | `/dev/sda1` |
| Pendrive | `/dev/sdb` |
| Terminal atual | `/dev/tty` |
| Disco virtual | `/dev/vda` |
| Áudio | `/dev/snd` |

Essa abordagem é uma das marcas registradas dos sistemas Unix.

---

# O que normalmente você encontrará aqui?

```text
/dev
│
├── sda
├── sda1
├── sdb
├── tty
├── null
├── zero
├── random
└── urandom
```

Alguns desses arquivos representam hardware.

Outros representam dispositivos virtuais criados pelo Kernel.

---

# Conhecendo alguns dispositivos especiais

## `/dev/null`

Descarta tudo que for enviado para ele.

Muito utilizado em scripts.

---

## `/dev/zero`

Gera zeros continuamente.

É utilizado em testes e criação de arquivos.

---

## `/dev/random`

Produz números aleatórios utilizando eventos do sistema.

---

## `/dev/urandom`

Semelhante ao anterior, porém mais rápido para diversas aplicações.

---

# Comparando com o Windows

| Windows | Linux |
|----------|--------|
| Gerenciador de Dispositivos | `/dev` |
| Disco 0 | `/dev/sda` |
| Disco 1 | `/dev/sdb` |
| COM1 | `/dev/ttyS0` |

---

# 🛠️ Ferramentas que utilizam este diretório

Diversas ferramentas trabalham diretamente com dispositivos presentes em `/dev`.

Exemplos:

- lsblk
- fdisk
- mount
- umount
- dd
- mkfs
- parted

---

# Pratique

Entre no diretório:

```bash
cd /dev
```

Confira onde está:

```bash
pwd
```

Liste os primeiros arquivos:

```bash
ls | head
```

Agora visualize apenas os discos:

```bash
ls /dev/sd*
```

Caso sua máquina utilize outro padrão, como NVMe, execute:

```bash
ls /dev/nvme*
```

---

# Explore

Descubra quais discos existem no sistema:

```bash
lsblk
```

Compare o resultado com os arquivos existentes em `/dev`.

Observe como cada dispositivo listado possui uma representação nesse diretório.

---

# 💼 Exemplos do mundo real

Quando você grava uma imagem ISO em um pendrive utilizando ferramentas como `dd`, está escrevendo diretamente em um dispositivo localizado em `/dev`.

Da mesma forma, ao montar um HD externo, o sistema utiliza os arquivos desse diretório para acessar o hardware.

---

# ⚠️ Pode alterar?

| Diretório | Pode alterar? | Observação |
|-----------|---------------|------------|
| `/dev` | ❌ Evite | Alterações incorretas podem causar perda de dados ou impedir o acesso a dispositivos. |

---

# 💡 Dica profissional

Antes de executar comandos que escrevem diretamente em dispositivos (como `dd`), confirme cuidadosamente o nome do dispositivo com `lsblk`.

Um erro pode sobrescrever completamente um disco.

---

# Você sabia?

Os arquivos em `/dev` normalmente não são armazenados permanentemente no disco.

Eles são criados dinamicamente pelo Kernel por meio do **udev**, conforme os dispositivos são detectados.

---

# Resumo rápido

| Situação | Comando |
|----------|----------|
| Entrar em `/dev` | `cd /dev` |
| Listar dispositivos | `ls` |
| Listar discos | `lsblk` |
| Listar discos SATA | `ls /dev/sd*` |

---

# Erros comuns

- Confundir dispositivos com arquivos comuns.
- Utilizar `dd` no dispositivo errado.
- Alterar permissões sem compreender suas consequências.

---

# Referências

- Linux Foundation
- Filesystem Hierarchy Standard (FHS)
- Ubuntu Documentation
- Manual do udev

---

# Conclusão

Neste capítulo você conheceu o diretório `/dev` e compreendeu uma das principais filosofias do Linux: tratar dispositivos como arquivos.

Também explorou dispositivos especiais e aprendeu como o Kernel representa o hardware dentro do sistema operacional.

---

# 🔗 Revisite este conceito

Lembre-se do capítulo sobre o Kernel no **Módulo 01**.

É o Kernel quem detecta os dispositivos e, com o auxílio do **udev**, cria automaticamente os arquivos correspondentes em `/dev`.

---

# Prepare-se para o próximo capítulo

Agora conheceremos dois diretórios muito especiais:

**`/proc`** e **`/sys`**.

Eles não armazenam arquivos comuns.

Na verdade, eles mostram informações do Kernel e do hardware **em tempo real**, funcionando como uma janela para o funcionamento interno do Linux.
