# 📄 Cheat Sheet — Módulo 06
# Gerenciamento de Pacotes

> Consulta rápida dos principais comandos apresentados neste módulo.

---

# 📦 Identificando o sistema

## Distribuição Linux

```bash
cat /etc/os-release
```

## Versão do Kernel

```bash
uname -r
```

## Descobrir o gerenciador de pacotes

```bash
which apt
which dnf
which yum
which pacman
which zypper
```

---

# 🔎 Pesquisando pacotes

Pesquisar um pacote:

```bash
apt search nome-do-pacote
```

Exemplo:

```bash
apt search git
```

---

# 📋 Informações de um pacote

```bash
apt show nome-do-pacote
```

Exemplo:

```bash
apt show curl
```

---

# 📥 Instalando programas

Instalar um pacote:

```bash
sudo apt install nome-do-pacote
```

Exemplo:

```bash
sudo apt install git
```

Instalar vários pacotes:

```bash
sudo apt install git curl wget
```

---

# 📤 Removendo programas

Remover um programa:

```bash
sudo apt remove nome-do-pacote
```

Remover incluindo arquivos de configuração:

```bash
sudo apt purge nome-do-pacote
```

---

# 🧹 Limpando dependências

Remover dependências não utilizadas:

```bash
sudo apt autoremove
```

Limpar cache:

```bash
sudo apt clean
```

---

# 🔄 Atualizando o sistema

Atualizar lista de pacotes:

```bash
sudo apt update
```

Atualizar programas:

```bash
sudo apt upgrade
```

Atualização completa:

```bash
sudo apt full-upgrade
```

Pacotes disponíveis para atualização:

```bash
apt list --upgradable
```

---

# 📚 Listando pacotes

Todos os pacotes instalados:

```bash
apt list --installed
```

Pesquisar um pacote instalado:

```bash
apt list --installed | grep git
```

---

# 🌍 Repositórios

Arquivo principal:

```text
/etc/apt/sources.list
```

Arquivos adicionais:

```text
/etc/apt/sources.list.d/
```

Visualizar:

```bash
cat /etc/apt/sources.list

ls /etc/apt/sources.list.d
```

---

# 📦 Snap

Pesquisar:

```bash
snap find nome
```

Instalar:

```bash
sudo snap install nome
```

Listar:

```bash
snap list
```

Remover:

```bash
sudo snap remove nome
```

Versão:

```bash
snap version
```

---

# 📦 Flatpak

Pesquisar:

```bash
flatpak search nome
```

Instalar:

```bash
flatpak install flathub aplicativo
```

Listar:

```bash
flatpak list
```

Remover:

```bash
flatpak uninstall aplicativo
```

Versão:

```bash
flatpak --version
```

---

# 📦 AppImage

Dar permissão:

```bash
chmod +x programa.AppImage
```

Executar:

```bash
./programa.AppImage
```

---

# ⚡ Fluxo recomendado

```text
Pesquisar
      │
      ▼
Consultar informações
      │
      ▼
Instalar
      │
      ▼
Utilizar
      │
      ▼
Atualizar
      │
      ▼
Remover
      │
      ▼
Executar autoremove
```

---

# 🧠 Conceitos importantes

| Conceito | Descrição |
|----------|-----------|
| Pacote | Forma de distribuição de software |
| Gerenciador de Pacotes | Ferramenta que instala e administra programas |
| Repositório | Servidor que armazena pacotes |
| Dependência | Biblioteca necessária para outro programa |
| APT | Gerenciador de pacotes do Ubuntu/Debian |
| Snap | Pacotes empacotados pela Canonical |
| Flatpak | Plataforma para aplicações desktop |
| AppImage | Aplicação portátil sem instalação |

---

# 💼 Boas práticas

- Utilize repositórios oficiais.
- Atualize o sistema regularmente.
- Evite instalar softwares desnecessários.
- Não misture tecnologias sem necessidade.
- Leia as mensagens exibidas pelo gerenciador.
- Utilize `sudo` apenas quando necessário.
- Remova dependências não utilizadas.
- Mantenha o sistema organizado.

---

# 🎯 Lembre-se

**Pesquisar → Instalar → Atualizar → Manter → Remover**

Essa é a rotina de qualquer administrador Linux.
