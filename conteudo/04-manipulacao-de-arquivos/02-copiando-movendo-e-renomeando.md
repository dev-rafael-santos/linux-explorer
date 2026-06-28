# 02. Copiando, Movendo e Renomeando Arquivos

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 45 minutos

**Pré-requisitos:**

* Capítulo 00 — Preparando o Linux Explorer Lab
* Capítulo 01 — Criando Arquivos e Diretórios

────────────────────────────────────────────

# Visão Geral

Criar arquivos é apenas o primeiro passo.

No dia a dia, você frequentemente precisará copiar documentos, mover arquivos entre diretórios e renomear pastas ou arquivos para manter tudo organizado.

Neste capítulo você aprenderá a utilizar os comandos `cp` e `mv`, dois dos comandos mais importantes do Linux.

Todos os exercícios serão realizados dentro do Linux Explorer Lab.

---

# Estado atual do laboratório

Antes de começar, seu laboratório deverá estar semelhante a este:

```text
linux-explorer-lab
│
├── backup
├── compactados
├── documentos
│   ├── clientes.txt
│   ├── fornecedores.txt
│   ├── meu-primeiro-arquivo.txt
│   └── produtos.txt
│
├── downloads
├── imagens
│
├── projetos
│   ├── api
│   │   └── app.py
│   ├── ecommerce
│   ├── mobile
│   └── site
│       └── index.html
│
├── temporarios
└── testes
```

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

* Copiar arquivos.
* Copiar diretórios.
* Mover arquivos.
* Renomear arquivos.
* Renomear diretórios.
* Organizar projetos utilizando o Terminal.

---

# Por que isso é importante?

Organizar arquivos faz parte da rotina de qualquer profissional.

Projetos crescem.

Novos diretórios são criados.

Arquivos precisam ser reorganizados constantemente.

Dominar esses comandos aumenta muito sua produtividade.

---

# Quando você usará isso?

Você utilizará esses comandos para:

* organizar projetos;
* criar backups;
* copiar configurações;
* mover arquivos entre pastas;
* renomear documentos;
* reorganizar diretórios.

---

# Você vai conhecer

| Comando | Finalidade                              |
| ------- | --------------------------------------- |
| `cp`    | Copiar arquivos e diretórios            |
| `mv`    | Mover ou renomear arquivos e diretórios |

---

# O comando `cp`

O comando `cp` copia arquivos.

Sintaxe:

```bash
cp origem destino
```

Exemplo:

```bash
cp documentos/clientes.txt backup/
```

O arquivo original permanece onde está.

Uma cópia é criada no diretório de destino.

---

# Copiando vários arquivos

Também é possível copiar diversos arquivos utilizando um único comando.

Exemplo:

```bash
cp documentos/*.txt backup/
```

Todos os arquivos `.txt` serão copiados para o diretório `backup`.

---

# Copiando diretórios

Para copiar diretórios utilize a opção `-r` (recursiva).

Exemplo:

```bash
cp -r projetos backup/
```

Toda a estrutura será copiada.

---

# O comando `mv`

O comando `mv` possui duas funções.

Ele pode:

* mover arquivos;
* renomear arquivos ou diretórios.

Exemplo:

```bash
mv documentos/produtos.txt downloads/
```

O arquivo será removido do diretório original e colocado no novo local.

---

# Renomeando arquivos

O mesmo comando pode ser utilizado para alterar nomes.

Exemplo:

```bash
mv documentos/clientes.txt documentos/clientes-antigos.txt
```

O conteúdo permanece exatamente igual.

Apenas o nome do arquivo muda.

---

# Renomeando diretórios

Também é possível renomear pastas.

Exemplo:

```bash
mv projetos/mobile projetos/app-mobile
```

Todo o conteúdo continuará existindo.

Apenas o nome do diretório será alterado.

---

# 🧠 Como o Linux enxerga isso?

Para o Linux, mover um arquivo dentro do mesmo sistema de arquivos normalmente significa apenas atualizar sua localização na estrutura de diretórios.

Já uma cópia cria um novo arquivo com o mesmo conteúdo.

Embora ambos pareçam semelhantes para o usuário, internamente são operações diferentes.

---

# O que normalmente você encontrará aqui?

Durante este capítulo você criará:

* cópias de segurança;
* arquivos reorganizados;
* diretórios renomeados;
* estruturas mais organizadas.

Essas alterações servirão de base para os próximos exercícios.

---

# Comparando com Windows

| Windows                | Linux    |
| ---------------------- | -------- |
| Ctrl+C / Ctrl+V        | `cp`     |
| Recortar               | `mv`     |
| Renomear               | `mv`     |
| Explorador de Arquivos | Terminal |

---

# 🛠️ Ferramentas que utilizam esses comandos

Os comandos `cp` e `mv` são utilizados constantemente por:

* Git
* Docker
* Shell Scripts
* Ferramentas de backup
* Instaladores de aplicações
* Scripts de deploy
* Sistemas de automação

Sempre que arquivos precisam ser organizados ou distribuídos, esses comandos estão entre os mais utilizados.

---

# Pratique

Entre no laboratório:

```bash
cd ~/linux-explorer-lab
```

Copie um arquivo para a pasta de backup:

```bash
cp documentos/clientes.txt backup/
```

Agora copie todos os arquivos `.txt`:

```bash
cp documentos/*.txt backup/
```

Liste o conteúdo da pasta `backup`:

```bash
ls backup
```

Agora mova um arquivo:

```bash
mv documentos/produtos.txt downloads/
```

Confira o resultado:

```bash
ls documentos
```

```bash
ls downloads
```

Agora renomeie um arquivo:

```bash
mv documentos/fornecedores.txt documentos/fornecedores-antigos.txt
```

Confira:

```bash
ls documentos
```

---

# 🧪 Experimento

Vamos organizar um projeto.

Crie uma pasta para arquivos antigos:

```bash
mkdir documentos/arquivados
```

Agora mova o arquivo renomeado:

```bash
mv documentos/fornecedores-antigos.txt documentos/arquivados/
```

Visualize a estrutura:

```bash
tree documentos
```

Observe como apenas a organização mudou.

O conteúdo do arquivo continua exatamente o mesmo.

---

# Explore

Copie todo o diretório `projetos` para `backup`:

```bash
cp -r projetos backup/
```

Agora visualize:

```bash
tree backup
```

Compare a estrutura original com a cópia.

Perceba que o conteúdo foi preservado.

---

# 💼 Exemplos do mundo real

Imagine que você está desenvolvendo uma aplicação.

Antes de realizar uma grande alteração, cria uma cópia do projeto:

```bash
cp -r sistema sistema-backup
```

Outra situação comum é reorganizar arquivos após uma entrega:

```bash
mv relatorio-final.pdf entregas/
```

Essas operações fazem parte da rotina de administradores de sistemas, desenvolvedores e engenheiros de dados.

---

# ⚠️ Pode alterar?

| Local                  | Pode alterar? | Observação                                  |
| ---------------------- | ------------- | ------------------------------------------- |
| `~/linux-explorer-lab` | ✅ Sim         | Ambiente destinado aos exercícios do curso. |

---

# 💡 Dica profissional

Antes de mover ou renomear arquivos importantes, confirme o diretório atual utilizando:

```bash
pwd
```

Esse hábito simples evita que arquivos sejam movidos para locais incorretos.

---

# 🧠 Mentalidade Linux

No Linux, copiar não substitui o original.

Mover normalmente significa alterar a localização do arquivo.

Saber escolher entre `cp` e `mv` evita perda de tempo e reduz erros durante a organização de projetos.

---

# Você sabia?

Quando um arquivo é movido dentro do mesmo sistema de arquivos, a operação costuma ser muito rápida.

Isso acontece porque, em muitos casos, o sistema apenas atualiza a referência para a nova localização, sem copiar novamente todo o conteúdo.

---

# 🏁 Estado esperado do laboratório

Ao concluir este capítulo, seu laboratório deverá estar semelhante a este:

```text
linux-explorer-lab
│
├── backup
│   ├── clientes.txt
│   ├── fornecedores.txt
│   ├── meu-primeiro-arquivo.txt
│   ├── produtos.txt
│   └── projetos
│
├── compactados
│
├── documentos
│   ├── arquivados
│   │   └── fornecedores-antigos.txt
│   │
│   ├── clientes.txt
│   └── meu-primeiro-arquivo.txt
│
├── downloads
│   └── produtos.txt
│
├── imagens
│
├── projetos
│   ├── api
│   │   └── app.py
│   ├── app-mobile
│   ├── ecommerce
│   └── site
│       └── index.html
│
├── temporarios
└── testes
```

---

# Resumo rápido

| Comando                | Finalidade                    |
| ---------------------- | ----------------------------- |
| `cp origem destino`    | Copiar arquivo                |
| `cp -r origem destino` | Copiar diretório              |
| `mv origem destino`    | Mover arquivo                 |
| `mv antigo novo`       | Renomear arquivo ou diretório |

---

# Erros comuns

* Esquecer a opção `-r` ao copiar diretórios.
* Mover arquivos sem verificar o diretório atual.
* Confundir copiar com mover.
* Renomear arquivos acidentalmente ao utilizar `mv`.

---

# Referências

* GNU Coreutils
* Linux Foundation
* Ubuntu Documentation

---

# Conclusão

Neste capítulo você aprendeu a copiar, mover e renomear arquivos e diretórios utilizando os comandos `cp` e `mv`.

Essas operações fazem parte das atividades mais frequentes de qualquer profissional que utiliza Linux e serão utilizadas constantemente ao longo do restante do curso.

---

# 🔗 Revisite este conceito

Lembre-se do capítulo anterior, onde você criou arquivos e diretórios.

Agora você já consegue reorganizar essa estrutura, criando uma base sólida para administrar projetos utilizando apenas o Terminal.

---

# Prepare-se para o próximo capítulo

Até agora você aprendeu a criar, copiar, mover e renomear arquivos.

No próximo capítulo veremos um tema que exige bastante atenção:

**como excluir arquivos e diretórios com segurança**, utilizando os comandos `rm` e `rmdir`.

---

# 📈 Evolução do Linux Explorer Lab

## Competências conquistadas

Até este momento você já domina:

* ✅ Preparar um ambiente seguro para estudos.
* ✅ Criar arquivos com `touch`.
* ✅ Criar diretórios com `mkdir`.
* ✅ Criar estruturas completas com `mkdir -p`.
* ✅ Copiar arquivos e diretórios com `cp`.
* ✅ Mover arquivos com `mv`.
* ✅ Renomear arquivos e diretórios.
* ✅ Organizar projetos utilizando o Terminal.

A cada novo capítulo, seu laboratório evoluirá e novas competências serão adicionadas, simulando situações cada vez mais próximas da rotina profissional.
