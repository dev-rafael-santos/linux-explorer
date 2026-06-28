# Cheat Sheet — Manipulação de Arquivos e Diretórios

Este material reúne os principais comandos apresentados no **Módulo 04**.

Utilize este arquivo como uma referência rápida durante seus estudos ou no dia a dia.

---

# Preparando o laboratório

Entrar no laboratório:

```bash
cd ~/linux-explorer-lab
```

Mostrar diretório atual:

```bash
pwd
```

Visualizar estrutura:

```bash
tree
```

---

# Criando arquivos e diretórios

Criar arquivo:

```bash
touch arquivo.txt
```

Criar vários arquivos:

```bash
touch a.txt b.txt c.txt
```

Criar diretório:

```bash
mkdir projetos
```

Criar vários diretórios:

```bash
mkdir frontend backend banco
```

Criar estrutura completa:

```bash
mkdir -p projeto/{css,js,img}
```

---

# Copiando arquivos

Copiar arquivo:

```bash
cp origem destino
```

Copiar vários arquivos:

```bash
cp documentos/*.txt backup/
```

Copiar diretório:

```bash
cp -r projetos backup/
```

---

# Movendo e renomeando

Mover arquivo:

```bash
mv origem destino
```

Renomear arquivo:

```bash
mv antigo novo
```

Renomear diretório:

```bash
mv pasta-antiga pasta-nova
```

---

# Removendo arquivos

Excluir arquivo:

```bash
rm arquivo.txt
```

Excluir com confirmação:

```bash
rm -i arquivo.txt
```

Excluir diretório vazio:

```bash
rmdir pasta
```

Excluir diretório completo:

```bash
rm -r pasta
```

---

# Visualizando arquivos

Mostrar conteúdo:

```bash
cat arquivo.txt
```

Visualizar arquivos grandes:

```bash
less arquivo.txt
```

Mostrar início:

```bash
head arquivo.txt
```

Mostrar cinco linhas:

```bash
head -5 arquivo.txt
```

Mostrar final:

```bash
tail arquivo.txt
```

Acompanhar alterações:

```bash
tail -f arquivo.txt
```

---

# Localizando arquivos

Pesquisar por nome:

```bash
find . -name "*.txt"
```

Pesquisar diretórios:

```bash
find . -type d
```

Pesquisar arquivos:

```bash
find . -type f
```

Localizar executável:

```bash
which git
```

Mais informações:

```bash
whereis git
```

Pesquisa rápida:

```bash
locate arquivo.txt
```

---

# Links

Criar Hard Link:

```bash
ln origem destino
```

Criar Link Simbólico:

```bash
ln -s origem destino
```

Ver Links Simbólicos:

```bash
ls -l
```

Ver inode:

```bash
ls -li
```

---

# Compactação

Criar TAR:

```bash
tar -cvf backup.tar documentos
```

Extrair TAR:

```bash
tar -xvf backup.tar
```

Criar TAR.GZ:

```bash
tar -czvf backup.tar.gz documentos
```

Listar conteúdo:

```bash
tar -tvf backup.tar.gz
```

Compactar arquivo:

```bash
gzip arquivo.txt
```

Descompactar:

```bash
gunzip arquivo.txt.gz
```

Criar ZIP:

```bash
zip -r backup.zip documentos
```

Extrair ZIP:

```bash
unzip backup.zip
```

---

# Fluxo básico de trabalho

```text
Criar
   │
   ▼
Organizar
   │
   ▼
Visualizar
   │
   ▼
Localizar
   │
   ▼
Compactar
   │
   ▼
Compartilhar
```

---

# Comandos mais utilizados

| Categoria | Comandos |
|------------|----------|
| Navegação | `cd`, `pwd`, `ls` |
| Arquivos | `touch`, `cp`, `mv`, `rm` |
| Diretórios | `mkdir`, `rmdir` |
| Visualização | `cat`, `less`, `head`, `tail` |
| Pesquisa | `find`, `which`, `whereis`, `locate` |
| Links | `ln`, `ln -s` |
| Compactação | `tar`, `gzip`, `gunzip`, `zip`, `unzip` |

---

# Boas práticas

✅ Trabalhe sempre dentro do laboratório.

✅ Confira o diretório atual utilizando:

```bash
pwd
```

✅ Antes de remover arquivos importantes:

```bash
ls
```

✅ Utilize:

```bash
rm -i
```

quando desejar confirmação.

✅ Antes de extrair arquivos compactados, visualize seu conteúdo.

---

# Dica profissional

Os comandos deste módulo são utilizados diariamente por administradores Linux, desenvolvedores, profissionais DevOps, engenheiros de dados e analistas de infraestrutura.

Quanto mais você praticar esses comandos, mais natural será seu uso no dia a dia.


