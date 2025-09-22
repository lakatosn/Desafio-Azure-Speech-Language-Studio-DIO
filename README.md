from azure.ai.textanalytics import TextAnalyticsClient
from azure.core.credentials import AzureKeyCredential

key = "SUA_CHAVE_AQUI"
endpoint = "SEU_ENDPOINT_AQUI"

client = TextAnalyticsClient(endpoint=endpoint, credential=AzureKeyCredential(key))
documents = ["Estou muito feliz com os resultados do laboratório!", "O teste não funcionou como esperado."]

response = client.analyze_sentiment(documents)
for doc in response:
    print(f"Sentimento: {doc.sentiment}, Pontuação: {doc.confidence_scores}")
