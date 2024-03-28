# Web Scraping de Notícias Esportivas

**Contexto:**

Como desenvolvedor em uma empresa de consultoria de software, você foi alocado em uma equipe de marketing analítico em uma marca esportiva. A equipe precisa coletar as principais notícias do mundo do esporte do portal **[https://globoesporte.globo.com/](https://globoesporte.globo.com/)**.

**Objetivo:**

Criar um componente que faça a extração dos dados em formato tabular, com os seguintes campos:

- Manchete
- Descrição
- Link
- Seção
- Hora da extração
- Tempo decorrido da publicação até a hora da extração

**Desafio:**

O grande desafio no web scraping é descobrir o padrão nas tags HTML e atributos CSS usados para alcançar as informações desejadas.

**Informações técnicas:**

O cliente forneceu as seguintes informações para auxiliar na extração:

- **Localizar todas as divs com atributo `class`: `feed-post-body`**
- **Extrair de cada item localizado:**
    - **Manchete:** Primeira posição do conteúdo.
    - **Link:** Tag `a` e atributo `href`.
    - **Descrição:**
        - Terceira posição do conteúdo.
        - Ou dentro de uma div com atributo `class`: `bstn-related`.
    - **Seção:**
        - Div com atributo `class`: `feed-post-metadata`.
        - Localizar o span com atributo `class`: `feed-post-metadata-section`.
    - **Tempo decorrido:**
        - Div com atributo `class`: `feed-post-metadata`.
        - Localizar o span com atributo `class`: `feed-post-datetime`.

**Tratamento de erros:**

- Se o texto de uma tag não for localizado, retornar `None`.
- Campos: `descrição`, `seção` e `time_delta`.

**Implementação:**

Para realizar o web scraping, foram utilizadas as bibliotecas:

- `requests`
    
- `BeautifulSoup`
    
- `pandas`
    
- `datetime`
    
- **`requests`: Para fazer solicitações HTTP.
	
- `BeautifulSoup`: Para analisar documentos HTML.
    
- **`pandas`:** Para manipulação e análise de dados.
    
- **`datetime`:** Marcação do dia e hora da extração.
    
Você pode instalar as dependências usando o seguinte comando pip:
```
pip install requests beautifulsoup4 pandas datetime
```
