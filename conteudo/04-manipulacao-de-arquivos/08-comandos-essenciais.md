# 08. Comandos Essenciais para Manipulação de Arquivos

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 60 minutos

**Pré-requisitos:**

- Conclusão dos capítulos anteriores deste módulo.

────────────────────────────────────────────

# Visão Geral

Ao longo deste módulo você aprendeu diversos comandos para trabalhar com arquivos e diretórios.

Neste capítulo faremos uma revisão prática dos principais comandos apresentados.

O objetivo não é ensinar novos comandos, mas consolidar o conhecimento adquirido e criar uma referência rápida para consultas futuras.

---

# Estado atual do laboratório

Entre no laboratório:

```bash
cd ~/linux-explorer-lab
```

Confira sua localização:

```bash
pwd
```

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

- Escolher rapidamente o comando adequado para cada situação.
- Revisar os comandos mais importantes do módulo.
- Identificar boas práticas na manipulação de arquivos.
- Trabalhar com mais confiança utilizando o Terminal.

---

# Por que isso é importante?

Conhecer muitos comandos é útil.

Saber **qual comando utilizar em cada situação** é o que realmente faz diferença.

Este capítulo servirá como um guia de consulta rápida para o seu dia a dia.

---

# Quando você usará isso?

Sempre que precisar:

- criar arquivos;
- copiar projetos;
- mover documentos;
- excluir arquivos;
- localizar informações;
- visualizar arquivos;
- criar backups.

---

# Você vai revisar

| Categoria | Principais comandos |
|-----------|---------------------|
| Criação | `touch`, `mkdir` |
| Organização | `cp`, `mv` |
| Remoção | `rm`, `rmdir` |
| Visualização | `cat`, `less`, `head`, `tail` |
| Pesquisa | `find`, `locate`, `which`, `whereis` |
| Links | `ln`, `ln -s` |
| Compactação | `tar`, `gzip`, `gunzip`, `zip`, `unzip` |

---

# Tabela de referência rápida

## Criando arquivos

```bash
touch arquivo.txt
```

Cria um arquivo vazio.

---

## Criando diretórios

```bash
mkdir projetos
```

Cria um diretório.

---

## Criando estruturas completas

```bash
mkdir -p projeto/{css,js,img}
```

Cria vários diretórios de uma única vez.

---

## Copiando arquivos

```bash
cp origem destino
```

Cria uma cópia do arquivo.

---

## Copiando diretórios

```bash
cp -r origem destino
```

Copia diretórios completos.

---

## Movendo arquivos

```bash
mv origem destino
```

Move arquivos ou diretórios.

---

## Renomeando

```bash
mv antigo novo
```

Também é utilizado para renomear.

---

## Excluindo arquivos

```bash
rm arquivo.txt
```

Remove arquivos.

---

## Excluindo diretórios

```bash
rm -r diretorio
```

Remove diretórios contendo arquivos.

---

## Visualizando arquivos

```bash
cat arquivo.txt
```

Exibe todo o conteúdo.

---

```bash
less arquivo.txt
```

Ideal para arquivos grandes.

---

```bash
head arquivo.txt
```

Mostra o início do arquivo.

---

```bash
tail arquivo.txt
```

Mostra o final do arquivo.

---

```bash
tail -f arquivo.txt
```

Acompanha alterações em tempo real.

---

## Localizando arquivos

```bash
find . -name "*.txt"
```

Pesquisa arquivos.

---

```bash
which git
```

Localiza um executável.

---

```bash
whereis python3
```

Mostra executáveis, manuais e outros arquivos relacionados.

---

## Criando Links

```bash
ln arquivo copia
```

Cria um Hard Link.

---

```bash
ln -s arquivo atalho
```

Cria um Link Simbólico.

---

## Compactando

```bash
tar -czvf backup.tar.gz pasta
```

Cria um arquivo compactado.

---

## Extraindo

```bash
tar -xvf backup.tar.gz
```

Extrai um arquivo compactado.

---

# 🧠 Como o Linux enxerga isso?

Todos esses comandos trabalham sobre o mesmo sistema de arquivos.

Eles apenas executam operações diferentes:

- criar;
- copiar;
- mover;
- remover;
- localizar;
- visualizar;
- compactar.

Quando você compreende essa lógica, deixa de decorar comandos isolados e passa a entender como o Linux organiza e manipula informações.

---

# O que normalmente você utilizará?

Durante sua rotina profissional, alguns comandos aparecerão com muito mais frequência que outros.

Os mais utilizados são:

- `ls`
- `cd`
- `pwd`
- `touch`
- `mkdir`
- `cp`
- `mv`
- `rm`
- `cat`
- `less`
- `find`

Esses comandos formam a base da manipulação de arquivos no Linux.

---

# 🛠️ Ferramentas que utilizam esses comandos

Os comandos apresentados neste módulo são utilizados diariamente por profissionais e ferramentas como:

* Git
* Docker
* Kubernetes
* Visual Studio Code
* Shell Scripts
* Jenkins
* Ansible
* Sistemas de Backup
* Distribuições Linux

Independentemente da área de atuação, dominar esses comandos aumenta significativamente sua produtividade no Terminal.

---

# Pratique

Entre no laboratório:

```bash
cd ~/linux-explorer-lab
```

Agora realize uma sequência de operações.

Crie um novo diretório:

```bash
mkdir projetos/exemplo-final
```

Crie dois arquivos:

```bash
touch projetos/exemplo-final/README.md
touch projetos/exemplo-final/anotacoes.txt
```

Copie um arquivo:

```bash
cp documentos/clientes.txt projetos/exemplo-final/
```

Renomeie um arquivo:

```bash
mv projetos/exemplo-final/anotacoes.txt projetos/exemplo-final/notas.txt
```

Visualize o conteúdo:

```bash
cat projetos/exemplo-final/clientes.txt
```

Localize o arquivo:

```bash
find . -name "README.md"
```

Compacte o diretório:

```bash
tar -czvf compactados/exemplo-final.tar.gz projetos/exemplo-final
```

Liste o conteúdo do arquivo compactado:

```bash
tar -tvf compactados/exemplo-final.tar.gz
```

---

# 🧪 Desafio final do módulo

Sem consultar os capítulos anteriores, tente realizar as seguintes tarefas:

1. Criar um diretório chamado `desafio-final`.
2. Criar três arquivos dentro dele.
3. Copiar um dos arquivos para `backup`.
4. Renomear outro arquivo.
5. Localizar todos os arquivos `.txt`.
6. Criar um link simbólico para um dos arquivos.
7. Compactar o diretório inteiro.
8. Remover o diretório original.
9. Restaurar o conteúdo a partir do arquivo compactado.

Se conseguir concluir todas as etapas, significa que você dominou os principais conceitos deste módulo.

---

# Explore

Experimente combinar diferentes comandos.

Por exemplo:

Crie um novo projeto:

```bash
mkdir -p projetos/teste-final/{docs,img,src}
```

Depois:

```bash
touch projetos/teste-final/docs/manual.md
```

Copie:

```bash
cp projetos/teste-final/docs/manual.md backup/
```

Pesquise:

```bash
find . -name "*.md"
```

Esse tipo de prática aproxima os exercícios de situações reais.

---

# 💼 Exemplos do mundo real

Imagine que você precisa preparar uma nova versão de um sistema.

Durante esse processo você poderá:

* criar novos diretórios;
* copiar arquivos de configuração;
* mover relatórios;
* remover arquivos antigos;
* localizar scripts;
* criar links;
* compactar todo o projeto para distribuição.

Perceba que praticamente todo o fluxo de trabalho utiliza comandos apresentados neste módulo.

---

# ⚠️ Pode alterar?

| Local                  | Pode alterar? | Observação                                                          |
| ---------------------- | ------------- | ------------------------------------------------------------------- |
| `~/linux-explorer-lab` | ✅ Sim         | Continue utilizando esse ambiente para praticar sempre que desejar. |

O laboratório foi criado exatamente para que você possa experimentar sem riscos.

---

# 💡 Dica profissional

Não tente decorar dezenas de comandos.

Domine primeiro os mais utilizados.

Com o tempo, os demais passarão a fazer parte da sua rotina naturalmente.

Mais importante do que memorizar é compreender quando utilizar cada ferramenta.

---

# 🧠 Mentalidade Linux

Profissionais Linux não trabalham decorando comandos.

Eles entendem a responsabilidade de cada ferramenta.

Quando surge um problema, sabem escolher rapidamente o comando mais adequado.

Essa é a habilidade que diferencia um iniciante de alguém experiente.

---

# Você sabia?

Grande parte das interfaces gráficas do Linux executa exatamente esses comandos "por trás das cortinas".

Ao utilizar o Terminal, você está acessando diretamente as mesmas funcionalidades, porém com muito mais controle e flexibilidade.

---

# 🏁 Estado esperado do laboratório

Ao concluir este capítulo, seu laboratório deverá conter toda a estrutura construída ao longo do módulo, além dos arquivos utilizados no desafio final.

Você poderá reutilizar esse ambiente sempre que desejar revisar comandos ou experimentar novas ideias.

---

# Resumo rápido

| Categoria   | Comandos                                |
| ----------- | --------------------------------------- |
| Criar       | `touch`, `mkdir`                        |
| Copiar      | `cp`                                    |
| Mover       | `mv`                                    |
| Remover     | `rm`, `rmdir`                           |
| Visualizar  | `cat`, `less`, `head`, `tail`           |
| Localizar   | `find`, `locate`, `which`, `whereis`    |
| Links       | `ln`, `ln -s`                           |
| Compactação | `tar`, `gzip`, `gunzip`, `zip`, `unzip` |

---

# Erros comuns

* Trabalhar fora do laboratório.
* Não verificar o diretório atual antes de executar comandos.
* Utilizar `rm -r` sem conferir o conteúdo.
* Esquecer de utilizar `-r` ao copiar diretórios.
* Compactar ou extrair arquivos no diretório incorreto.

---

# Referências

* GNU Coreutils
* GNU Findutils
* GNU Tar Manual
* Linux Foundation
* Ubuntu Documentation

---

# Conclusão

Parabéns!

Você concluiu o **Módulo 04 — Manipulação de Arquivos**.

Ao longo deste módulo você aprendeu a criar, organizar, localizar, visualizar, remover, compactar arquivos e utilizar links no Linux.

Essas habilidades representam a base da manipulação de arquivos no sistema operacional e serão utilizadas constantemente nos próximos módulos.

---

# 🔗 Revisite este módulo

Antes de avançar, revise:

* o **CHEATSHEET.md**;
* o **RESUMO.md**;
* os exercícios práticos;
* o Linux Explorer Lab.

Quanto mais você praticar, mais naturais esses comandos se tornarão.

---

# 📈 Evolução do Linux Explorer Lab

## Competências conquistadas

Ao concluir este módulo você já domina:

* ✅ Preparar um ambiente seguro para estudos.
* ✅ Criar arquivos e diretórios.
* ✅ Copiar arquivos e diretórios.
* ✅ Mover e renomear arquivos.
* ✅ Excluir arquivos e diretórios com segurança.
* ✅ Visualizar arquivos com `cat`, `less`, `head` e `tail`.
* ✅ Acompanhar arquivos em tempo real com `tail -f`.
* ✅ Localizar arquivos e programas.
* ✅ Criar Links Simbólicos e Hard Links.
* ✅ Compactar e descompactar arquivos.
* ✅ Escolher o comando adequado para cada situação.

🎉 **Parabéns! Você concluiu com sucesso o Módulo 04 do Linux Explorer.**

