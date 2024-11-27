O objetivo geral deste trabalho é criar uma ferramenta que acesse os dados do Censo
Escolar e elabore relatórios customizados às instituições de ensino que precisem saber
informações específicas sobre público-alvo para criar, manter, ampliar, reduzir ou eliminar
turmas de cursos existentes ou para ofertar novos cursos.
Objetivos Específicos são:
● Levantar as necessidades dos dados do censo do IFSP - Campus São Roque.
● Identificar as funcionalidades essenciais do sistema de gestão de dados do censo.
● Escolher o framework web mais adequado para a implementação do sistema.
● Projetar a arquitetura do sistema, incluindo a modelagem do banco de dados.
● Implementar as funcionalidades do sistema de acordo com os requisitos
levantados e a arquitetura definida.

Importação de Bibliotecas:
requests: Para fazer requisições HTTP à API do INEP.
pandas: Para manipulação e análise de dados.
json: Para converter a resposta da API em um formato Python.
Função get_censo_data:
Realiza a requisição à API do INEP com base nos parâmetros fornecidos.
Retorna os dados da API em formato JSON.
Função save_to_csv:
Converte os dados em um DataFrame do Pandas.
Salva os dados em um arquivo CSV.


