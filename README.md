# amazon-data-analysis

<p align="center">
 
[Caso](#caso)  •  [Ferramentas Utilizadas](#ferramentas-utilizadas)  •  [Metodologia](#metodologia)  •  [Testes de Hipóteses](#testes-de-hipóteses)  •  [Análise de Sentimentos](#análise-de-sentimentos)  •  [Conclusão](#conclusão)  •  [Recomendações](#recomendações)  •  [Limitações e Próximos Passos](#limitações-e-próximos-passos)  •  [Venha nos conhecer!](#venha-nos-conhecer)

</p>

**Time responsável pelo projeto**: [Eslaine Santos](https://www.linkedin.com/in/eslaine-santos/) e [Maiully Mendonça](https://www.linkedin.com/in/maiully-data-science/) 

## Caso

O principal problema que este projeto busca resolver é entender os fatores que influenciam as avaliações dos clientes nos produtos vendidos na Amazon. As empresas precisam compreender como variáveis como descontos, preços, número de avaliações e categorias de produtos afetam a percepção dos consumidores para otimizar suas estratégias de marketing, aprimorar a qualidade dos produtos e melhorar a experiência do cliente. Além disso, identificar padrões de sentimento nas avaliações dos clientes pode ajudar a detectar problemas específicos e oportunidades de melhoria.

**Principais questões que buscamos responder com esse projeto:** 

- Produtos com maior desconto tendem a receber melhores avaliações?
- Produtos mais caros tendem a receber uma melhor avaliação?
- Quanto maior o número de pessoas que avaliaram o produto, melhor será a classificação?
- Quais categorias de produtos possuem melhores avaliações e mais compras? Quais são as categorias mais bem avaliadas?
- Qual o principal conteúdo das avaliações?

## Ferramentas Utilizadas

- [Google Colab (Python)](https://colab.research.google.com/drive/1S6991KmizrNeO5Z0UluEJ8d58YQ_kvsA?usp=sharing) - Tratamento, limpeza, análise e visualização dos dados.
- [Power Bi](https://app.powerbi.com/view?r=eyJrIjoiMTRjYTA1ZGMtNDMxMS00MmU0LWEzYjEtYzhmODYzYmRlYWMyIiwidCI6ImUwZjY3ODE5LTJmNmYtNDg0Mi1hZjVlLTA5ZjI4Y2U4N2U0NyJ9&pageName=6310dbc2a0723055404b) - Visualização dos dados / Dashboard.

[![image](https://github.com/user-attachments/assets/9404416e-3921-4440-aa1a-4cdfce2bc390)](https://app.powerbi.com/view?r=eyJrIjoiMTRjYTA1ZGMtNDMxMS00MmU0LWEzYjEtYzhmODYzYmRlYWMyIiwidCI6ImUwZjY3ODE5LTJmNmYtNDg0Mi1hZjVlLTA5ZjI4Y2U4N2U0NyJ9&pageName=6310dbc2a0723055404b)


## **Metodologia**

- **Tratamento e Limpeza dos Dados**
- **Análise Estatística**: Aplicação de testes de hipóteses, análise de correlação e regressão linear para identificar relações entre variáveis.
- **Natural Language Processing para Análise de Sentimentos das Avaliações**: Uso de técnicas de Processamento de Linguagem Natural (NLP) para analisar sentimentos expressos nas avaliações dos clientes, assim como a identificação de palavras (unigramas), assim como pares (bigramas) e trios (trigramas) de palavras frequentes em avaliações para entender melhor o contexto e as principais reclamações dos clientes.

## Testes de Hipóteses

Os dados que analisamos incluem um total de 1.185 mil produtos. Durante a análise, descobrimos que a categoria "Casa & Cozinha" é a mais avaliada pelos consumidores. Além disso, notamos que, em média, os produtos que estão em promoção têm preços quase pela metade do valor original.

![image](https://github.com/user-attachments/assets/85230f17-4d0b-4b08-9e62-3c0bef14805f)

### Produtos com maior desconto tendem a receber melhores avaliações?

A análise mostrou que não existe uma relação direta entre o percentual de desconto e a avaliação dos produtos. Isso foi confirmado pela linha de tendência na visualização dos dados, que não indicou uma correlação clara. No entanto, o teste de hipóteses revelou uma diferença significativa nas médias das avaliações entre produtos com altos e baixos descontos, com um p-valor inferior a 0,05. Surpreendentemente, os produtos com descontos menores tiveram, em média, avaliações um pouco melhores do que aqueles com descontos maiores, o que contradiz nossa expectativa inicial.

### Produtos mais caros tendem a receber uma melhor avaliação?

A análise de regressão linear indicou uma relação positiva, mas fraca, entre o preço dos produtos com desconto e suas avaliações, com um coeficiente de 0,12. Esse número sugere que o preço tem pouca influência nas avaliações. Além disso, o teste de Mann-Whitney confirmou que não há uma diferença significativa entre os preços dos produtos com avaliações altas e baixas. Esses resultados contrariam a nossa hipótese inicial de que produtos mais caros receberiam melhores avaliações.

### Quanto maior o número de pessoas que avaliaram o produto, melhor será a classificação?

A análise que realizamos entre o número de pessoas que avaliaram um produto e a sua classificação média mostrou que não há uma relação significativa entre esses dois fatores. O coeficiente de correlação de Pearson que encontramos foi de 0,0521, o que indica uma correlação extremamente fraca. Além disso, o p-valor de 0,0558 sugere que essa correlação não é estatisticamente significativa, já que está acima do nível comum de significância de 0,05. Esses resultados sugerem que a quantidade de pessoas que avaliam um produto não tem um impacto direto na média das suas classificações. Isso contraria a nossa hipótese inicial de que um maior número de avaliações estaria associado a melhores classificações, já que os dados não suportam essa suposição.

### Quais categorias de produtos possuem melhores avaliações e mais compras? Quais são as categorias mais bem avaliadas?

Realizamos uma segmentação das categorias de produtos e testes de hipóteses para identificar se havia diferenças significativas entre as medianas das avaliações em diferentes categorias. A categoria "Office Products" se destacou por ter a maior mediana de avaliações, mostrando que, em média, seus produtos recebem boas notas. No entanto, as categorias "Computers & Accessories," "Electronics" e "Home & Kitchen" tiveram o maior número de avaliações, com "Computers & Accessories" apresentando uma mediana de avaliações de 4,20, a mais alta entre elas.

Além disso, quando analisamos a porcentagem de avaliações altas, "Computers & Accessories" se destacou novamente. Isso indica que essa categoria não apenas possui um grande volume de avaliações, mas também uma alta porcentagem de classificações positivas. Esses dados reforçam a ideia de que os produtos em "Computers & Accessories" são bem recebidos pelos consumidores.

## Análise de Sentimentos | Nature Language Processing

## Análise de Sentimentos | Títulos

A análise de sentimentos dos títulos das avaliações revelou que a maioria esmagadora dos comentários foi classificada como positiva. Foram 1.432 entradas positivas, enquanto apenas 21 avaliações foram consideradas negativas e 6 foram neutras. Isso indica que, no geral, os títulos das avaliações refletem um sentimento amplamente positivo. Contudo, para essa análise vamos focar nos títulos que foram classificados como negativos, visando entender quais fatores estão relacionados com avaliações negativas.

![image](https://github.com/user-attachments/assets/f1e9eb20-251d-425c-980e-c77450c108ad)

### Qualidade do Produto

→ Termos que se destacam: "good", "quality", "bad", "poor".

→ Os termos mais comentados nas avaliações mostram que muitos clientes estão preocupados com a qualidade dos produtos. Isso pode significar que alguns itens não estão correspondendo às expectativas das pessoas quando se trata de durabilidade, desempenho ou acabamento. Além disso, vale a pena verificar se há uma diferença considerável na qualidade entre diferentes unidades do mesmo produto. Afinal, inconsistências podem afetar a experiência dos clientes e a reputação da marca. É importante entender essas questões para poder oferecer produtos que realmente satisfaçam os consumidores.

### Preço 

→ Termos que se destacam: "price" e "money".

→ Palavras como "preço" e "dinheiro" aparecem com frequência nas avaliações negativas, sugerindo que o custo é um fator importante para os clientes. Isso pode indicar que as pessoas estão insatisfeitas com o custo-benefício dos produtos, comparando-os com alternativas mais baratas ou de melhor qualidade oferecidas por concorrentes. Essa percepção pode impactar as decisões de compra, por isso é essencial entender o que está levando os consumidores a sentirem que não estão obtendo um bom valor pelo que pagam.

### Funcionalidade 

→ Termos que se destacam: "working", "features", "battery", "damaged", "works".

→ Os termos mais mencionados nas avaliações sugerem que muitos produtos podem apresentar problemas técnicos. Isso inclui baterias que não duram o esperado, recursos que não funcionam corretamente e até produtos que chegam danificados. Essas questões podem frustrar os clientes e impactar negativamente a experiência deles com a marca. É importante abordar esses problemas para melhorar a satisfação do cliente e garantir que os produtos atendam às expectativas.

### Sentimento Negativo

→ Termos que se destacam: "negation" (representando "no", "not", "never"), "fool", "youworst".

→ Os termos mais mencionados nas avaliações refletem um sentimento geral de frustração e insatisfação. Isso sugere que algumas experiências dos clientes foram especialmente ruins, resultando em feedbacks carregados de emoções negativas. Quando os consumidores se sentem decepcionados ou frustrados, eles tendem a expressar suas preocupações de forma mais enfática. Entender essas experiências negativas pode ser crucial para identificar áreas de melhoria e aumentar a satisfação do cliente.

### Análise dos Bigramas Negativos | Títulos

![image](https://github.com/user-attachments/assets/5425b182-f06d-40ea-a0d6-b6c069a1d682)

Os principais bigramas negativos destacam algumas das principais frustrações dos clientes. Por exemplo:

- "Negation working – Não funciona": Os clientes ficaram insatisfeitos porque o produto não funcionou como esperavam ou simplesmente não funciona.

- "Watch Negation" e "Smart one": Os clientes ficaram frustrados por acharem que o produto não é um smartwatch de verdade, apesar das expectativas.

- "One features", "Features make", "Make fool", "Fool youworst": Esses bigramas mostram que os clientes se sentiram enganados quanto às características do produto. Eles acharam que as funcionalidades foram exageradas ou não eram como descritas.

### Análise dos Trigramas Negativos | Títulos

![image](https://github.com/user-attachments/assets/2ba448f6-a982-4e15-8e05-54949e48f619)

Os principais trigramas negativos revelam ainda mais insatisfação dos clientes em relação a produtos, possivelmente smartwatches. Aqui estão algumas observações:

- "watch negation smart" e "negation smart one": Os clientes estavam insatisfeitos com o fato de o produto não ser um smartwatch de verdade ou não ter as funcionalidades inteligentes prometidas.

- "smart one features" e "one features make": Os recursos do produto não se mostraram tão bons quanto os clientes esperavam, o que contribuiu para a insatisfação.

- "features make fool" e "make fool youworst": Os clientes se sentiram enganados pelas características anunciadas do produto, sentiram-se decepcionados ou até enganados.

- "youworst watch connecting" e "watch connecting problem": Esses trigramas destacam problemas específicos de conexão, o produto apresentou dificuldades para se conectar, possivelmente a um celular ou outro dispositivo.

## Análise de Sentimentos | Conteúdo das Avaliações

A análise de sentimentos dos títulos conteúdo das avaliações revelou que a maioria das avaliações foi classificada como positiva, com 1.423 entradas positivas. Em comparação, houve apenas 27 avaliações negativas e 9 neutras. Isso sugere que, em geral, os clientes estão satisfeitos, expressando opiniões favoráveis em seus comentários. Essa tendência positiva pode indicar uma experiência geral positiva dos consumidores com o produto ou serviço. Contudo, mais uma vez, vamos focar na análise das avaliações categorizadas como negativas.

![image](https://github.com/user-attachments/assets/262de161-181a-486b-b2e4-08da1c597320)

### Problemas de Funcionamento

→ Termos que se destacam: negation, product, using, working, cable, battery, money.

→  Os termos que se destacam estão relacionados a discussões sobre problemas de funcionamento do produto e questões financeiras relacionadas ao custo-benefício.

### Qualidade do Produto e Experiência dos Usuários

→ Termos que se destacam: product, quality, got, good, bit, water, days, like.

→ Palavras como "quality", "got", "good" e "like" estão relacionadas com avaliações focadas na qualidade do produto e na experiência dos usuários com os produtos.

### Desempenho

→ Termos que se destacam: unit, working, item, service.

→ As palavras como "unit", "working", "item" e "service" estão relacionadas a discussões sobre o desempenho dos produtos.

### Qualidade do Produto

→ Termos que se destacam: use, poor, quality, charging, cable, handle.

→ Os termos que se destacam indicam discussões sobre o uso do produto e questões de qualidade, especialmente em relação ao carregamento e manuseio.

### Compra, Serviço e Instalação

→ Termos que se destacam: buy, bad, service, come, install, provider, stand, pay.

→ Os termos que se destacam estão relacionados a discussões sobre a compra, a qualidade do serviço, e aspectos relacionados à instalação dos produtos.

### Análise dos Bigramas Negativos | Conteúdo das Avaliações

![image](https://github.com/user-attachments/assets/7e5435ec-98ca-4b9b-bad7-31b0565380e2)

Os bigramas negativos mais frequentes revelam problemas específicos que os clientes têm enfrentado:

"Negative come": Os produtos não foram entregues corretamente ou chegaram com problemas, causando frustração aos clientes.

"Product come": Os produtos foram entregues em condições inadequadas, possivelmente danificados ou não como esperado.

"Quality poor": Insatisfação dos clientes com a qualidade dos produtos, indicando que não atenderam às expectativas.

"Bad service": Destaca problemas com o atendimento ao cliente, os clientes não se sentiram bem atendidos ou que suas questões não foram resolvidas de maneira satisfatória.

"Installation guy": Aponta para questões relacionadas ao serviço de instalação, talvez devido a profissionais não qualificados ou instalações mal feitas.

"Good product" em contextos negativos: Embora o produto em si seja de boa qualidade, há outros problemas associados, como suporte ou logística, que afetaram a experiência do cliente.

### Análise dos Trigramas | Conteúdo das Avaliações

![image](https://github.com/user-attachments/assets/8d1146f9-7741-423e-8bec-a42e25707d43)

Os trigramas negativos reforçam as principais reclamações dos clientes em relação à qualidade dos produtos:

"Câmera display poor" e "Display poor quality": Esses trigramas apontam para problemas significativos com a qualidade do display, a tela ou a câmera não atendeu às expectativas dos usuários.

"Poor quality batery": Destaca insatisfação com a baixa qualidade da bateria, possivelmente em termos de duração ou confiabilidade.

"Good nothing badnice" e "Fool youworst watch": Experiências gerais negativas com os produtos, apesar de alguma expectativa positiva inicial, os clientes sentiram-se enganados ou decepcionados com a qualidade ou funcionalidade dos produtos.

"Badnice phone reasonable" e "Phone reasonable pricegoodnicevalue": Embora o preço do produto seja razoável, a qualidade ou o valor percebido ainda está aquém do esperado.

## Conclusão

### Testes de Hipóteses

Os testes de hipóteses revelaram que não há uma relação significativa entre:

- **Desconto do produto e avaliações**: Produtos com maiores descontos não necessariamente recebem melhores avaliações.
- **Preço do produto e avaliações**: Produtos mais caros não garantem melhores avaliações, e produtos mais baratos não são necessariamente avaliados de forma inferior.
- **Número de avaliações e avaliações**: Um maior número de avaliações não implica em uma melhor avaliação geral do produto.

### Análise de Sentimentos

A análise de sentimentos, realizada através dos textos dos títulos e do conteúdo das avaliações, indicou que a maioria das avaliações foram positivas. No entanto, focamos nos textos classificados como negativos para entender melhor os pontos de insatisfação.

Nos títulos das avaliações negativas, surgiram frequentemente temas como qualidade do produto, preço, funcionalidade e sentimentos negativos. Termos como "bom", "qualidade", "ruim" e "pobre" sugerem insatisfações com durabilidade, desempenho e acabamento dos produtos. Em relação ao preço, palavras como "preço" e "dinheiro" indicam insatisfação com o custo-benefício, levando a comparações desfavoráveis com alternativas de concorrentes. Problemas técnicos são refletidos em termos como "funcionando", "recursos", "bateria", "danificado" e "funciona". Finalmente, termos como "não", "nunca" e "pior" expressam frustração e insatisfação, indicando experiências particularmente negativas.

No conteúdo das avaliações negativas, surgem problemas de funcionamento, qualidade do produto, desempenho, e questões relacionadas à compra, serviço e instalação. Consumidores frequentemente mencionam produtos defeituosos, cabos e baterias problemáticos, e questionam o custo-benefício. Palavras como "qualidade", "recebi", "bom" e "gostar" são comuns quando discutem suas experiências pessoais. Termos como "unidade", "funcionando", "item" e "serviço" refletem preocupações com o desempenho, enquanto palavras como "uso", "pobre", "carregando" e "manuseio" destacam problemas específicos. Em relação à compra, termos como "comprar", "ruim", "serviço", "chegar", "instalar", "provedor" e "pagar" revelam frustrações com o processo de compra e a qualidade do atendimento e instalação.

A análise de bigramas e trigramas revelou importantes insights sobre as principais reclamações dos clientes, que incluem problemas de entrega, condições inadequadas dos produtos e insatisfação com a qualidade, especialmente em relação a telas e baterias. Além disso, muitos clientes expressaram frustração com o atendimento ao cliente, indicando que o suporte não está atendendo suas necessidades de maneira satisfatória. Esses insights destacam áreas críticas que precisam ser abordadas para melhorar a experiência do cliente e aumentar a satisfação com os produtos e serviços oferecidos.

## Recomendações

### Recomendações Gerais

- **Análise de Desempenho de Categorias**
    - **Foco em Categorias de Destaque**: Continuar investindo na categoria "Computers&Accessories", que apresentou a maior mediana e porcentagem de avaliações altas.
    - **Expansão para Outras Categorias**: Avaliar a possibilidade de expandir as estratégias de sucesso de "Computers&Accessories" para outras categorias que apresentam potencial de crescimento.
- **Promoções e Descontos Estratégicos**
    - **Promoções Alinhadas à Qualidade**: Oferecer descontos em produtos que já possuem boa avaliação, incentivando clientes satisfeitos a retornarem.
    - **Campanhas Sazonais**: Planejar campanhas de desconto durante períodos de alta demanda, garantindo que a logística e o atendimento ao cliente estejam preparados para o aumento de vendas.
- **Comunicação Clara e Transparente**
    - **Descrição Detalhada do Produto**: Melhorar as descrições dos produtos para garantir que os clientes saibam exatamente o que estão comprando, reduzindo insatisfações pós-compra.
    - **Respostas às Avaliações**: Responder proativamente às avaliações negativas, mostrando aos clientes que suas opiniões são valorizadas e que a empresa está comprometida em resolver problemas.
- **Aproveitamento dos Insights de Análise de Sentimentos**
    - **Uso de Bigramas e Trigramas**: Utilizar insights de bigramas e trigramas para identificar e corrigir os problemas mais comuns mencionados nas avaliações dos clientes.
    - **Monitoramento Contínuo**: Continuar monitorando as avaliações e feedbacks dos clientes para identificar novas tendências e problemas emergentes, ajustando as estratégias conforme necessário.
- **Monitoramento**
    - **Monitoramento Contínuo**: Monitorar continuamente as avaliações dos produtos e atuar rapidamente sobre feedbacks negativos.

### Recomendações para Vendedores

- **Qualidade do Produto**
    - **Controle de Qualidade**: Implementar rigorosos processos de controle de qualidade para garantir que todos os produtos atendam aos padrões de qualidade.
    - **Testes de Durabilidade**: Realizar testes de durabilidade para assegurar que os produtos sejam robustos e duradouros.
    - **Feedback dos Clientes**: Utilizar o feedback dos clientes para identificar padrões de problemas de qualidade e corrigi-los.
- **Funcionalidade**
    - **Testes de Funcionamento**: Garantir que todos os recursos dos produtos sejam testados exaustivamente antes do lançamento.
    - **Atualizações de Firmware**: Oferecer atualizações de firmware para corrigir problemas de software e melhorar o desempenho dos produtos.
    - **Manual do Usuário**: Fornecer manuais detalhados e tutoriais para ajudar os clientes a utilizarem os produtos corretamente.
- **Preço**
    - **Análise de Preços**: Realizar uma análise de preços para garantir que os produtos estejam competitivos no mercado.
    - **Promoções e Descontos**: Oferecer promoções e descontos para aumentar a percepção de valor.
    - **Pacotes de Valor**: Criar pacotes de produtos que ofereçam melhor custo-benefício.
- **Sentimento Negativo**
    - **Atendimento ao Cliente**: Melhorar o atendimento ao cliente para lidar rapidamente com problemas e queixas.
    - **Garantias e Políticas de Devolução**: Oferecer garantias e políticas de devolução flexíveis para aumentar a confiança dos clientes.
    - **Comunicação Clara**: Comunicar claramente as características e limitações dos produtos para alinhar as expectativas dos clientes.

## Limitações e Próximos Passos

A análise apresentou algumas limitações, como a quantidade insuficiente de avaliações para certos produtos ou categorias, o que restringiu a profundidade da análise nessas áreas. Além disso, os dados podem estar enviesados, uma vez que clientes mais propensos a deixar avaliações são geralmente aqueles que tiveram experiências extremamente positivas ou negativas, o que pode não representar a experiência geral dos consumidores.

Para aprimorar a análise, algumas ideias para o futuro incluem examinar como as avaliações e as vendas variam ao longo do tempo, permitindo identificar padrões sazonais ou tendências de longo prazo. Outra ideia é avaliar o efeito de diferentes campanhas promocionais nas avaliações dos produtos, ajudando a entender quais estratégias de marketing impactam positivamente a percepção dos clientes. Além disso, comparar as avaliações e o desempenho dos produtos com os de concorrentes diretos pode revelar pontos fortes e áreas de melhoria, fornecendo uma visão mais clara do posicionamento de mercado.

## Venha nos conhecer!

Quer saber mais sobre as autoras desse projeto? Acesse o nosso LinkedIn:

https://www.linkedin.com/in/eslaine-santos/

https://www.linkedin.com/in/maiully-data-science/

Obrigada por sua atenção!
