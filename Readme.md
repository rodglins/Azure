Como os dados são definidos , armazenados, e acessados na computação em nuvem?


Fluxo de dados>> agendamento, controle, fluxo, monitoramento.

Estágios de processamento dos dados: 

Data warehouse moderno:
1) Ingestão (Azure Data Factory)
2) Armazenamento(Azure Data Lake Storage)
3) Preparação e treinamento (Azure Databricks - Spark Scala) Pipeline
4) Modelar e fornecer (Azure Synapse Analytcs>> Azure Analysis Services>> Power BI)

Análise avançada de Big Data:
1) Ingestão (Azure Data Factory)
2) Armazenamento(Azure Data Lake Storage)
3) Preparação e treinamento (Azure Databricks - sparklyr -Spark ML - SparkR), PolyBase
4) Modelar e fornecer (Azure Synapse Analytcs>> Azure Analysis Services>> Power BI) / Cosmos DB; Aplicativos em tempo real

Análise em tempo real:
1) Ingestão (Apache Kafka para HDInsight; Azure Data Factory)
2) Armazenamento(Azure Data Lake Storage)
3) Preparação e treinamento (Azure Databricks - sparklyr -Spark ML - SparkR), PolyBase
4) Modelar e fornecer (Azure Synapse Analytcs>> Azure Analysis Services>> Power BI) / Cosmos DB; Aplicativos em tempo real

---


Azure HDInsight
É um serviço de análise totalmente gerenciado, completo e open-source na nuvem para empresas. Na Microsoft, a análise por meio de software livre é implementada no Azure HDInsight. Para utilização de estruturas de software livre Hadoop, Apache Spark, Apache Hive, LLAP, Apache Kafka, Apache Storm e R.

É um sistema de processamento de dados distribuido na nuvem altamente disponível e seguro por padrao. No cerne deste sistema esta o apacha hadoop

Excelente opção para cargas de trabalho que envolvem a ingestão de dados para relatórios históricos e analises avançadas, além de dados de streaming para análise. Os dados podem ser ingeridos em uma só localização de Data Lake.

Gerencia o processamento em lotes, o data warehouse, as operações de ciência de dados e as cargas de trabalho de streaming pelas configurações do HDInsight. Há separação entre computação e armazenamento, diretamente sobre os mesmos dados.


Dados não estruturados>>Ingerir(Kafka no Azure HDInsight)>> Armazenar (Armazenamento do Azure)>>Preparar e treinar >> Spark no Azure HDInsight >>>Modelar e fornecer (Synapse / Azure HDInsight (LLAP)>> Inteligência (Interface de BI)


Executa transformações avançadas de dados de streaming com o Spark e Kafka no Azure HDInsight:


----------

Azure Stream Analytics
	É um mecanismo de processamento de eventos complexos e análise em tempo real desenvolvimento para analisar e processar simultaneamente altos volumes de dados de streaming rápido a partir de várias fontes.
	Indentifica padrões e relações em informações extraidas de diversas fontes de entrada, incluindo dispositivos, sensores, sequencias de cliques, feeds de midias sociais e aplicativos.

Tipos de trabalhos: 
	Analisa streams em tempo real de dispositivo IoT; análise de sequencia de clies/blogs; analise geoespacial para gerenciamento de frotas e veiculos sem motoristas; monitoramento remoto e manutenção preditiva de ativos de alto valor; analise em tempo real em dados de pontos de venda para detecção de anomalias e controle de estoque.

Como funciona?
	Consiste em uma entrada, um a consulta e uma saída. Ingere dados dos Hubs de eventos do Azure, incluindo Hubs de eventos do Azure do Apache Kafka, do Hub IoT do Azure ou armazenamento de Blobs do Azure.
	A consulta, que tem como base a linguagem de consulta SQL, usada para filtrar, classificar, agregar e associar dados de streaming com facilidade por um período de tempo.
	Cada trabalho tem uma ou várias saídas para os dados transformados e controla o que acontece em resposta as informações analisadas.

Funcionalidades:
	Envia dados para serviços como Azure Functions, Filas ou Tópicos do Barramento de Serviço para disparar comunicações ou de fluxos de trabalho personalizados downstream.
	Envia dados a um painel do Power BI para painéis en tempo real.
	Amazena dados em outros servicos de armanezamento do Azure (Azure Data Lake, Azure Synapse Analytics) para treinar um modelo de machine learning com base em dados históricos ou para executar a análise em lotes.

Arquitetura:
Ingerir (IoT, logs, dados clientes, transações, clima, negócios)>>Hubs de eventos; Armazenamento de blobs no Azure; Hub IoT>>Analisar (Inteligencia /analise em tempo real continua); Stream Analytics; Dados de referência (BD SQL, armazenamento de Blob); Pontuação em tempo (Azure ML)>>Fornecimento (Alertas e ações (Hubs de eventos, barramento de serviço, azure functions); Criação dinâmica de painéis (PowerBI); Data Warehousing (Azure Synapse Analytics); Amazenamento(DB SQL, Azure Datalake, CosmosDB, Serviço de armazenamento de blobs)


----

Desafio:
Definir um trabalho no Stream Analytics que le dados de streaming em tempo real e filtra mensagens indicando temperatuva acima de 27 graus. Seu trabalho no Stream Analytics lerá dados no Hub IoT, transformará os dados e fará write-back para um contêiner no armazenamento de blobs. Os dados de entrada usados neste início rápido sao gerador por um simulador online do Raspberry Pi.

-----








