# Sofia Mobile 💜

<p align="justify"> Sofia é um Software Orientado por Inteligência Artificial para Auxílio ao Pré-diagnóstico de Crianças de 0 a 4 Anos com Manifestações Comportamentais do Transtorno do Espectro Autista (TEA). O aplicativo mobile CAD (computer aided design) é destinado ao auxílio de profissionais da saúde na triagem e identificação de sinais do TEA. <strong> 💜 Nosso Objetivo 💜 </strong> é promover a acessibilidade ao diagnóstico precoce de TEA! 💜 </p>

<p align="center">
  <img src="https://github.com/aasjunior/com.sofia.mobile/assets/85968113/ce5ba98e-c63a-4fb7-a311-ced454084bc7" width="700" alt="ilustracao">
</p>

## REDE NEURAL MLP PARA PREDIÇÃO DE AUTISMO 💜

Este projeto implementa uma Rede Neural Multicamadas (MLP) para auxiliar no pré-diagnóstico de crianças de 0 a 4 anos com manifestações comportamentais do Transtorno do Espectro Autista (TEA).

### Dependências 💜
O projeto usa as seguintes bibliotecas:

- numpy
- keras
- sklearn
- pandas
- joblib

### Como funciona 💜
O projeto consiste em várias partes:

1. **Criação do modelo**: A função `create_model` cria um modelo de rede neural com duas camadas ocultas de 64 neurônios cada, e uma camada de saída com um neurônio. A função recebe como parâmetro a forma da entrada dos dados.

2. **Validação cruzada**: A função `cross_validate_model` realiza a validação cruzada do modelo, dividindo os dados em conjuntos de treinamento e teste. A função retorna as acurácias obtidas em cada divisão.

3. **Pré-processamento de novos dados**: A função `preprocess_new_data` recebe novos dados, realiza a codificação de rótulos para variáveis categóricas, aplica o `OneHotEncoder` para variáveis categóricas e normaliza a coluna ‘Age_Mons’. A função retorna os dados pré-processados.

4. **Previsão a partir de um arquivo CSV**: A função `predict_from_csv` recebe o caminho de um arquivo CSV, carrega os dados, pré-processa os dados e faz previsões usando o modelo treinado.

5. **Treinamento do modelo final**: O script principal carrega e pré-processa os dados, realiza a validação cruzada, treina o modelo final em todos os dados e salva o modelo treinado.

6. **API Flask**: O projeto inclui uma API Flask que recebe respostas via POST, salva as respostas em um arquivo CSV e retorna previsões via GET. O resultado da predição é retornado com valor `'1'` para casos positivos de TEA ou valor `'0'` para casos negativos, indicando ausência de sinais de TEA.

### Base de treinamento 💜

**Base de dados**: [Autism screening data for toddlers](https://www.kaggle.com/datasets/fabdelja/autism-screening-for-toddlers?resource=download) <br>
**Tarefa**: Classificação <br>
**Número de Instâncias**: 1054 <br>
**Autor**: Fadi Fayez Thabtah <br>

A base de dados utilizada no projeto teve seu conjunto de dados coletados com base no **Q-Chat-10**, um questionário utilizado para avaliar traços de Transtorno do Espectro Autista (TEA) em crianças pequenas. Aqui estão os principais detalhes:

- O Q-Chat-10 é composto por 10 perguntas.
- As respostas possíveis para cada pergunta são: “Sempre”, “Normalmente”, “Às vezes”, “Raramente” e “Nunca”.
- Os valores das respostas são mapeados para “1” ou “0” no conjunto de dados.
- Para as perguntas de 1 a 9 (A1-A9), se a resposta foi “Às vezes”, “Raramente” ou “Nunca”, é atribuído o valor “1” à pergunta.
- Para a pergunta 10 (A10), se a resposta foi “Sempre”, “Normalmente” ou “Às vezes”, é atribuído o valor “1”.
- Se a soma dos pontos para todas as dez perguntas for maior que 3, há um potencial de traços de TEA. Caso contrário, não há traços de TEA observados.

## Iniciando o projeto 💜

###### Requisitos de Software

- Python
- VSCode

### Instalação

1. Clone o repositório para o seu computador:

```
git clone https://github.com/mandis-ncs/api-flask.git
```

2. Abra o projeto pelo VSCode e execute o comando pelo terminal: 

```
pip install -r requirements.txt
```

3. Navegue até o diretório `app` e execute:

```Python
python main.py
```

4. A API estará rodando em `http://127.0.0.1:5000`
<br>

## Endpoints 💜

A API possui os seguintes endpoints:

| Type   | Path                       |                     Obs.                              |
|--------|----------------------------|:-----------------------------------------------------:|
| POST   | /respostas                 |       Envia as respostas preenchidas do Q-Chat 10.    |
| GET    | /resultado                 | Retorna o resultado do processamento da rede neural.  |

### Respostas
- **URI**: `/respostas`
- **Método**: `POST`
- **Request body**: `application/JSON`
- **Exemplo de Entrada**:

```json
{
  "responses": [
    {
  "Case_No": 1,
  "A1": 0,
  "A2": 0,
  "A3": 0,
  "A4": 0,
  "A5": 0,
  "A6": 0,
  "A7": 1,
  "A8": 1,
  "A9": 0,
  "A10": 1,
  "Age_Mons": 28,
  "Sex": "f",
  "Ethnicity": "black",
  "Jaundice": "yes",
  "Family_mem_with_ASD": "no",
  "Who_completed_the_test": "family member",
  "Class_ASD_Traits": ""
}

  ]
}
```

### Resultado
- **URI**: `/resultado`
- **Método**: `GET`
- **Exemplo de Saída**:

```json
{
    "result": "1"
}
```

## Tecnologias 💜
<p align="center">
   <img src="https://github.com/aasjunior/com.sofia.mobile/assets/85968113/adc364c7-8401-4326-ad56-3807673b85f2" width="600px" alt="Android"/>
   <div align="center">
    <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
    <img src="https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white" alt="Flask"/>
    <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white" alt="TensorFlow"/>
    <img src="https://img.shields.io/badge/Keras-D00000?style=for-the-badge&logo=keras&logoColor=white" alt="Keras"/>     
        
  </div>
</p>

## Nosso Time AJA 💜
You can see more about us in our profile:
* [Amanda](https://github.com/mandis-ncs)
* [Junior](https://github.com/aasjunior)
* [Aline](https://github.com/AlineLauriano)

###### Aviso
Esta é uma iniciativa acadêmica, sendo assim, não possui todas as funcionalidades e características de uma aplicação real.
