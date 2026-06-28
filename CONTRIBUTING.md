# Contribuindo com o Linux Explorer

Obrigado pelo interesse em contribuir com o **Linux Explorer**!

Este projeto tem como objetivo ensinar Linux de forma estruturada, progressiva e prática, permitindo que qualquer pessoa possa aprender desde os fundamentos até tópicos avançados.

Para manter a qualidade da documentação, algumas diretrizes devem ser seguidas.

---

# Nossa filosofia

O Linux Explorer não é apenas uma coleção de comandos.

Nosso objetivo é desenvolver a compreensão do sistema operacional.

Sempre que possível:

* explique os conceitos antes da prática;
* utilize exemplos reais;
* incentive o leitor a experimentar;
* construa o conhecimento de forma progressiva.

Não queremos que o leitor apenas decore comandos.

Queremos que ele compreenda o motivo de utilizá-los.

---

# Organização do projeto

A estrutura do projeto é organizada por módulos.

```text
conteudo/
│
├── 01-fundamentos-linux/
├── 02-terminal/
├── 03-sistema-de-arquivos/
├── ...
```

Cada módulo possui:

* `README.md`
* capítulos numerados
* `CHEATSHEET.md`
* `RESUMO.md`

---

# Estrutura dos capítulos

Todos os capítulos devem seguir o mesmo padrão.

```text
Título

Visão Geral

O que você aprenderá

Por que isso é importante?

Conceitos

Como funciona

Ficha do comando (quando aplicável)

Exemplo

Pratique

Explore

Erros comuns

Curiosidade

Referências

Conclusão

Prepare-se para o próximo passo
```

Esse padrão garante consistência em toda a documentação.

---

# Escrita

Utilize uma linguagem:

* clara;
* objetiva;
* amigável;
* técnica quando necessário.

Evite:

* jargões sem explicação;
* assumir conhecimento prévio;
* parágrafos excessivamente longos.

Sempre explique novos termos na primeira vez em que aparecerem.

---

# Exemplos

Todo conceito deve possuir pelo menos um exemplo.

Sempre que possível:

* utilize exemplos reais;
* explique a saída apresentada;
* incentive o leitor a reproduzir o exemplo.

---

# Comandos

Sempre que um novo comando for apresentado, inclua uma ficha técnica.

Modelo:

| Item                               | Descrição               |
| ---------------------------------- | ----------------------- |
| Nome                               | `pwd`                   |
| Significado                        | Print Working Directory |
| Categoria                          | Navegação               |
| Nível                              | Iniciante               |
| Uso diário                         | ⭐⭐⭐⭐⭐                   |
| Pode alterar arquivos?             | Não                     |
| Requer permissões administrativas? | Não                     |

---

# Laboratórios

Sempre que possível, inclua:

* um exercício guiado (**Pratique**);
* um pequeno desafio (**Explore**).

Essas atividades ajudam o leitor a consolidar o conhecimento.

---

# Padrão de commits

Utilize mensagens curtas e objetivas.

Exemplos:

```text
docs: adiciona capítulo 03

docs: revisa capítulo 05

docs: atualiza resumo do módulo

docs: corrige exemplos

docs: atualiza roadmap
```

Evite mensagens genéricas como:

* alterações
* correções
* atualização

---

# Fluxo de desenvolvimento

Cada módulo segue o seguinte processo:

```text
Planejamento

↓

Capítulos

↓

CHEATSHEET

↓

RESUMO

↓

Atualização do README

↓

Atualização do ROADMAP

↓

Revisão

↓

Commit de encerramento
```

Esse fluxo garante que todos os módulos mantenham a mesma qualidade.

---

# Boas práticas

* Teste todos os comandos antes de publicá-los.
* Utilize referências oficiais sempre que possível.
* Mantenha os capítulos independentes.
* Evite repetir explicações já apresentadas em capítulos anteriores.
* Prefira vários capítulos curtos a um capítulo excessivamente longo.

---

# Referências

Sempre priorize documentação oficial.

Exemplos:

* https://ubuntu.com/
* https://www.gnu.org/
* https://kernel.org/
* https://linuxfoundation.org/

---

# Código de conduta

Contribuições devem manter um ambiente respeitoso e colaborativo.

Sugestões, correções e melhorias são sempre bem-vindas.

O objetivo do projeto é compartilhar conhecimento e tornar o aprendizado de Linux acessível para todos.

---

# Obrigado!

Obrigado por contribuir com o Linux Explorer.

Esperamos que este projeto ajude milhares de pessoas a aprender Linux de forma clara, prática e consistente.

Bons estudos e boas contribuições! 🐧
