# 💻 ULA Digital de 8-bits (ALU)

Este repositório contém o projeto de uma **Unidade Lógica e Aritmética (ALU) de 8 bits**, desenvolvida como atividade ponderada para simulação de circuitos digitais. O projeto foi implementado utilizando o software de simulação [Digital (hneemann)](https://github.com/hneemann/Digital).

## 🎥 Vídeo de Apresentação

[![Vídeo de Demonstração](https://img.youtube.com/vi/LbK_SP19gcc/0.jpg)](https://youtu.be/LbK_SP19gcc)

*Clique na imagem acima para assistir à explicação e demonstração do funcionamento da ULA.*

**Link alternativo (Google Drive):** [Clique aqui para acessar o vídeo reserva](https://drive.google.com/file/d/1SOdocvwvXYWiwySvpyd6bPQsugavxBam/view?usp=sharing)

---

## ⚙️ Arquitetura e Componentes

A ULA foi projetada para processar dados de 8 bits e é composta pelos seguintes componentes principais:

- **Circuitos de Operações:** Módulos lógicos isolados responsáveis por executar cada cálculo aritmético e lógico.
- **Seletor de Operações (Multiplexador):** Circuito que recebe um código de instrução (Opcode) e direciona o resultado da operação correta para a saída.
- **Registradores Internos:**
  - **AC (Acumulador):** Registrador principal de 8 bits, atua como um dos operandos e armazena os resultados primários.
  - **MQ (Multiplier/Quotient):** Registrador auxiliar de 8 bits utilizado exclusivamente para armazenar os bits mais significativos em multiplicações e o quociente em divisões.

---

## 🧮 Tabela de Operações

A Unidade é capaz de realizar as seguintes operações matemáticas e lógicas, a partir do valor armazenado no Acumulador (AC) e uma entrada N de 8 bits:

| Seletor (Opcode) | Operação | Descrição Técnica | Saída / Destino |
| :---: | :--- | :--- | :--- |
| `000` | **Soma** | AC + N | AC (8 bits) |
| `001` | **Subtração** | AC - N | AC (8 bits) |
| `010` | **Multiplicação** | AC × N | LSB no AC e MSB no MQ |
| `011` | **Divisão** | AC / N | Resto no AC e Quociente no MQ |
| `100` | **Shift Lógico** | Deslocamento de bits | AC (8 bits) |
| `101` | **NAND** | AC NAND N (Bit a Bit) | AC (8 bits) |
| `110` | **XOR** | AC XOR N (Bit a Bit) | AC (8 bits) |

*(Nota: Os seletores acima são ilustrativos. Devem ser atualizados conforme a pinagem final do projeto)*

---

## 🚀 Como Executar o Projeto

1. **Pré-requisitos:** 
   - Ter o Java instalado na máquina.
   - Baixar o simulador [Digital](https://github.com/hneemann/Digital/releases).
2. **Clonar o Repositório:**
   ```bash
   git clone https://github.com/SEU_USUARIO/ULA-Digital.git
   ```
3. **Execução:**
   - Abra o simulador `Digital`.
   - Vá em `File > Open` e selecione o arquivo principal `.dig` que se encontra na pasta deste repositório.
   - Execute a simulação (botão "Play") e altere as entradas (N) e os seletores no painel do circuito.

---

## 🛠️ Processo de Desenvolvimento

*(Nesta seção, você pode adicionar um pequeno texto explicando as maiores dificuldades do projeto: Como implementou o multiplicador, como fez o seletor ligar AC e MQ, etc.)*

* **Soma/Subtração:** Utilizou-se somadores completos (Full-Adders). A subtração funciona através de complemento de 2.
* **Multiplicação e Divisão:** Foram conectados aos barramentos de dois registradores conforme a exigência estrutural (AC recebendo o LSB/Resto e MQ recebendo o MSB/Quociente).

---

## 📝 Licença e Autoria
Desenvolvido por **[Seu Nome]** para fins acadêmicos.
