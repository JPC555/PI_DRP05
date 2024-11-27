# O objetivo geral deste trabalho é criar uma ferramenta que acesse os dados do Censo
Escolar e elabore relatórios customizados às instituições de ensino que precisem saber
informações específicas sobre público-alvo para criar, manter, ampliar, reduzir ou eliminar
turmas de cursos existentes ou para ofertar novos cursos.
Objetivos Específicos são:
● Levantar as necessidades dos dados do censo do IFSP - Campus São Roque.
● Identificar as funcionalidades essenciais do sistema de gestão de dados do censo.
● Escolher o framework web mais adequado para a implementação do sistema.
● Projetar a arquitetura do sistema, incluindo a modelagem do banco de dados.
● Implementar as funcionalidades do sistema de acordo com os requisitos
levantados e a arquitetura definida 

#




import requests
import pandas as pd
import json

# Substitua pela sua chave de acesso à API do INEP
api_key = "sua_chave_de_acesso"

# Função para realizar a requisição à API do INEP
def get_censo_data(ano, nivel_ensino, uf, municipio):
    url = f"https://api.inep.gov.br/educacao-basica/censo-escolar/{ano}/{nivel_ensino}/{uf}/{municipio}"
    headers = {"Authorization": f"Token {api_key}"}
    response = requests.get(url, headers=headers)
    data = json.loads(response.text)
    return data

# Função para salvar os dados em um arquivo CSV
def save_to_csv(data, filename):
    df = pd.DataFrame(data)
    df.to_csv(filename, index=False)

# Exemplo de uso
ano = 2023
nivel_ensino = "ensino_medio"
uf = "SP"
municipio = "SaoRoque"

data = get_censo_data(ano, nivel_ensino, uf, municipio)
save_to_csv(data, "censo_sao_roque_2023.csv")




