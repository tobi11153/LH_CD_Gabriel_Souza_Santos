# Previsão de Preços de Imóveis

Este projeto tem como objetivo prever o preço de imóveis a partir de variáveis como localização, tipo de acomodação, número de noites mínimas, entre outras.

## 📌 Instalação
Clone o repositório e instale as dependências:
```bash
git clone https://github.com/seu-usuario/meu-projeto.git
cd meu-projeto
pip install -r requirements.txt
```

📊 Estrutura

notebooks/: Contém notebooks com análise exploratória e modelagem
relatorios/: Contém o relatório em PDF da análise estatística e EDA
modelo/: Contém o modelo treinado salvo em .pkl


🔮 Como Fazer Previsões com o Modelo .pkl

Após instalar as dependências, você pode carregar o modelo salvo e fazer previsões com novos dados.

Exemplo de Uso
```python

# Importando as bibliotecas necessárias
import joblib
import pandas as pd

# Carregando o modelo treinado
modelo_carregado = joblib.load('modelo/modelo_treinado.pkl')

# Criando uma nova entrada com os dados de um apartamento
nova_entrada = pd.DataFrame([{
   'id': 2595,
    'nome': 'Skylit Midtown Castle',
    'host_id': 2845,
    'host_name': 'Jennifer',
    'bairro_group': 'Manhattan',
    'bairro': 'Midtown',
    'latitude': 40.75362,
    'longitude': -73.98377,
    'room_type': 'Entire home/apt',
    'minimo_noites': 1,
    'numero_de_reviews': 45,
    'ultima_review': '2019-05-21',
    'reviews_por_mes': 0.38,
    'calculado_host_listings_count': 2,
    'disponibilidade_365': 355
}])

# Fazendo a previsão
previsao = modelo_carregado.predict(nova_entrada)
print(f"Preço previsto: ${previsao[0]:.2f}")

```

📌 Exemplo de Saída:
Preço previsto: $246.10
