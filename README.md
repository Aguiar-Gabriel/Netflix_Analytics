# Netflix Projeto Integrado Big Data

A Internet das Coisas (Internet of Things, IoT) está cada vez mais presente no cotidiano das pessoas de diferentes formas, desde a produção na indústria até em suas próprias casas e condomínios inteligentes. Nesse sentido, um dos setores em que a IoT tem sido amplamente utilizada é o de entretenimento, com plataformas de streaming de vídeo como a Netflix. Com isso, há uma grande quantidade de dados que podem ser coletados dos dispositivos utilizados para assistir a esses conteúdos, possibilitando uma análise aprofundada do comportamento dos usuários e dos dispositivos mais utilizados.

Neste trabalho, iremos explorar os dados extraídos da Netflix, em que foram utilizados os seguintes dispositivos: 'DefaultWidevineAndroidPhone', 'LG DTV 2020 RTK K6Hp UHD TV Smart TV', 'Android DefaultWidevineL3Phone Android Phone', 'Samsung 2018 Kant-M2 UHD TV (1.5G) Smart TV', 'LG 2018 Mstar LM18A STD UHD TV Smart TV', 'Xiaomi volver Smart TV', 'Chrome PC (Cadmium)', 'LG LG 2017 MStar M2R Standard DTV Smart TV', 'Android DefaultWidevineL3Phone Android Phone (motorola_MotoG3)', 'Philips 2013 MTK5396 based TVs Smart TV'.

A motivação para este trabalho é identificar padrões de média de tempo assistido em cada dispositivo, entender quais dispositivos são utilizados por quais perfis de usuários e identificar os dispositivos mais utilizados para assistir conteúdo na plataforma. Além disso, serão realizadas comparações entre a duração média das visualizações em diferentes tipos de dispositivos, análises da distribuição das visualizações por dispositivo ao longo do tempo e identificação de diferenças significativas no comportamento de uso da plataforma entre usuários que utilizam diferentes dispositivos. Será também explorada a relação entre o tipo de dispositivo utilizado e outras variáveis, como país, gênero ou idade dos usuários. Com isso, espera-se contribuir para o avanço no conhecimento da área de IoT e análise de dados em entretenimento, permitindo uma compreensão mais aprofundada do comportamento dos usuários e dos dispositivos utilizados para acessar conteúdos de streaming.

2.3. Coleta de dados

Desenvolver um relatório que especifique os metadados dos dados coletados. O relatório deve conter:

- **Introdução**:

A Netflix é uma plataforma de streaming que armazena uma grande quantidade de dados sobre as visualizações dos seus usuários. O processo de geração desses dados é feito por meio de uma tabela chamada ViewingActivity, que contém informações como o nome do perfil usado para assistir, a data e hora de início da visualização, a duração da sessão, entre outras.

Dentre as informações armazenadas na tabela, destaca-se o campo "Device Type", que indica o tipo de aparelho utilizado para acessar a série ou o filme. Isso permite à plataforma identificar quais dispositivos são mais utilizados pelos seus usuários para assistir conteúdo, bem como comparar a duração média das visualizações em diferentes tipos de dispositivos.

Além disso, a distribuição das visualizações por dispositivo ao longo do tempo também é analisada, permitindo à Netflix identificar se existem diferenças significativas no comportamento de uso da plataforma entre usuários que utilizam diferentes dispositivos.

Para armazenar esses dados, a Netflix utiliza bancos de dados que são projetados para atender às suas necessidades de armazenamento e análise de dados em larga escala. A tabela ViewingActivity, por exemplo, é armazenada em um banco de dados relacional que permite a realização de consultas e análises sobre as visualizações dos usuários. Além disso, a Netflix utiliza tecnologias como o Apache Cassandra para armazenar dados em grande escala e o Apache Hadoop para processamento de dados distribuído. Tudo isso é necessário para garantir que a plataforma possa processar e analisar grandes volumes de dados de maneira eficiente e escalável.

- **Dicionário de dados**:

Nome do arquivo: viewing_activity.csv

Itens de dados gerados e armazenados no projeto:

- Profile Name: o nome do perfil usado para assistir.
- Start Time: a data e a hora (UTC) do início da visualização.
- Duration: a duração da sessão.
- Attributes: esta coluna mostra detalhes adicionais das interações com o conteúdo acessado, quando disponíveis:
    - Autoplayed: user action: None: significa que o assinante não interagiu com essa série ou filme.
    - Autoplayed: user action: Unspecified: significa que o assinante interagiu com a série ou o filme (clicando na imagem da caixa e visualizando a página da série ou do filme enquanto é apresentado o conteúdo automático) ou que assistiu ao conteúdo automático por mais de 2 minutos.
    - Autoplayed: user action: User_Interaction: significa que o assinante interagiu com a série ou o filme em um navegador clicando nos controles do player ou utilizando os atalhos do teclado.
    - View was hidden: indica que a série ou filme foi marcado como “Ocultar do histórico do que foi assistido” nas configurações da conta.
    - Has branched playback: indica que o assinante pode escolher opções enquanto assiste ao título, para controlar o que acontece em seguida.
- Title: a série ou o filme assistido.
- Supplemental Video Type: vídeos que não sejam uma série ou um filme, como trailers ou montagens. A referência “N/A” significa “não se aplica”.
- Device Type: o tipo de aparelho utilizado para acessar a série ou o filme.
- Bookmark: a posição de visualização mais recente (em relação à duração total da série ou do filme) da sessão de reprodução específica de uma série ou um filme.
- Latest Bookmark: indica se o marcador é a posição de visualização mais recente (em relação à duração total da série ou do filme) na sessão de reprodução mais recente de uma série ou filme. A referência “Not latest view” indica que uma determinada sessão de reprodução não é a reprodução mais recente da série ou do filme e que, portanto, o marcador não é o mais recente.
- Country: o país de onde a série ou o filme foi assistido. Para assinantes na União Europeia que viajam por até 60 dias de um país para outros países da União Europeia, a partir de 1º de abril de 2018, este é o país em que a conta foi criada e não o país em que a série ou o filme foi assistido.
- **Considerações finais**:
    
    Além disso, falhas nos equipamentos podem ocorrer e afetar a coleta de dados. Por exemplo, pode haver problemas com a conexão à internet ou com o próprio dispositivo de medição. É importante monitorar e resolver rapidamente quaisquer problemas técnicos que possam afetar a coleta de dados.
    
    Outra questão importante é a possibilidade de viés na coleta de dados. Por exemplo, pode haver uma preferência entre os usuários por assistir a determinados tipos de conteúdo em determinados dispositivos, o que pode afetar a análise dos dados. É importante levar em consideração essas possíveis fontes de viés e tentar minimizá-las por meio de técnicas estatísticas adequadas.
    
    Em resumo, é fundamental monitorar continuamente a coleta de dados, identificar possíveis problemas e adaptar o equipamento ou a metodologia de coleta para garantir que os dados coletados sejam confiáveis e possam ser usados para tomada de decisões precisas e informadas.
    

Ao finalizar este projeto, podemos concluir que a análise de dados é extremamente importante para as empresas, como a Netflix, que precisam entender o comportamento de seus usuários e aprimorar a experiência deles na plataforma.

A coleta de dados precisa ser realizada de forma adequada e confiável para que as análises feitas a partir desses dados sejam precisas e relevantes. Além disso, é importante ressaltar que a privacidade dos usuários deve ser respeitada e a coleta de dados deve ser feita de acordo com as leis e regulamentações em vigor.

Neste projeto, foi possível identificar os dispositivos mais utilizados para assistir conteúdo na plataforma, comparar a duração média das visualizações em diferentes tipos de dispositivos, analisar a distribuição das visualizações por dispositivo ao longo do tempo e identificar diferenças significativas no comportamento de uso da plataforma entre usuários que utilizam diferentes dispositivos. Também foi analisada a relação entre o tipo de dispositivo utilizado e outras variáveis, como país, gênero ou idade dos usuários.

Por fim, é importante destacar que a análise de dados é um processo contínuo e que novas questões podem surgir à medida que novos dados são coletados e novas tecnologias são utilizadas. Por isso, é fundamental que as empresas invistam em profissionais capacitados para lidar com dados e em tecnologias que permitam a coleta e análise de dados de forma confiável e eficiente.

2.4. Análise exploratória e visualização dos dados feita em um notebook utilizando Jupyter:

[relatório_netflix_devices_data_analytics.ipynb](Netflix%20Projeto%20Integrado%20Big%20Data%2033929c9514e34db1a6975d56f9478617/relatrio_netflix_devices_data_analytics.ipynb)

2.5. Link de como coletar dados da sua própria conta:
https://help.netflix.com/pt/node/100624#:~:text=Como%20faço%20para%20obter%20uma,para%20produzir%20as%20informações%20solicitadas.
