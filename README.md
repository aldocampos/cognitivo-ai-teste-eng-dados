# COGNITIVO.AI - Teste Técnico

## Considerações sobre o ambiente de trabalho
*Utilizei o Jupyter Notebook, instalado em um ambiente Linux dentro de uma EC2. Decidi por essa configuração devido já ter todo o ambiente configurado.  .* 

*O código-fonte do teste técnico encontra-se no repositório Github: https://github.com/aldocampos/cognitivo-ai-teste-eng-dados/blob/master/resolucao.ipynb.* 

# Requisitos
1. Conversão do formato dos arquivos: Converter o arquivo CSV presente no diretório data/input/users/load.csv, 
para um formato colunar de alta performance de leitura de sua escolha. Justificar brevemente a escolha do formato. *Decidi por utilizar o Parquet por ser um arquivo do tipo colunar, e por causa da sua compressão dos dados e o reduzido disco I/O. Com essas características, o Parquet necessita de menos espaço para armazenar os dados e tem uma melhora significativa na performance das consultas. Reduzindo assim o custo do armazenamento e processamento dos dados, assim como o tempo para obter o resultado das consultas.*

2. Deduplicação dos dados convertidos: No conjunto de dados convertidos haverão múltiplas entradas para um mesmo registro, 
variando apenas os valores de alguns dos campos entre elas. 
Será necessário realizar um processo de deduplicação destes dados, a fim de apenas manter a última entrada de cada registro, 
usando como referência o id para identificação dos registros duplicados e a data de atualização (update_date) para definição do 
registro mais recente;

3. Conversão do tipo dos dados deduplicados: No diretório config haverá um arquivo JSON de configuração (types_mapping.json), 
contendo os nomes dos campos e os respectivos tipos desejados de output. Utilizando esse arquivo como input, realizar um 
processo de conversão dos tipos dos campos descritos, no conjunto de dados deduplicados;

# Notas gerais
- Todas as operações devem ser realizadas utilizando Spark. O serviço de execução fica a seu critério, podendo utilizar tanto 
serviços locais como serviços em cloud. Justificar brevemente o serviço escolhido (EMR, Glue, Zeppelin, etc.).

- Cada operação deve ser realizada no dataframe resultante do passo anterior, podendo ser persistido e carregado em diferentes 
conjuntos de arquivos após cada etapa ou executados em memória e apenas persistido após operação final.

- Você tem liberdade p/ seguir a sequência de execução desejada;

- Solicitamos a transformação de tipos de dados apenas de alguns campos. Os outros ficam a seu critério

- O arquivo ou o conjunto de arquivos finais devem ser compactados e enviados por e-mail.