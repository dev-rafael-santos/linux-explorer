# 02. Como um computador inicia?

────────────────────────────────────────────

**Nível:** Iniciante

**Tempo estimado:** 20 minutos

**Pré-requisitos:**

* Capítulo 01 — O que é Linux?

────────────────────────────────────────────

# Visão Geral

Todos os dias ligamos computadores, notebooks e servidores sem pensar muito no que acontece nos primeiros segundos.

Apertamos o botão de energia e, poucos instantes depois, o sistema operacional está pronto para uso.

Mas...

**O que acontece nesse intervalo?**

Será que o Linux já está funcionando assim que apertamos o botão?

A resposta é **não**.

Antes que o Linux possa assumir o controle do computador, existe uma sequência de etapas que acontecem automaticamente.

Entender esse processo é fundamental para compreender como um sistema operacional funciona.

---

# O que você aprenderá

Ao final deste capítulo você será capaz de:

* Entender as etapas da inicialização de um computador.
* Conhecer o papel do firmware (BIOS ou UEFI).
* Compreender o que é um bootloader.
* Saber quando o Kernel Linux entra em ação.
* Visualizar a sequência completa do processo de inicialização.

---

# Por que isso é importante?

Imagine assistir a um filme começando pela metade.

Você provavelmente entenderá parte da história, mas perderá acontecimentos importantes.

Com Linux acontece o mesmo.

Antes de estudar o Kernel, precisamos entender **como ele chega até a memória do computador**.

Esse conhecimento facilitará bastante os próximos capítulos.

---

# Conceitos

Quando você pressiona o botão de energia, o computador ainda **não conhece o Linux**.

Naquele momento existe apenas hardware.

Para que tudo funcione, vários componentes entram em ação em uma ordem específica.

A sequência simplificada é esta:

```text
Botão de energia
        │
        ▼
 BIOS ou UEFI
        │
        ▼
 Bootloader
        │
        ▼
 Kernel Linux
        │
        ▼
 Sistema Operacional
        │
        ▼
 Tela de Login
```

Cada etapa possui uma responsabilidade diferente.

Vamos entender cada uma delas.

---

## 1. Botão de energia

Tudo começa quando você pressiona o botão de ligar.

A placa-mãe energiza os componentes do computador.

Nesse momento o processador começa a executar as primeiras instruções.

Ainda não existe Linux em execução.

---

## 2. BIOS ou UEFI

A primeira tarefa é executada pelo firmware da placa-mãe.

Dependendo do computador, esse firmware será:

* BIOS (mais antiga)
* UEFI (mais moderna)

Sua função é:

* verificar se o hardware está funcionando;
* identificar discos e dispositivos;
* localizar um sistema que possa ser iniciado.

---

## 3. Bootloader

Depois de localizar um sistema operacional, o firmware entrega o controle para um pequeno programa chamado **Bootloader**.

O Bootloader é responsável por localizar o Kernel Linux e carregá-lo na memória.

Nas distribuições Linux, o Bootloader mais utilizado é o **GRUB**.

Você aprenderá mais sobre ele em capítulos futuros.

---

## 4. Kernel Linux

Somente agora o Linux começa a participar do processo.

O Kernel é carregado para a memória e passa a controlar:

* processador;
* memória RAM;
* discos;
* teclado;
* mouse;
* placa de vídeo;
* dispositivos conectados.

A partir desse momento, o sistema operacional começa a assumir o controle do computador.

---

## 5. Sistema operacional

Depois que o Kernel está funcionando, outros programas são iniciados.

Esses programas são responsáveis por preparar o ambiente para o usuário.

Entre eles estão:

* serviços do sistema;
* interface gráfica (quando existir);
* tela de login.

Quando tudo estiver pronto, o computador estará preparado para uso.

---

# Como funciona

Podemos comparar o processo de inicialização com a abertura de um teatro.

Imagine que o público ainda está do lado de fora.

Antes do espetáculo começar, várias pessoas precisam trabalhar.

Primeiro o prédio é aberto.

Depois as luzes são acesas.

Os equipamentos são preparados.

Os artistas ocupam seus lugares.

Somente então o público entra.

O processo de inicialização do computador funciona de maneira semelhante.

Cada etapa prepara o caminho para a próxima.

---

# Exemplo prático

Imagine que você ligou seu notebook.

Durante poucos segundos acontece toda esta sequência:

```text
Energia
   │
   ▼
BIOS/UEFI
   │
   ▼
GRUB
   │
   ▼
Kernel Linux
   │
   ▼
Serviços
   │
   ▼
Tela de Login
```

Tudo isso normalmente acontece em poucos segundos.

---

# Colocando em prática

Vamos identificar se o seu computador utiliza BIOS ou UEFI.

No Terminal, execute:

```bash
ls /sys/firmware
```

Se aparecer uma pasta chamada:

```text
efi
```

significa que seu computador utiliza **UEFI**.

Caso contrário, provavelmente utiliza BIOS.

> **Observação:** Em máquinas virtuais ou alguns ambientes específicos, esse resultado pode variar.

---

# Erros comuns

* Pensar que o Linux começa a funcionar imediatamente após pressionar o botão de energia.
* Acreditar que BIOS e Linux são a mesma coisa.
* Confundir o Bootloader com o Kernel.

---

# Dicas para aproveitar melhor este capítulo

* Não tente decorar toda a sequência na primeira leitura.
* O importante é compreender a ordem em que cada etapa acontece.
* Nos próximos capítulos cada componente será estudado com mais detalhes.

---

# Você sabia?

Um computador pode possuir vários sistemas operacionais instalados.

Nesse caso, o Bootloader permite escolher qual sistema será iniciado.

É por isso que muitos computadores exibem um menu antes da inicialização.

---

# Referências

* Documentação oficial do GRUB
* Documentação da UEFI Forum
* Kernel.org

---

# Conclusão

Neste capítulo você conheceu a sequência básica utilizada para iniciar um computador.

Agora você sabe que o Linux não é o primeiro software executado quando o computador é ligado.

Antes dele entram em ação o firmware e o Bootloader.

Somente depois o Kernel Linux assume o controle do hardware.

---

# Prepare-se para o próximo passo

Agora que você entende como o Linux chega até a memória do computador, chegou o momento de conhecer o seu principal componente.

No próximo capítulo responderemos à pergunta:

> **O que é o Kernel Linux e por que ele é considerado o coração do sistema operacional?**
