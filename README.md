# Marketing Analytics

#### Aluno: [Manuel Sousa](https://github.com/manuelcalcada)
#### Orientadora: [Manoela Kohler](https://github.com/manoelakohler)


---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

---

### Resumo


Este trabalho aborda o desafio de aumentar a eficácia das campanhas de marketing de um banco europeu, utilizando a base de dados disponibilizada pela UCI. O principal objetivo é identificar quais clientes são mais propensos a adquirir um depósito oferecido pelo banco, otimizando o uso de recursos e maximizando as taxas de conversão. A necessidade de personalização das campanhas se torna evidente diante da diversidade dos perfis de clientes, com variações significativas em termos de idade, nível de educação, status de emprego e preferências de contato.

Para enfrentar este desafio, foram aplicados conceitos de segmentação de clientes e modelagem preditiva. A segmentação foi realizada utilizando técnicas de clusterização, que permitiram agrupar os clientes com características similares em clusters distintos. Cada cluster representa um perfil de cliente com comportamentos e necessidades específicas, possibilitando a criação de estratégias de marketing mais direcionadas e eficazes. A segmentação levou em consideração variáveis como idade, nível educacional, tipo de ocupação, status marital e histórico de inadimplência, resultando em grupos como "Executivos", "Tradicionais", "Jovens em Ascensão", entre outros.

Além da segmentação, um modelo de propensão à conversão foi desenvolvido para prever quais clientes, dentro de cada cluster, têm maior probabilidade de realizar a compra do depósito. Esse modelo utiliza técnicas de machine learning para analisar padrões comportamentais e identificar os leads mais promissores. A combinação de segmentação e modelagem preditiva permite ao banco direcionar seus esforços de marketing de forma mais precisa, economizando recursos e aumentando as chances de sucesso das campanhas.


### Abstract 

This work addresses the challenge of increasing the effectiveness of marketing campaigns for a European bank using a dataset provided by UCI. The primary goal is to identify which customers are most likely to purchase a deposit offered by the bank, optimizing resource usage and maximizing conversion rates. The need for personalized campaigns becomes evident given the diversity of customer profiles, with significant variations in age, education level, employment status, and contact preferences.

To tackle this challenge, concepts of customer segmentation and predictive modeling were applied. Segmentation was performed using clustering techniques, allowing the grouping of customers with similar characteristics into distinct clusters. Each cluster represents a customer profile with specific behaviors and needs, enabling the creation of more targeted and effective marketing strategies. The segmentation considered variables such as age, educational level, occupation type, marital status, and delinquency history, resulting in groups like "Executives," "Traditionals," "Young Up-and-Comers," among others.

In addition to segmentation, a conversion propensity model was developed to predict which customers within each cluster are most likely to purchase the deposit. This model uses machine learning techniques to analyze behavioral patterns and identify the most promising leads. The combination of segmentation and predictive modeling allows the bank to direct its marketing efforts more precisely, saving resources and increasing the success rate of campaigns.


### 1. Introdução

 O marketing moderno enfrenta desafios significativos ao tentar atingir o público certo em um cenário repleto de informações e ofertas. No setor financeiro, onde a competição é acirrada, é crucial identificar com precisão os clientes mais propensos a responder positivamente às campanhas, maximizando o retorno sobre o investimento (ROI) e minimizando desperdícios. A personalização das campanhas, baseada em um entendimento profundo dos perfis e comportamentos dos clientes, é fundamental para se destacar no mercado.

Neste projeto, o objetivo principal é aumentar a eficácia das campanhas de marketing de um banco, utilizando técnicas de segmentação e modelagem preditiva para otimizar a taxa de conversão. Isso envolve uma análise detalhada dos dados demográficos, comportamentais e transacionais para identificar os perfis de clientes com maior propensão à conversão, e o desenvolvimento de campanhas personalizadas para cada segmento identificado.

Além de segmentar os clientes, um modelo preditivo de propensão à conversão será desenvolvido, permitindo que as campanhas sejam direcionadas com mais precisão. A implementação de um otimizador de campanha, que ajusta os parâmetros em tempo real, garantirá que os esforços de marketing sejam eficientes, reduzindo o custo por conversão e aumentando o ROI.

Para medir o sucesso do projeto, serão utilizados KPIs como taxa de conversão, taxa de contato, custo por conversão, ROI e satisfação do cliente. Os principais stakeholders incluem as equipes de marketing, vendas, administração, TI e data science, que trabalharão em conjunto para garantir que as estratégias desenvolvidas sejam implementadas com sucesso na prática.

Neste projeto, a metodologia CRISP DM (Cross-Industry Standard Process for Data Mining) será utilizada para estruturar todo o processo de análise e modelagem. Inicialmente, a Compreensão do Negócio permitirá o alinhamento das metas de marketing com as necessidades do banco. Em seguida, a Compreensão dos Dados ajudará a explorar e identificar características relevantes na base de dados. Na etapa de Preparação dos Dados, os dados serão limpos e transformados para garantir sua adequação para as fases subsequentes. Durante a Modelagem, técnicas de machine learning serão aplicadas para desenvolver modelos preditivos e de segmentação. A Avaliação será realizada para validar a eficácia dos modelos, e, por fim, na etapa de Implantação, os insights e modelos serão aplicados na prática para otimizar as campanhas de marketing, garantindo que o banco atinja seus objetivos de conversão e ROI.

### 2. Modelagem

Inicialmente, foi realizada uma Análise Exploratória de Dados (EDA) univariada e bivariada para explorar cada variável individualmente e identificar os principais insights que pudessem gerar quick-wins e a criação de variáveis derivadas. Essa etapa foi crucial para entender a distribuição dos dados e a relação entre as variáveis, permitindo a identificação de padrões e tendências importantes. Com os insights obtidos, foram criadas variáveis derivadas que capturam nuances adicionais do comportamento dos clientes, preparando a base para a modelagem preditiva.

Na modelagem de propensão à conversão, diversos algoritmos foram testados, incluindo Logistic Regression, K-Nearest Neighbors, Decision Tree, Random Forest, XGBoost e Multi Layer Perceptron Neural Network. Para garantir a robustez do modelo, foram aplicadas técnicas de balanceamento de classes e redução de dimensionalidade. As métricas de avaliação priorizadas foram o F1-Score, ROC AUC, explicabilidade, precision, recall e acurácia. O XGBoost, com balanceamento via class weight e sem redução de dimensionalidade, se destacou como o modelo mais eficaz. Além disso, optou-se por separar a modelagem em dois submodelos: um para clientes já contactados em campanhas anteriores e outro para leads inéditos. 

Complementando a modelagem, foi realizada uma segmentação não supervisionada usando o K-means, combinada com técnicas de redução de dimensionalidade como PCA. A avaliação dos clusters foi feita utilizando WCSS, a curva da silhueta e Davies Bouldin, garantindo uma segmentação precisa e informativa.


### 3. Resultados

A campanha alcançou uma **taxa de conversão de 11%**, convertendo aproximadamente **4,6 mil clientes**. A **taxa de conversão de chamadas** foi de 4%, mas o **contact rate** foi de 39%, refletindo uma boa taxa de resposta. **4,2 mil clientes** foram impactados mensalmente, com picos em maio, julho, agosto e novembro, sugerindo a necessidade de otimização no público-alvo.

#### Análise Demográfica

- **Idade**: A campanha focou mais em **indivíduos jovens** (média de 40 anos), com bom desempenho entre a **Geração Y** e pessoas acima de 60 anos. A maioria dos clientes contactados pertence à **Geração X** e **Baby Boomers**.
- **Ocupação**: A maioria dos clientes potenciais trabalha em funções **administrativas**, com bom desempenho também entre **aposentados**, **estudantes** e **desempregados**.
- **Estado Civil**: **60% dos leads são casados**, mas a melhor conversão foi observada entre os **solteiros**.
- **Educação**: A campanha teve mais sucesso entre aqueles com **ensino superior**, enquanto os com **educação básica** apresentaram pior desempenho.

#### Análise de Empréstimos e Inadimplência

- **Empréstimo Pessoal**: A presença de empréstimos pessoais não demonstrou correlação significativa com a decisão de adquirir o depósito.
- **Empréstimo Habitacional**: Leads com **empréstimos habitacionais** mostraram uma ligeira tendência a converter melhor, indicando estabilidade financeira.
- **Inadimplência**: A maioria dos leads não está inadimplente, mas os dados ausentes sobre inadimplência têm uma taxa de conversão pior.

#### Métodos de Contato

- **Tipo de Contato**: **63,5% dos leads foram contatados via celular**, com uma taxa de conversão significativamente melhor comparada ao telefone fixo. Indivíduos mais jovens e com maior poder aquisitivo tendem a preferir celulares.
- **Contato em Campanhas Anteriores**: Apenas **14% dos leads foram contatados em campanhas anteriores**, com a maioria tendo recusado antes.
- **Número e Frequência de Contatos**: A média foi de **2,5 contatos por lead**. A eficácia foi maior no **primeiro contato**, e o tempo entre campanhas foi em média de **6 dias**.

Os dois modelos de propensão desenvolvidos podem ser utilizados para identificar os clientes (a nível individual) com maior propensão a conversão, enquanto que o modelo de segmentação identifica perfis e direciona ações específicas. 

Da segmentação, chegamos nos seguintes perfis de clientes:

Aqui está uma descrição dos clusters com base nas características fornecidas:


#### **Cluster 0 - Experientes**

- **Perfil**: Leads mais velhos.
- **Educação**: Pouca educação formal.
- **Inadimplência**: Alta.
- **Ocupação**: Majoritariamente trabalhadores manuais, com alta representação de não-empregados, especialmente aposentados.
- **Estado Civil**: Quase todos são casados.
- **Método de Contato**: Preferência por celular.
- **Taxa de Conversão**: Média.

####  **Cluster 1 - Executivos**

- **Perfil**: Leads mais velhos.
- **Educação**: Altíssima educação formal.
- **Inadimplência**: Baixa.
- **Ocupação**: Majoritariamente profissionais de escritório.
- **Estado Civil**: Todos são ou foram casados.
- **Método de Contato**: Preferência por celular.
- **Taxa de Conversão**: Média-Alta.

#### **Cluster 2 - Tradicionais**

- **Perfil**: Leads de pouca educação formal.
- **Educação**: Pouca educação formal.
- **Inadimplência**: Alta.
- **Ocupação**: Majoritariamente trabalhadores manuais.
- **Estado Civil**: A maioria são casados.
- **Método de Contato**: Preferência por telefone fixo.
- **Taxa de Conversão**: Baixíssima.

#### **Cluster 3 - Versáteis**

- **Perfil**: Leads com alta educação formal.
- **Educação**: Alta.
- **Inadimplência**: Média.
- **Ocupação**: Majoritariamente profissionais de escritório, com alta representação de autônomos.
- **Estado Civil**: Maioria casados, mas com alta representatividade de solteiros.
- **Método de Contato**: Preferência por telefone fixo.
- **Taxa de Conversão**: Baixíssima.

#### **Cluster 4 - Jovens em Ascensão**

- **Perfil**: Leads mais jovens.
- **Educação**: Alta.
- **Inadimplência**: Baixíssima.
- **Ocupação**: Boa representatividade de trabalhadores de escritórios, trabalhadores manuais de maior renda e estudantes.
- **Estado Civil**: Solteiros.
- **Método de Contato**: Preferência por celular.
- **Taxa de Conversão**: Alta.


### 4. Conclusões

Das análises, surgiram quick-insights acionáveis como:

**Otimização do Público-Alvo**: Para melhorar a eficácia das campanhas, é recomendável segmentar **jovens e aposentados**. Além disso, é importante focar em leads que possuem um **histórico positivo** em campanhas anteriores, pois esses indivíduos têm maior propensão a converter.

**Métodos de Contato**: A prioridade deve ser dada aos **contatos via celular**, já que esse método demonstrou uma taxa de conversão significativamente superior em comparação ao telefone fixo.

**Timing e Frequência**: É mais eficaz concentrar os esforços no **primeiro contato**, já que a probabilidade de conversão é maior nesse estágio. A frequência de contatos subsequentes deve ser reduzida para evitar a diminuição da eficácia.

**Segmentação Ocupacional**: A campanha deve focar em **indivíduos em funções administrativas** e **estudantes**, pois esses grupos apresentaram boas taxas de conversão.

**Educação e Estado Civil**: As campanhas devem ser direcionadas para indivíduos com **ensino superior**, que mostraram maior sucesso em conversões. Além disso, estratégias específicas devem ser desenvolvidas para **solteiros**, que apresentaram a melhor taxa de conversão entre os estados civis analisados.




Para segmentar a mensagem, canal e produto a fim de otimizar a campanha para cada público, recomendamos as seguintes personalizações:




**Experientes**


- **Benefícios de Estabilidade**: Promova a segurança e estabilidade do depósito como uma forma de complementar a aposentadoria ou poupar para o futuro.
- **Simplicidade e Facilidade de Acesso**: Ofereça um processo simplificado, com suporte para sanar dúvidas rapidamente via celular, já que a educação formal é baixa.


**Executivos**


- **Ofertas Exclusivas**: Apresente o depósito como um produto premium, destacando benefícios exclusivos e taxas de retorno mais altas, apelando ao senso de valor agregado.
- **Consultoria Personalizada**: Ofereça serviços de consultoria financeira, enfatizando estratégias de investimento que complementem o depósito, algo que ressoe com seu alto nível de educação.


**Tradicionais**


- **Condições de Acesso Facilitadas**: Ofereça condições especiais para quem enfrenta dificuldades financeiras, como depósitos com valor inicial mais baixo ou flexibilidade em saques.
- **Campanhas Educativas**: Crie campanhas que expliquem de forma simples e direta os benefícios do depósito, usando linguagem acessível e exemplos práticos.


**Versáteis**


- **Flexibilidade e Personalização**: Destaque a flexibilidade do depósito para atender às necessidades de profissionais com rendas variáveis, como autônomos.
- **Comunicação Assertiva**: Use uma abordagem mais direta e técnica nas comunicações, focando em dados e números que mostrem o retorno do investimento.


**Jovens em Ascensão**


- **Ofertas de Longo Prazo**: Promova o depósito como uma maneira inteligente de começar a poupar cedo, com foco em metas de longo prazo como comprar uma casa ou financiar estudos adicionais.
- **Campanhas Digitais e Gamificadas**: Use campanhas digitais e gamificadas que ressoem com o estilo de vida conectado e a familiaridade com tecnologia desse grupo.
- **Incentivos de Carreira**: Ofereça pacotes que combinem o depósito com oportunidades de crescimento profissional, como cursos ou parcerias com instituições educacionais.

---

Matrícula: 202.100.175

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
