# 00. Preparando o Linux Explorer Lab

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 20 minutos

**Pré-requisitos:**

- Módulo 01 — Fundamentos do Linux
- Módulo 02 — Terminal Linux
- Módulo 03 — Sistema de Arquivos Linux

────────────────────────────────────────────

# Visão Geral

Bem-vindo ao **Linux Explorer Lab**.

A partir deste módulo, você começará a criar, copiar, mover, renomear e excluir arquivos utilizando o Terminal.

Essas operações fazem parte da rotina de qualquer profissional que trabalha com Linux.

Para evitar alterações acidentais em documentos pessoais ou arquivos importantes do sistema, utilizaremos um ambiente de laboratório criado exclusivamente para os exercícios deste curso.

Durante todo este módulo, praticamente todos os exemplos serão realizados dentro desse ambiente.

---

# O que você aprenderá

Ao concluir este capítulo você será capaz de:

- Criar o Linux Explorer Lab.
- Navegar até o laboratório.
- Compreender sua estrutura.
- Restaurar o ambiente sempre que desejar.
- Trabalhar com segurança durante os exercícios.

---

# Por que isso é importante?

Aprender envolve experimentar.

E experimentar significa cometer erros.

Criar um ambiente dedicado para os exercícios permite praticar livremente, sem risco de apagar documentos importantes ou modificar arquivos do sistema.

Essa também é uma prática comum em ambientes profissionais.

---

# Quando você usará isso?

Embora este laboratório tenha sido criado para o curso, a ideia por trás dele é utilizada diariamente por profissionais.

Você encontrará esse conceito em situações como:

- testes de scripts;
- desenvolvimento de aplicações;
- treinamento de equipes;
- estudos de novas ferramentas;
- validação de comandos antes de utilizá-los em produção.

---

# Você vai conhecer

| Item | Informação |
|------|------------|
| Ambiente | Linux Explorer Lab |
| Local | `~/linux-explorer-lab` |
| Finalidade | Ambiente de estudos |
| Pode alterar? | ✅ Sim |
| Pode apagar? | ✅ Sim |

---

# O que é o Linux Explorer Lab?

O Linux Explorer Lab é uma pasta criada exclusivamente para os exercícios deste curso.

Tudo o que você criar, modificar ou excluir durante este módulo ficará dentro dela.

Assim, você poderá repetir qualquer atividade quantas vezes desejar.

---

# Como funciona

A estrutura inicial será semelhante a esta:

```text
linux-explorer-lab
│
├── backup
├── compactados
├── documentos
├── downloads
├── imagens
├── projetos
├── temporarios
└── testes
```

Cada diretório será utilizado em diferentes exercícios ao longo do módulo.

---

# 🧠 Como o Linux enxerga isso?

Para o Linux, o Linux Explorer Lab é apenas mais um diretório dentro da sua pasta pessoal.

A diferença está no propósito.

Enquanto seus documentos pessoais permanecem organizados em outras pastas, este diretório será utilizado exclusivamente para aprendizado.

---

# Criando o laboratório

Execute o comando abaixo:

```bash
mkdir -p ~/linux-explorer-lab/{backup,compactados,documentos,downloads,imagens,projetos,temporarios,testes}
```

Agora entre no laboratório:

```bash
cd ~/linux-explorer-lab
```

Confirme sua localização:

```bash
pwd
```

O resultado deverá ser semelhante a:

```text
/home/seu-usuario/linux-explorer-lab
```

---

# O que normalmente você encontrará aqui?

| Diretório | Finalidade |
|-----------|------------|
| `backup` | Exercícios de cópia e restauração |
| `compactados` | Arquivos compactados |
| `documentos` | Arquivos de texto |
| `downloads` | Simulação de downloads |
| `imagens` | Arquivos de imagem |
| `projetos` | Projetos de exemplo |
| `temporarios` | Arquivos temporários |
| `testes` | Exercícios diversos |

---

# Pratique

Liste os diretórios criados:

```bash
ls
```

Agora visualize a estrutura completa:

```bash
tree
```

> Caso o comando `tree` não esteja instalado, utilize:

```bash
sudo apt install tree
```

Depois execute novamente:

```bash
tree
```

---

# 🧪 Experimento

Crie um arquivo de teste:

```bash
touch documentos/meu-primeiro-arquivo.txt
```

Agora visualize a estrutura:

```bash
tree
```

Observe como o novo arquivo aparece dentro do laboratório.

Você utilizará esse mesmo arquivo em diversos capítulos deste módulo.

---

# 💼 Exemplos do mundo real

É comum que empresas mantenham ambientes separados para desenvolvimento, homologação e produção.

O Linux Explorer Lab segue a mesma ideia.

Antes de executar comandos em arquivos reais, você pratica em um ambiente seguro.

Esse hábito reduz riscos e aumenta a confiança durante o trabalho.

---

# ⚠️ Pode alterar?

| Diretório | Pode alterar? | Observação |
|-----------|---------------|------------|
| `~/linux-explorer-lab` | ✅ Sim | Todo o conteúdo foi criado para os exercícios. |

---

# 💡 Dica profissional

Crie o hábito de testar comandos em um ambiente controlado antes de executá-los em projetos importantes.

Esse cuidado pode evitar perda de dados e economizar muitas horas de trabalho.

---

# 🧠 Mentalidade Linux

Profissionais experientes raramente aprendem diretamente em ambientes de produção.

Eles criam laboratórios, máquinas virtuais ou contêineres para experimentar novas ferramentas e comandos.

Esse é um hábito que vale a pena desenvolver desde o início.

---

# Você sabia?

Muitos cursos e certificações Linux utilizam ambientes isolados para que o aluno possa experimentar livremente.

Esse método reduz riscos e acelera o aprendizado.

---

# Resumo rápido

| Ação | Comando |
|------|----------|
| Criar o laboratório | `mkdir -p ...` |
| Entrar no laboratório | `cd ~/linux-explorer-lab` |
| Mostrar diretório atual | `pwd` |
| Listar conteúdo | `ls` |
| Mostrar estrutura | `tree` |

---

# Erros comuns

- Executar os exercícios fora do laboratório.
- Apagar arquivos pessoais por estar no diretório errado.
- Não verificar o diretório atual antes de utilizar comandos.

---

# Referências

- Linux Foundation
- Ubuntu Documentation

---

# Conclusão

Parabéns!

Agora você possui um ambiente preparado para realizar todos os exercícios deste módulo com segurança.

Nos próximos capítulos, utilizaremos esse laboratório para aprender a criar, copiar, mover, renomear e excluir arquivos e diretórios.

---

# Prepare-se para o próximo capítulo

Com o laboratório pronto, chegou o momento de realizar as primeiras operações.

No próximo capítulo você aprenderá a criar arquivos e diretórios utilizando os principais comandos do Linux.
