# Calculadora de IMC

Este projeto é uma aplicação simples em Python com interface gráfica para calcular o Índice de Massa Corporal (IMC), utilizando a biblioteca Tkinter.

## Requisitos

- Python 3.6 ou superior
- Tkinter (incluído na maioria das distribuições Python)

## Como executar

1. Salve o código em um arquivo `.py`.
2. No terminal, execute:
   ```bash
   python calculadora_imc.py
   ```

## Interface Gráfica

- **Nome:** Campo para inserir o nome.
- **Idade:** Campo para inserir a idade.
- **Altura:** Altura em metros (ex: 1.75).
- **Peso:** Peso em kg (ex: 70).
- **Botão Calcular IMC:** Calcula e exibe o IMC e classificação.

## Cálculo do IMC

Fórmula:
\[
IMC = \frac{peso}{altura^2}
\]

### Classificação:
- **Abaixo de 18.5:** Abaixo do peso
- **18.5 - 24.9:** Peso normal
- **25.0 - 29.9:** Sobrepeso
- **30.0 - 34.9:** Obesidade Grau 1
- **35.0 - 39.9:** Obesidade Grau 2
- **40.0 ou mais:** Obesidade Grau 3

## Exemplo de Uso

1. Execute o programa.
2. Preencha os campos com suas informações.
3. Clique no botão "Calcular IMC".
4. Veja o resultado na tela com o cálculo e classificação.

## Observações

- Insira altura em metros (ex: 1.75) e peso em kg (ex: 70).
- O programa valida entradas incorretas e exibe mensagens de erro.

## Licença

Projeto de uso livre, modifique conforme necessário.
