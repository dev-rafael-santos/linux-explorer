# Resumo — Manipulação de Arquivos e Diretórios

Este resumo reúne os principais conceitos estudados no **Módulo 04**.

Seu objetivo é consolidar os conhecimentos adquiridos e servir como material de revisão rápida antes de avançar para o próximo módulo.

---

# Mapa mental

```text
Manipulação de Arquivos
│
├── Criar
│   ├── touch
│   └── mkdir
│
├── Organizar
│   ├── cp
│   └── mv
│
├── Remover
│   ├── rm
│   └── rmdir
│
├── Visualizar
│   ├── cat
│   ├── less
│   ├── head
│   └── tail
│
├── Localizar
│   ├── find
│   ├── locate
│   ├── which
│   └── whereis
│
├── Links
│   ├── ln
│   └── ln -s
│
└── Compactação
    ├── tar
    ├── gzip
    ├── zip
    └── unzip
```

---

# O conceito mais importante

Manipular arquivos no Linux vai muito além de criar e apagar documentos.

Um profissional precisa saber:

- criar;
- organizar;
- localizar;
- visualizar;
- compartilhar;
- proteger.

Cada comando apresentado neste módulo resolve um problema específico.

O segredo não está em decorar comandos, mas em compreender quando utilizar cada um.

---

# Linux Explorer Lab

Durante todo o módulo utilizamos um ambiente seguro para praticar.

```text
~/linux-explorer-lab
```

Esse laboratório permitiu experimentar comandos sem risco para os arquivos pessoais.

Sempre que desejar revisar este módulo, basta voltar ao laboratório e repetir os exercícios.

---

# Resumo dos comandos

## Criando arquivos

```bash
touch arquivo.txt
```

Cria arquivos vazios.

---

## Criando diretórios

```bash
mkdir projetos
```

Cria diretórios.

---

## Copiando

```bash
cp origem destino
```

Cria uma cópia do arquivo.

---

## Movendo

```bash
mv origem destino
```

Move arquivos entre diretórios.

Também é utilizado para renomear.

---

## Removendo

```bash
rm arquivo
```

Remove arquivos.

```bash
rmdir pasta
```

Remove diretórios vazios.

```bash
rm -r pasta
```

Remove diretórios completos.

---

## Visualizando

```bash
cat
```

Arquivo completo.

```bash
less
```

Arquivos grandes.

```bash
head
```

Primeiras linhas.

```bash
tail
```

Últimas linhas.

```bash
tail -f
```

Acompanhamento em tempo real.

---

## Localizando

```bash
find
```

Pesquisa arquivos.

```bash
locate
```

Pesquisa utilizando banco de dados.

```bash
which
```

Localiza executáveis.

```bash
whereis
```

Mostra executáveis, documentação e páginas de manual.

---

## Links

```bash
ln
```

Hard Link.

```bash
ln -s
```

Link Simbólico.

---

## Compactação

```bash
tar
```

Agrupa arquivos.

```bash
gzip
```

Compacta arquivos.

```bash
zip
```

Cria arquivos ZIP.

```bash
unzip
```

Extrai arquivos ZIP.

---

# Fluxo de trabalho aprendido

Durante este módulo você executou praticamente o mesmo fluxo utilizado em ambientes profissionais.

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
Compartilhar
   │
   ▼
Compactar
```

Esse ciclo aparece diariamente em atividades de desenvolvimento, administração de sistemas e DevOps.

---

# O que vale a pena memorizar?

Mais importante do que decorar comandos é memorizar suas responsabilidades.

| Situação | Comando |
|-----------|----------|
| Criar arquivo | `touch` |
| Criar diretório | `mkdir` |
| Copiar | `cp` |
| Mover ou renomear | `mv` |
| Remover | `rm` |
| Visualizar | `cat`, `less` |
| Pesquisar | `find` |
| Localizar programa | `which` |
| Criar link | `ln` |
| Compactar | `tar`, `zip` |

---

# O que você já é capaz de fazer?

Após concluir este módulo você consegue:

- criar arquivos e diretórios;
- organizar estruturas de projetos;
- copiar arquivos e pastas;
- mover e renomear arquivos;
- remover arquivos com segurança;
- visualizar arquivos de diferentes maneiras;
- acompanhar logs em tempo real;
- localizar arquivos e programas;
- criar Links Simbólicos e Hard Links;
- compactar e descompactar arquivos.

Essas habilidades representam uma parte importante da rotina de qualquer profissional Linux.

---

# Erros comuns

Evite estes erros:

- Trabalhar fora do laboratório.
- Executar `rm -r` sem conferir o diretório.
- Utilizar `cat` em arquivos muito grandes.
- Esquecer a opção `-r` ao copiar diretórios.
- Confundir Hard Links com Links Simbólicos.
- Extrair arquivos compactados sem verificar seu conteúdo.

---

# Dicas para continuar praticando

Antes de avançar para o próximo módulo:

- repita todos os laboratórios;
- refaça o desafio final;
- consulte o `CHEATSHEET.md`;
- crie novos diretórios e arquivos por conta própria;
- experimente combinar os comandos apresentados.

Quanto mais você praticar, mais naturais essas operações se tornarão.

---

# Conclusão

Neste módulo você desenvolveu uma das competências mais importantes para trabalhar com Linux: a manipulação de arquivos e diretórios.

Você aprendeu desde operações simples, como criar arquivos, até tarefas mais avançadas, como criar Links Simbólicos, localizar programas e compactar projetos.

Esses conhecimentos serão utilizados constantemente nos próximos módulos e servirão como base para administração de sistemas, automação e Shell Script.


