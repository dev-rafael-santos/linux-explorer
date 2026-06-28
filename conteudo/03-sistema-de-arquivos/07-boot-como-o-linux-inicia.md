# 07. `/boot` — Como o Linux inicia

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 40 minutos

**Pré-requisitos:**

- Módulo 01 — Fundamentos do Linux
- Módulo 02 — Terminal
- Capítulos anteriores deste módulo

────────────────────────────────────────────

# Visão Geral

Imagine que você pressiona o botão Power do computador.

Em poucos segundos aparece a tela do Ubuntu.

Mas o que aconteceu durante esse tempo?

Existe um conjunto de arquivos responsáveis por permitir que o Linux seja carregado corretamente.

Grande parte deles está localizada no diretório **`/boot`**.

Neste capítulo você conhecerá esse diretório e entenderá sua importância para a inicialização do sistema.

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

- Entender a função do diretório `/boot`.
- Conhecer seus principais arquivos.
- Compreender o processo de inicialização do Linux.
- Entender por que alterações nesse diretório exigem cuidado.

---

# Por que isso é importante?

Sem os arquivos presentes em `/boot`, o Linux não consegue iniciar.

Embora seja um diretório pequeno, ele é essencial para o funcionamento do sistema operacional.

Mesmo desenvolvedores costumam encontrá-lo ao instalar novos kernels ou solucionar problemas de inicialização.

---

# Quando você usará isso?

Você encontrará o diretório `/boot` em situações como:

- Atualização do Kernel.
- Recuperação do sistema.
- Configuração do GRUB.
- Solução de problemas de inicialização.
- Administração de servidores.
- Dual Boot.

---

# Você vai conhecer

| Item | Informação |
|------|------------|
| Diretório | `/boot` |
| Categoria | Inicialização do sistema |
| Importância | ⭐⭐⭐⭐⭐ |
| Utilizado diariamente? | ❌ Não |
| Pode alterar? | ❌ Evite |
| Equivalente no Windows | Partição EFI + Boot Manager (aproximadamente) |

---

# O que é o diretório `/boot`?

O diretório `/boot` contém os arquivos necessários para iniciar o Linux.

Entre eles estão:

- Kernel Linux
- initramfs
- arquivos do GRUB
- arquivos auxiliares da inicialização

Sem esses arquivos o sistema operacional não consegue ser carregado.

---

# Como funciona

Quando o computador é ligado, diversos componentes trabalham juntos até que a tela de login seja exibida.

O diretório `/boot` participa justamente dessa etapa.

---

# 🔄 Fluxo completo

```text
Botão Power
      │
      ▼
 BIOS / UEFI
      │
      ▼
 Bootloader (GRUB)
      │
      ▼
 Kernel Linux
      │
      ▼
 initramfs
      │
      ▼
 Sistema de Arquivos
      │
      ▼
 Serviços do Sistema
      │
      ▼
 Tela de Login
```

Observe que o diretório `/boot` fornece os arquivos utilizados nas etapas do GRUB, do Kernel e do initramfs.

---

# O que normalmente você encontrará aqui?

```text
/boot
│
├── vmlinuz
├── initrd.img
├── grub/
├── System.map
└── config
```

Arquivos comuns:

| Arquivo | Função |
|----------|--------|
| `vmlinuz` | Kernel Linux |
| `initrd.img` | Sistema temporário carregado na memória |
| `grub/` | Arquivos do bootloader GRUB |
| `System.map` | Mapeamento de símbolos do Kernel |
| `config` | Configuração do Kernel utilizado |

---

# Comparando com o Windows

| Windows | Linux |
|----------|--------|
| Windows Boot Manager | GRUB |
| winload.efi | Kernel Linux |
| Partição EFI | `/boot` (em conjunto com a ESP quando utilizada) |

Embora existam diferenças importantes, ambos possuem arquivos responsáveis pela inicialização do sistema.

---

# 🛠️ Ferramentas que utilizam este diretório

Durante a administração do sistema é comum encontrar ferramentas como:

- GRUB
- update-grub
- update-initramfs
- Kernel Linux
- UEFI

Essas ferramentas trabalham diretamente com arquivos localizados em `/boot` ou relacionados ao processo de inicialização.

---

# Pratique

Entre no diretório:

```bash
cd /boot
```

Confira onde está:

```bash
pwd
```

Liste os arquivos:

```bash
ls
```

Caso existam vários kernels instalados:

```bash
ls -lh
```

Observe os nomes dos arquivos.

Não altere nenhum deles.

---

# Explore

Procure pelo diretório do GRUB:

```bash
ls /boot/grub
```

Depois observe os arquivos do Kernel:

```bash
ls /boot | grep vmlinuz
```

Cada distribuição pode apresentar pequenas diferenças na organização dos arquivos.

---

# 💼 Exemplos do mundo real

Imagine que uma atualização do Kernel foi instalada.

Os novos arquivos serão adicionados ao diretório `/boot`.

Outro exemplo ocorre quando um computador apresenta falha de inicialização.

Uma das primeiras verificações realizadas por administradores é justamente confirmar se os arquivos do `/boot` estão íntegros.

---

# ⚠️ Pode alterar?

| Diretório | Pode alterar? | Observação |
|-----------|---------------|------------|
| `/boot` | ❌ Evite | Alterações incorretas podem impedir a inicialização do sistema. |

---

# 💡 Dica profissional

Evite remover arquivos manualmente do diretório `/boot`.

A remoção de kernels antigos deve ser feita utilizando as ferramentas da própria distribuição, garantindo que todas as dependências sejam tratadas corretamente.

---

# Você sabia?

É comum um sistema Linux possuir mais de um Kernel instalado.

Isso permite iniciar uma versão anterior caso uma atualização apresente problemas.

Por esse motivo, ao listar o conteúdo de `/boot`, você pode encontrar diversos arquivos `vmlinuz` e `initrd.img` correspondentes a versões diferentes do Kernel.

---

# Resumo rápido

| Situação | Comando |
|----------|----------|
| Entrar em `/boot` | `cd /boot` |
| Listar arquivos | `ls` |
| Listar detalhadamente | `ls -lh` |
| Procurar kernels | `ls /boot | grep vmlinuz` |

---

# Erros comuns

- Excluir arquivos do Kernel manualmente.
- Alterar configurações do GRUB sem backup.
- Assumir que `/boot` armazena todo o sistema operacional.
- Confundir o diretório `/boot` com a partição EFI.

---

# Referências

- Filesystem Hierarchy Standard (FHS)
- Ubuntu Documentation
- GNU GRUB Manual
- Linux Foundation

---

# Conclusão

Neste capítulo você conheceu o diretório `/boot` e compreendeu seu papel na inicialização do Linux.

Também aprendeu como BIOS/UEFI, GRUB, Kernel e initramfs trabalham em conjunto para carregar o sistema operacional.

Esse conhecimento será útil sempre que precisar entender ou solucionar problemas relacionados ao processo de boot.

---

# Prepare-se para o próximo capítulo

Até agora conhecemos diretórios voltados para usuários, configurações, programas, dados variáveis, arquivos temporários e inicialização.

No próximo capítulo estudaremos um dos diretórios mais curiosos do Linux:

**`/dev`**, onde dispositivos de hardware são representados como arquivos.
