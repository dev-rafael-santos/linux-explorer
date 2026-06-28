# Guia de Estilo — Linux Explorer

Este documento define o padrão oficial de escrita utilizado em todo o projeto **Linux Explorer**.

Seu objetivo é garantir consistência, qualidade e uma excelente experiência de aprendizagem para todos os leitores.

Todo novo conteúdo deve seguir este guia.

---

# Nossa missão

O Linux Explorer existe para ensinar Linux de forma clara, organizada e prática.

Nosso foco não é ensinar comandos.

Nosso foco é ensinar como o Linux funciona.

Queremos que o estudante compreenda os conceitos e desenvolva autonomia para continuar aprendendo por conta própria.

---

# Filosofia do projeto

Todo conteúdo deve seguir estes princípios.

## 1. Conceitos antes de comandos

Nunca apresente um comando antes de explicar o conceito.

Primeiro explique:

* O que é.
* Para que serve.
* Quando utilizar.

Depois mostre o comando.

---

## 2. Evolução progressiva

Cada capítulo deve depender apenas do conhecimento apresentado anteriormente.

Evite assumir que o leitor já conhece um assunto.

Construa o aprendizado passo a passo.

---

## 3. Aprendizado ativo

Sempre que possível, faça o leitor praticar.

Cada capítulo deve conter:

* exemplos;
* laboratório guiado;
* desafio.

O objetivo é transformar leitura em experiência prática.

---

## 4. Explicar antes de decorar

Não queremos que o estudante memorize comandos.

Queremos que ele compreenda por que eles existem e quando utilizá-los.

---

# Tom de voz

Todo o conteúdo deve ser escrito utilizando uma linguagem:

* clara;
* objetiva;
* amigável;
* profissional;
* acessível para iniciantes.

Evite:

* excesso de formalidade;
* excesso de informalidade;
* jargões sem explicação;
* frases muito longas.

Escreva como um professor experiente explicando o assunto para um aluno curioso.

---

# Estrutura oficial dos capítulos

Todos os capítulos seguem a seguinte estrutura:

```text
Título

Visão Geral

O que você aprenderá

Por que isso é importante?

Você vai conhecer

Conceitos

Como funciona

Comparando com o Windows (quando aplicável)

Exemplo

Pratique

Explore

Resumo rápido

Erros comuns

Curiosidade

Referências

Conclusão

Prepare-se para o próximo capítulo
```

Essa estrutura deve ser mantida sempre que possível.

---

# Escrita

Utilize frases curtas.

Cada parágrafo deve desenvolver apenas uma ideia.

Prefira:

✔️ Explicações simples.

✔️ Analogias.

✔️ Exemplos reais.

✔️ Comparações.

Evite textos excessivamente longos.

---

# Diagramas

Sempre que possível utilize diagramas ASCII.

Exemplo:

```text
Aplicação

↓

Shell

↓

Kernel

↓

Hardware
```

Ou:

```text
/
├── home
├── etc
├── usr
└── var
```

Diagramas ajudam muito na compreensão.

---

# Comparações com Windows

Sempre que fizer sentido, compare os conceitos.

Exemplo:

| Windows  | Linux |
| -------- | ----- |
| C:\Users | /home |
| Registro | /etc  |

Esse tipo de comparação facilita a migração para quem vem do Windows.

---

# Exemplos

Todo conceito deve possuir exemplos.

Boas práticas:

* utilizar exemplos simples;
* explicar a saída apresentada;
* mostrar situações reais;
* incentivar o leitor a reproduzir o exemplo.

Nunca apresente um comando sem explicar seu resultado.

---

# Laboratórios

Todo capítulo deve possuir uma seção **Pratique**.

O laboratório deve:

* apresentar um objetivo claro;
* explicar cada passo;
* mostrar o resultado esperado.

---

# Desafios

Todo capítulo deve possuir uma seção **Explore**.

O desafio deve incentivar o estudante a experimentar.

Sempre que possível, evite fornecer imediatamente a resposta.

---

# Erros comuns

Sempre que possível liste:

* erros frequentes;
* causas;
* formas de evitar.

Isso reduz a frustração do estudante.

---

# Referências

Priorize documentação oficial.

Exemplos:

* GNU Project
* Linux Foundation
* Ubuntu Documentation
* Kernel.org

Quando utilizar outras referências, verifique sua confiabilidade.

---

# Padrão de nomenclatura

## Diretórios

Utilizar:

```text
03-sistema-de-arquivos
```

Evitar:

```text
SistemaArquivos
```

ou

```text
Sistema de Arquivos
```

---

## Arquivos

Utilizar:

```text
01-o-diretorio-raiz.md
```

Sempre:

* numerados;
* letras minúsculas;
* separados por hífen.

---

# Materiais complementares

Todo módulo deve possuir:

```text
README.md

CHEATSHEET.md

RESUMO.md
```

Esses arquivos fazem parte da estrutura oficial do Linux Explorer.

---

# Qualidade

Antes da publicação, verifique:

* Todos os exemplos foram testados.
* Não existem erros ortográficos.
* Os comandos funcionam.
* Os diagramas estão corretos.
* As referências são confiáveis.
* O capítulo segue o TEMPLATE_CAPITULO.md.

---

# Objetivo final

O Linux Explorer pretende ser uma referência em língua portuguesa para o aprendizado de Linux.

Mais do que ensinar comandos, queremos desenvolver profissionais capazes de compreender o funcionamento do sistema operacional e utilizar esse conhecimento em situações reais.

Cada capítulo publicado deve aproximar o projeto desse objetivo.
