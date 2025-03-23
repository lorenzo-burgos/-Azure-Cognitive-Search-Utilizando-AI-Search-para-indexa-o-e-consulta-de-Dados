# -Azure-Cognitive-Search-Utilizando-AI-Search-para-indexa-o-e-consulta-de-Dados


## Visão Geral
Azure Cognitive Search é um serviço de busca baseado em nuvem da Microsoft que permite a indexação e pesquisa de dados com o suporte de inteligência artificial (AI Search). Ele pode ser utilizado para melhorar a descoberta de informações em aplicações empresariais, sites e sistemas.

## Configuração Passo a Passo

### 1. Criando um Serviço no Azure Cognitive Search
1. Acesse o [portal do Azure](https://portal.azure.com/)
2. No menu de pesquisa, procure por **Azure Cognitive Search**
3. Clique em **Criar** e preencha os seguintes campos:
   - Nome do Serviço
   - Grupo de Recursos
   - Localização
   - Camada de Preço (Escolha de acordo com a necessidade)
4. Clique em **Revisar + Criar** e depois **Criar**.

### 2. Criando um Índice de Pesquisa
1. Acesse seu serviço recém-criado
2. No menu lateral, selecione **Índices** e clique em **Adicionar Índice**
3. Defina o nome do índice e configure os campos:
   - **Chave primária**: Identificador único para os documentos
   - **Campos**: Defina os atributos pesquisáveis, filtráveis e classificáveis
   - **Habilite AI Enrichment**, se necessário (por exemplo, reconhecimento de imagem, extração de texto, etc.)
4. Salve o índice

### 3. Criando uma Fonte de Dados
1. No menu lateral, selecione **Fontes de Dados**
2. Clique em **Adicionar fonte de dados**
3. Escolha o tipo de fonte (Azure Blob Storage, SQL Database, Cosmos DB, etc.)
4. Configure a conexão e teste a conectividade

### 4. Criando um Indexador
1. No menu lateral, selecione **Indexadores**
2. Clique em **Adicionar Indexador**
3. Escolha o índice e a fonte de dados criados anteriormente
4. Configure a frequência da indexação (manual, agendada, contínua)
5. Clique em **Criar** para ativar a indexação

### 5. Executando Consultas
Azure Cognitive Search oferece suporte a consultas RESTful ou integração com SDKs (Python, .NET, Java, etc.).

#### Exemplo de Consulta REST API:
```bash
GET https://{NOME_DO_SERVICO}.search.windows.net/indexes/{NOME_DO_INDICE}/docs?api-version=2023-07-01&search="termo de pesquisa"
```

Adicione a `api-key` no cabeçalho da requisição para autenticação.

#### Exemplo de Consulta em Python:
```python
import requests

url = "https://{NOME_DO_SERVICO}.search.windows.net/indexes/{NOME_DO_INDICE}/docs?api-version=2023-07-01&search=teste"
headers = {"api-key": "SUA_API_KEY", "Content-Type": "application/json"}
response = requests.get(url, headers=headers)
print(response.json())
```

## Possibilidades e Aplicações
- **Pesquisa Inteligente**: Aprimora a busca em bases de dados com NLP e análise semântica.
- **Análises Avançadas**: Indexa dados complexos e fornece insights valiosos.
- **Suporte Multimodal**: Pesquisa não apenas texto, mas também imagens e documentos.
- **Chatbots e Assistentes Virtuais**: Melhora a busca de respostas em chatbots com pesquisa semântica.

## Insights e Aprendizados
- **Desempenho**: Indexar documentos regularmente melhora a experiência do usuário.
- **Segurança**: O uso de chaves de API e autenticação do Azure são fundamentais.
- **Customização**: A pesquisa pode ser refinada com sinônimos, boosts de relevância e filtragem avançada.

