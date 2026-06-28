# Cheat Sheet — Sistema de Arquivos Linux

Este material reúne os principais diretórios do Linux apresentados no Módulo 03.

Utilize este arquivo como consulta rápida durante seus estudos ou no dia a dia.

---

# Visão geral da estrutura

```text
/
├── home
├── etc
├── usr
├── var
├── tmp
├── boot
├── dev
├── proc
├── sys
└── opt
```

---

# Diretório raiz (`/`)

## Função

É o ponto inicial de todo o sistema de arquivos Linux.

Todos os demais diretórios fazem parte dessa árvore.

### Comandos

```bash
cd /
pwd
ls /
```

---

# `/home`

## Função

Armazena os arquivos pessoais dos usuários.

### Exemplos

```text
/home/rafael
/home/maria
```

### Comandos

```bash
cd ~
pwd
ls
ls -la
```

---

# `/etc`

## Função

Armazena configurações do sistema.

### Arquivos importantes

```text
/etc/hostname
/etc/hosts
/etc/passwd
/etc/group
/etc/fstab
```

### Comandos

```bash
cd /etc
ls
cat /etc/hostname
```

---

# `/usr`

## Função

Armazena programas, bibliotecas e documentação.

### Subdiretórios

```text
/usr/bin
/usr/lib
/usr/share
/usr/local
/usr/sbin
/usr/src
```

### Comandos

```bash
cd /usr
ls
cd /usr/bin
```

---

# `/var`

## Função

Armazena dados que mudam constantemente.

### Subdiretórios

```text
/var/log
/var/cache
/var/lib
/var/spool
/var/tmp
```

### Comandos

```bash
cd /var
cd /var/log
ls
```

---

# `/tmp`

## Função

Armazena arquivos temporários.

### Comandos

```bash
cd /tmp
touch teste.tmp
rm teste.tmp
```

---

# `/boot`

## Função

Armazena arquivos utilizados durante a inicialização do sistema.

### Arquivos comuns

```text
vmlinuz
initrd.img
grub/
```

### Comandos

```bash
cd /boot
ls
ls -lh
```

---

# `/dev`

## Função

Representa dispositivos do sistema como arquivos.

### Exemplos

```text
/dev/sda
/dev/sda1
/dev/null
/dev/zero
/dev/random
```

### Comandos

```bash
lsblk
ls /dev
```

---

# `/proc`

## Função

Disponibiliza informações do Kernel e dos processos.

### Arquivos importantes

```text
/proc/cpuinfo
/proc/meminfo
/proc/uptime
```

### Comandos

```bash
cat /proc/cpuinfo
cat /proc/meminfo
cat /proc/uptime
```

---

# `/sys`

## Função

Disponibiliza informações sobre hardware e dispositivos.

### Comandos

```bash
cd /sys
ls
```

---

# `/opt`

## Função

Armazena aplicações opcionais instaladas manualmente.

### Exemplos

```text
/opt/android-studio
/opt/pycharm
/opt/intellij
```

### Comandos

```bash
cd /opt
ls
```

---

# Comparação rápida

| Diretório | Finalidade |
|------------|------------|
| `/` | Raiz do sistema |
| `/home` | Arquivos dos usuários |
| `/etc` | Configurações |
| `/usr` | Programas |
| `/var` | Logs e dados variáveis |
| `/tmp` | Arquivos temporários |
| `/boot` | Inicialização |
| `/dev` | Dispositivos |
| `/proc` | Informações do Kernel |
| `/sys` | Informações de hardware |
| `/opt` | Aplicações opcionais |

---

# Pode alterar?

| Diretório | Alterar? |
|------------|----------|
| `/home` | ✅ Sim |
| `/tmp` | ✅ Com cuidado |
| `/opt` | ⚠️ Com cuidado |
| `/etc` | ⚠️ Muito cuidado |
| `/usr` | ⚠️ Muito cuidado |
| `/var` | ⚠️ Muito cuidado |
| `/boot` | ❌ Evite |
| `/dev` | ❌ Evite |
| `/proc` | ❌ Evite |
| `/sys` | ❌ Evite |

---

# Conceitos importantes

✔ Tudo começa em `/`

✔ O Linux possui uma única árvore de diretórios.

✔ Dispositivos são representados como arquivos.

✔ Muitos arquivos em `/proc` e `/sys` são gerados em tempo real pelo Kernel.

✔ Cada diretório possui uma responsabilidade específica.

✔ Compreender essa organização facilita a administração do sistema.

---

# Dica profissional

Não tente decorar todos os diretórios.

Procure compreender **a responsabilidade de cada um**.

Quando você entende a lógica da organização do Linux, localizar arquivos e resolver problemas torna-se muito mais fácil.
