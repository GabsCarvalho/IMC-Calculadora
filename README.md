import tkinter as tk  # Biblioteca padrão para criar interfaces gráficas

# Função para calcular o IMC
def calcular_imc():
    try:
        # Obter valores dos campos
        nome = entry_nome.get()  
        idade = int(entry_idade.get())  
        altura = float(entry_altura.get())
        peso = float(entry_peso.get())

        # Verificar se altura e peso são válidos
        if altura <= 0 or peso <= 0:
            resultado_texto = "Erro: Altura ou peso inválidos!"
        else:
            # Cálculo do IMC
            imc = peso / (altura ** 2)
            
            # Determinar a classificação do IMC
            if imc < 18.5:
                classificacao = "ABAIXO DO PESO"
            elif 18.5 <= imc < 25:
                classificacao = "NORMAL"
            elif 25 <= imc < 30:
                classificacao = "SOBREPESO"
            elif 30 <= imc < 35:
                classificacao = "OBESIDADE 1"
            elif 35 <= imc < 40:
                classificacao = "OBESIDADE 2"
            else:
                classificacao = "OBESIDADE 3"

            # Montar a mensagem de resultado
            resultado_texto = (
                f"Olá, {nome}!\n"
                f"Idade: {idade} anos\n"
                f"IMC: {imc:.2f}\n"
                f"Classificação: {classificacao}"
            )

        # Atualizar o texto do resultado na interface
        label_resultado.config(text=resultado_texto)

    except ValueError:
        # Caso o usuário digite algo inválido (como letras em vez de números)
        label_resultado.config(text="Erro: Insira valores válidos!")

# Criar a janela principal
janela = tk.Tk()
janela.title("Calculadora de IMC")
janela.geometry("400x400")  # Tamanho da janela

# Título da interface
label_titulo = tk.Label(janela, text="Calculadora de IMC", font=("Arial", 16, "bold"))
label_titulo.pack(pady=10)  # Adicionar espaçamento vertical

# Campo para o nome
label_nome = tk.Label(janela, text="Nome:")
label_nome.pack()
entry_nome = tk.Entry(janela)  # Campo para o usuário digitar
entry_nome.pack(pady=5)

# Campo para a idade
label_idade = tk.Label(janela, text="Idade:")
label_idade.pack()
entry_idade = tk.Entry(janela)
entry_idade.pack(pady=5)

# Campo para a altura
label_altura = tk.Label(janela, text="Altura (em metros, ex: 1.75):")
label_altura.pack()
entry_altura = tk.Entry(janela)
entry_altura.pack(pady=5)

# Campo para o peso
label_peso = tk.Label(janela, text="Peso (em kg, ex: 70):")
label_peso.pack()
entry_peso = tk.Entry(janela)
entry_peso.pack(pady=5)

# Botão para calcular o IMC
botao_calcular = tk.Button(janela, text="Calcular IMC", command=calcular_imc)
botao_calcular.pack(pady=10)

# Label para exibir o resultado
label_resultado = tk.Label(janela, text="", font=("Arial", 12), justify="left")
label_resultado.pack(pady=10)

# Iniciar o loop principal da interface
janela.mainloop()
