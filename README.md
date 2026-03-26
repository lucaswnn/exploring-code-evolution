# Explorando evolução de código

Neste exercício, iremos explorar a evolução de código em sistemas reais.

Iremos utilizar a ferramenta [GitEvo](https://github.com/andrehora/gitevo).
Essa ferramenta analisa a evolução de código em repositórios Git nas linguagens Python, JavaScript, TypeScript e Java, e gera relatórios `HTML` como [este](https://andrehora.github.io/gitevo-examples/python/pandas.html).

Mais exemplos de relatórios podem ser podem ser encontrados em https://github.com/andrehora/gitevo-examples.

# Passo 1: Selecionar repositório a ser analisado

Selecione um repositório relevante na linguagem de sua preferência (Python, JavaScript, TypeScript ou Java).
Você pode encontrar projetos interessantes nos links abaixo:

- Python: https://github.com/topics/python?l=python
- JavaScript: https://github.com/topics/javascript?l=javascript
- TypeScript: https://github.com/topics/typescript?l=typescript
- Java: https://github.com/topics/java?l=java

# Passo 2: Instalar e rodar a ferramenta GitEvo

> [!NOTE]
> Antes de instalar a ferramenta, é recomendado criar e ativar um [ambiente virtual Python](https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/#create-and-use-virtual-environments).

Instale a ferramenta [GitEvo](https://github.com/andrehora/gitevo) com o comando:

```
$ pip install gitevo
```

Execute a ferramenta no repositório selecionado utilizando o comando abaixo (ajuste conforme a linguagem do repositório).
Substitua `<git_url>` pela URL do repositório que será analisado:

```shell
# Python
$ gitevo -r python <git_url>

# JavaScript
$ gitevo -r javascript <git_url>

# TypeScript
$ gitevo -r typescript <git_url>

# Java
$ gitevo -r java <git_url>
```

Por exemplo, para analisar o projeto Flask escrito em Python:

```
$ gitevo -r python https://github.com/pallets/flask
```

> [!NOTE]
> Essa etapa pode demorar alguns minutos pois o projeto será clonado e analisado localmente.

# Passo 3: Explorar o relatório de evolução de código

Após executar a ferramenta [GitEvo](https://github.com/andrehora/gitevo), é gerado um relatório `HTML` contendo diversos gráficos sobre a evolução do código.

Abra o relatório `HTML` e observe com atenção os gráficos.

# Passo 4: Explicar um gráfico de evolução de código

Selecione um dos gráficos de evolução e explique-o com suas palavras.
Por exemplo, você pode:

- Detalhar a evolução ao longo do tempo
- Detalhar se as curvas estão de acordo com boas práticas
- Explicar grandes alterações nas curvas
- Explorar a documentação do repositório em busca de explicações para grandes alterações
- etc.

Seja criativo!

# Instruções para o exercício

1. Crie um `fork` deste repositório (mais informações sobre forks [aqui](https://docs.github.com/pt/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)).
2. Adicione o relatório `HTML` no seu fork.
3. No Moodle, submeta apenas a URL do seu `fork`.

Responda às questões abaixo diretamente neste arquivo `README.md` do seu fork:

1. Repositório selecionado:
https://github.com/scikit-learn/scikit-learn

2. Gráfico selecionado:
<img width="664" height="318" alt="function_parameters" src="https://github.com/user-attachments/assets/18a2a213-7ada-48a9-b1c7-8a37d828eeba" />

3. Explicação:
O gráfico "Function parameters" exibe cinco diferentes séries temporais, desde o ano 2010 até o ano de 2026:
- número de parâmetros em geral (identifiers);
- número de parâmetros com valor padrão (default_parameter);
- número de parâmetros com separador de identificadores (keyword_separator);
- número de parâmetros com tipo esperado (typed_parameter);
- número de parâmetros com valor padrão e com tipo esperado (typed_default_parameter).
Percebe-se que o número de parâmetros em geral cresce de forma proporcionalmente linear conforme o tempo, o que é de se esperar de uma biblioteca que evolui e se mantém. Além disso, observa-se um crescimento no número de parâmetros com valor padrão proporcional ao número de parâmetros em geral até o ano de 2017, sendo seu crescimento após este ano um pouco mais lento.
De forma curiosa, observa-se o baixo uso dos parâmetros com identificadores obrigatórios e dos parâmetros com tipo esperado (seja com valor padrão ou não). Até o ano de 2020, o uso destes tipos de parâmetro não foi utilizado, apesar de seu baixo uso em relação aos demais tipos atualmente.
Este comportamento do baixo uso de identificadores de tipos é esperado para a linguagem python, por seguir um estilo de tipagem "duck typing". Mesmo com o uso de identificadores de tipos, dependendo do interpretador utilizado, não há a verificação de tipos em tempo de execução, portanto, na maioria dos casos, o identificação dos tipos serve como um auxiliador e um contrato "fraco" para o programador que utiliza funções com estes identificadores.
Apesar disso, é uma boa prática a utilização de tipos explícitos: para o desenvolvedor da própria biblioteca, é importante para evitar imprevisibilidade. Para o desenvolvedor que utiliza a biblioteca, garante que ele esteja ciente das estruturas de dados a serem utilizadas e que utilizar tipos diferentes pode ocasionar comportamento indefinido.
Com o crescimento da biblioteca, provavelmente os desenvolvedores sentiram a necessidade de introduzir o uso de identificadores de tipos, tendo um salto expressivo no ano de 2026 em relação aos anos anteriores. Uma hipótese deste salto pode ser a utilização de tipos internos da biblioteca para auxiliar a evolução da própria biblioteca, pois não faria sentido criar novas interfaces (funções e métodos) com identificadores de tipo para o desenvolvedor que utiliza a biblioteca, visto que já existem diversas interfaces sem tipagem explícita.
Com base no gráfico "Functions and classes", observa-se que foram contabilizadas 11.202 funções no ano de 2026. Com base nisso e no gráfico estudado, cujos dados revelam que a contagem de parâmetros em geral é de 16.585 no ano de 2026, estimam-se em média 1,48 parâmetros por função. De forma geral, as funções aparentam seguir uma boa prática para evitar funções com muitos parâmetros.
