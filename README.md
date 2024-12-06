# PlanilhaDashboard-DIO
Financeira com Planilhas Inteligentes e IA
-----------------------------------------------------------------------
import pandas as pd

# Criando dados para o dashboard financeiro
dados_mensais = {
    "Mês": ["Outubro", "Novembro", "Dezembro"],
    "Receita (R$)": [2400.65, 2339.00, None],
    "Despesas (R$)": [4081.48, None, None],
    "Saldo (R$)": [1697.79, None, None],
    "Investimento (R$)": [300, None, None]
}

gastos_categoria = {
    "Categoria": ["Alimentação", "Transporte", "Lazer", "Outros"],
    "Gastos (Outubro)": [800, 500, 300, 400]
}

# Criando DataFrames
df_mensal = pd.DataFrame(dados_mensais)
df_categorias = pd.DataFrame(gastos_categoria)

# Salvando em uma planilha Excel
caminho_arquivo = "/mnt/data/Dashboard_Financeiro.xlsx"
with pd.ExcelWriter(caminho_arquivo) as writer:
    df_mensal.to_excel(writer, index=False, sheet_name="Resumo Mensal")
    df_categorias.to_excel(writer, index=False, sheet_name="Gastos por Categoria")

caminho_arquivo
