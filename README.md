# Previsão de Preço de Imóveis com Regressão Linear

Finalizando o projeto de precificação de casas da Alura
.

## Modelo Utilizado

O modelo final (modelo_3) utiliza as seguintes variáveis:

- area_primeiro_andar
- existe_segundo_andar
- quantidade_banheiros
- qualidade_da_cozinha_Excelente

Coeficientes do modelo:

- Intercepto: -129979.67
- Área do primeiro andar: +6119.65 por unidade
- Segundo andar: +221306.96
- Banheiros: +149036.29 por unidade
- Cozinha excelente: +444391.23

## Predição de um Novo Imóvel

Exemplo de imóvel:

- Área: 120
- Possui segundo andar: Sim
- Banheiros: 2
- Cozinha excelente: Não

Resultado:

- Modelo simples: R$ 968146.29  
- Modelo completo: R$ 1123758.24  

O modelo mais completo gera previsões mais realistas por considerar mais variáveis.

## Predição em Lote

Foi realizada a previsão para múltiplos imóveis a partir de um arquivo CSV.

Exemplo de resultados:

- Casa 1: 1.751.739  
- Casa 2: 1.863.058  
- Casa 3: 1.568.149  
- Casa 4: 2.206.758  

Isso demonstra como o modelo pode ser utilizado em escala.

## Análise de Multicolinearidade (VIF)

Foi utilizado o Variance Inflation Factor (VIF) para identificar multicolinearidade.

Modelo inicial apresentou problema:

- existe_segundo_andar: VIF alto  
- area_segundo_andar: VIF alto  

Isso indica que as variáveis estavam representando a mesma informação.

Após remoção de variáveis redundantes, os valores de VIF ficaram abaixo de 5, indicando ausência de multicolinearidade relevante.

## Avaliação do Modelo

Foi feita a comparação entre valores reais e previstos.

O modelo apresentou boa capacidade preditiva na maior parte dos casos.

## Análise de Resíduos

Resíduo é definido como:

resíduo = valor real − valor previsto

### Interpretação

- Resíduo positivo: modelo subestimou o preço  
- Resíduo negativo: modelo superestimou o preço  

### Comportamento esperado

- Distribuição simétrica  
- Centrada em zero  
- Formato aproximadamente normal  

### Resultados observados

- A maioria dos resíduos está próxima de zero  
- Existe concentração central adequada  
- Presença de cauda à direita  

Isso indica que o modelo, em alguns casos, subestima fortemente imóveis mais caros.

## Heterocedasticidade

Foi observado que os erros aumentam conforme o valor do imóvel cresce.

Isso caracteriza heterocedasticidade.

Interpretação:

- O modelo tem maior dificuldade em prever imóveis de alto valor  
- Possivelmente faltam variáveis relevantes para capturar melhor esse comportamento  

## Conclusão

O modelo de regressão linear apresentou bom desempenho geral.

Pontos fortes:

- Boa capacidade de explicação dos dados  
- Coeficientes interpretáveis  
- Aplicável para previsão em lote  

Limitações:

- Erros maiores em imóveis de alto valor  
- Presença de heterocedasticidade  
- Possível ausência de variáveis relevantes  

## Possíveis melhorias

- Incluir novas variáveis (localização, padrão do imóvel, etc.)  
- Testar transformações (log do preço)  
- Utilizar modelos mais robustos  
- Tratar outliers  

Este projeto demonstra a aplicação prática de regressão linear para previsão de preços e análise de qualidade do modelo.
