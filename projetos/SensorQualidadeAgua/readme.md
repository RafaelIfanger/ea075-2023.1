Sensor de Qualidade de Água
Water Quality Sensor

Apresentação
O presente projeto foi originado no contexto das atividades da disciplina de graduação EA075 – Sistemas Embarcados, oferecida no primeiro semestre de 2023, na Unicamp, sob supervisão da Profa. Dra. Paula Dornhofer Paro Costa, do Departamento de Engenharia de Computação e Automação (DCA) da Faculdade de Engenharia Elétrica e de Computação (FEEC).
O desenvolvimento será realizado pelos seguintes alunos:
Nome	RA	Curso
Rafael Ifanger Ribeiro	250499	Eng. Automação
Vicente José Campitelli Real	239834	Eng. Computação

Descrição do Projeto
O presente projeto destina-se a desenvolver um sensor que analise a qualidade da água em fluxo por um conduto, permitindo sua classificação em relação às possíveis aplicações desejadas, sejam elas provenientes de quaisquer fontes, como:
•	Captação de águas pluviais;
•	Efluentes (industriais, domésticos etc.);
•	Corpos hídricos;
•	Etc.

Utilizações possíveis
A partir do conjunto adequado de sensores e do desenvolvimento do firmware correspondente, o sistema proposto poderá ser utilizado em diversas aplicações, como, por exemplo: análise de água de aquário, destinação adequada de águas pluviais, análise de qualidade de corpos hídricos e definição do tratamento e destinação corretas de efluentes industriais em tempo real.
O projeto será desenvolvido visando o aproveitamento de águas pluviais em uma residência unifamiliar, devido a perspectiva de implementação prática imediata, sem envolver outros agentes externos ao desenvolvimento e a possiblidade de multiplicação da aplicação beneficiando a comunidade no entorno da Unicamp.

Motivação
A destinação adequada dos recursos de água doce é de tamanha importância na busca de uma economia sustável que foi escolhido para compor o capítulo 18 da Agenda 21. De modo coerente às recomendações da Agenda, em 21 de fevereiro de 1993, a Assembleia Geral da Organização das Nações Unidas, declarou o dia 22 de março como o “Dia Mundial da Água”. De acordo com a Wikipédia:
A cada ano, uma agência diferente das Nações Unidas produz um kit para imprensa sobre o DMA que é distribuído nas redes de agências contatadas. Este kit tem como objetivos, além de focar a atenção nas necessidades, entre outras, de:
Tocar assuntos relacionados a problemas de abastecimento de água potável;
Aumentar a consciência pública sobre a importância de conservação, preservação e proteção da água, fontes e suprimentos de água potável;
Aumentar a consciência dos governos, de agências internacionais, organizações não governamentais e setor privado;
Promover campanhas sobre a importância da água.
Portanto as sociedades já tomaram consciência que a água é um recurso a ser preservado e corretamente utilizado, justificando o projeto em tela.

Regulamentação aplicável
No Brasil, a Agência Nacional de Águas (ANA), publicou os Indicadores de Qualidade das Águas (IQA) para avaliar a qualidade da água bruta (água não tratada), adotando a sistemática que vinha sendo utilizada pela CETESB (Companhia Ambiental do Estado de São Paulo) desde 1975 (criado pela National Sanitation Foundation dos Estados em 1970). A composição do IQA está listada na tabela 1:
PARÂMETRO DE QUALIDADE DA ÁGUA	PESO (w)
Oxigênio dissolvido
0,17
Coliformes termotolerantes
0,15
Potencial hidrogeniônico - pH
0,12
Demanda Bioquímica de Oxigênio - DBO5,20
0,10
Temperatura da água
0,10
Nitrogênio total
0,10
Fósforo total
0,10
Turbidez
0,08
Resíduo total
0,08
Tabela 1: Indicadores de Qualidade das Águas (IQA) – fonte ANA

Conforme observado, na tabela 1, os IQA são nove parâmetros com respectivos pesos.
A publicação traz, ainda, o valor de qualidade em função da concentração de cada parâmetro, conforme figura 1:
 
Figura 1: Qualidade da Água em Cada Parâmetro do IQA – fonte ANA

A Agência reconhece as limitações de tal sistemática, posto que não são observados outros parâmetros importantes para o abastecimento, como o teor de substâncias tóxicas (pesticidas, metais pesados etc.) e agentes patogênicos entre outros.
Considerando as várias possiblidades de utilização das águas, o Conselho Nacional do Meio Ambiente-CONAMA, publicou a Resolução CONAMA nº 357, de 17 de março de 2005, que “dispõe sobre a classificação e diretrizes ambientais para o enquadramento dos corpos de água superficiais, bem como estabelece as condições e padrões de lançamento de efluentes”. Tal regulamentação classifica as águas doces, salinas e salobras em classes adequadas à diversas finalidades e amplia os parâmetros utilizados para tal classificação indicando, por exemplo, teores limites de contaminantes (orgânicos e inorgânicos) para os diversos usos.

[Descrição do objetivo principal do projeto, incluindo contexto gerador, motivação. Escreva essa seção imaginando que está tentando convencer alguém a investir financeiramente no seu projeto. Qual problema vocês pretendem solucionar? Quem são os potenciais usuários? É possível estabelecer um valor econômico associado?]

Descrição Funcional
Os componentes principais de hardware serão um processador e os sensores e atuadores.
O firmware será desenvolvido em linguagem C. Ele possibilitará a parametrização para as diversas aplicações, entretanto o desenvolvimento pleno será realizado para água pluvial, conforme item anterior.
O protótipo será montado para análise do parâmetro de turbidez, utilizando um sensor ótico. O estabelecimento da curva para determinar a qualidade da água por este parâmetro será feita de maneira empírica.
Além do sensor de turbidez de água, o sistema será dotado de uma chave de fluxo, para detectar o fluxo de água e de um atuador, no caso, um solenoíde de duas vias, possibilitando o direcionamento do fluxo de água para dois reservatórios a partir da classificação da água em fluxo. 
[@@@@A descrição funcional do projeto é a principal entrega do E1 e pode ser realizada neste próprio arquivo Markdown, com links para diagramas ou outros arquivos que estejam no próprio repositório]


Funcionalidades
As funcionalidades serão:  @@@@ 
[@@@@Detalhe todas as tarefas que o sistema será capaz de executar]
As funcionalidades do sistema se baseiam no objetivo de detectar a qualidade da água a partir da leitura de sensores por um microcontrolador. Desse modo, utilizando o sistema operacional de tempo real FreeRTOS, o sistema recolherá periodicamente os valores de sensores como de pH, turbidez e temperatura, por exemplo. Estes sensores tem propósito de fornecer parametros de qualidade da água com baixo custo e fácil implementacao. Armazenando as entradas, o sistema (microcontrolador), a partir de limiares de qualidade estabelecidos, definirá se a água do fluxo analisado está fora ou nao do aceitável. Se a qualidade for aceita, com uma válvula de duas viás, será liberado a continuidade do fluxo, caso contrário o fluxo é desviado para um local de armazenamento, que, pensando em um caso real, pode servir para uma análise mais detalhada em laboratório.

Configurabilidade
Como citado, o sistema deverá ser configurado para a aplicação a que se destinar, no caso em desenvolvimento aproveitamento de águas pluviais em uma residência unifamiliar. @@@@
[@@@@Detalhe, se houver, todas as possíveis configurações do circuito e todos os pontos de alteração da configuração]
As configuracoes do sistema sao o período de leitura dos sensores, podendo diminuir ou aumentar o tempo entre as leituras de cada sensor, e os limirares aceitáveis dos parametros lidos.

Eventos
A ser desenvolvido oportunamente 
[@@@@Quais eventos o sistema deve tratar? Se aplicável, classifique os eventos que são periódicos (procure especificar a periodicidade) e os que são não-periódicos (qual o tempo mínimo entre dois eventos sucessivos)?]
Nao se espera evento externo além dos dados dos sensores, sendo único evento possível a ser adicionado a configuracao dos limiares com um teclado matricial. Desse modo, fixo sao os eventos de leitura dos sensores, periódicos cuja periodicidade será definida de acordo com o número de amostras que se deseja obter para cada volume V de água que passa pelo sistema. Caso seja implementado o evento de configuracao por teclado matricial, este evento será nao periódico.

Tratamento de Eventos
A ser desenvolvido oportunamente 
[@@@@Qual comportamento o sistema deve ter para tratar corretamente cada evento?]
Para o evento de recepcao dos dados dos sensores, o tratamento será feito por uma tarefa periódica, que, ao longo de um tempo t, deve colher n amostras de modo que, periodicamente de T em T segundos, execute a leitura para armazenamento e tratamento dos dados. O tratamento dos dados será feita por uma outra tarefa nao periódica.
A qualidade da água definida pelo sistema será apresentada por um display.
Caso seja implementado a configuracao por teclado matricial, o tratamento será por interrupcao.
O microcontrolador que se deseja utilizar (ESP32 possui dois núcleos).

Descrição Estrutural do Sistema
A ser desenvolvido oportunamente 
[@@@@Junto com a descrição do comportamento do sistema, deve-se especificar, em nível de bloco ou sistema, a estrutura necessária para captar os eventos do mundo externo, para alojar e processar o programa de tratamento de eventos, e para atuar sobre o mundo externo.
Para essa descrição recomenda-se a criação de diagramas de blocos. Nesse diagrama, devem ser destacados os blocos funcionais que compõem o sistema, incluindo uma síntese das funcionalidades de cada bloco. Além disso, deve-se esclarecer também o relacionamento entre estes blocos, incluindo os principais sinais de comunicação entre os blocos de forma a assegurar a execução de todas as tarefas que o sistema deve realizar.
Você sabia? Ferramentas como o draw.io permitem integração com o Github.].
%3CmxGraphModel%3E%3Croot%3E%3CmxCell%20id%3D%220%22%2F%3E%3CmxCell%20id%3D%221%22%20parent%3D%220%22%2F%3E%3CmxCell%20id%3D%222%22%20value%3D%22%22%20style%3D%22rounded%3D0%3Bhtml%3D1%3BjettySize%3Dauto%3BorthogonalLoop%3D1%3BfontSize%3D11%3BendArrow%3Dblock%3BendFill%3D0%3BendSize%3D8%3BstrokeWidth%3D1%3Bshadow%3D0%3BlabelBackgroundColor%3Dnone%3BedgeStyle%3DorthogonalEdgeStyle%3BentryX%3D0.5%3BentryY%3D0%3BentryDx%3D0%3BentryDy%3D0%3BexitX%3D1%3BexitY%3D0.5%3BexitDx%3D0%3BexitDy%3D0%3B%22%20edge%3D%221%22%20parent%3D%221%22%3E%3CmxGeometry%20relative%3D%221%22%20as%3D%22geometry%22%3E%3CmxPoint%20x%3D%22650%22%20y%3D%22210%22%20as%3D%22sourcePoint%22%2F%3E%3CmxPoint%20x%3D%22310%22%20y%3D%2270%22%20as%3D%22targetPoint%22%2F%3E%3CArray%20as%3D%22points%22%3E%3CmxPoint%20x%3D%22710%22%20y%3D%22210%22%2F%3E%3CmxPoint%20x%3D%22710%22%20y%3D%2250%22%2F%3E%3CmxPoint%20x%3D%22310%22%20y%3D%2250%22%2F%3E%3C%2FArray%3E%3C%2FmxGeometry%3E%3C%2FmxCell%3E%3C%2Froot%3E%3C%2FmxGraphModel%3E

Glossário
Agenda 21: foi um dos principais resultados da conferência Eco-92 ou Rio-92, ocorrida no Rio de Janeiro, Brasil, em 1992. É um documento que estabeleceu a importância de cada país a se comprometer a refletir, global e localmente, sobre a forma pela qual governos, empresas, organizações não-governamentais e todos os setores da sociedade poderiam cooperar no estudo de soluções para os problemas socioambientais (fonte Wikipédia).

Referências
Agência Nacional das águas (ANA): Indicadores de Qualidade das Águas (IQA), disponível em http://pnqa.ana.gov.br/indicadores-indice-aguas.aspx, consulta em 15.mar.2023
Conselho Nacional do Meio Ambiente-CONAMA: Resolução CONAMA nº 357, de 17 de março de 2005, disponível em https://www.mpf.mp.br/atuacao-tematica/ccr4/dados-da-atuacao/projetos/qualidade-da-agua/legislacao/resolucoes/resolucao-conama-no-357-de-17-de-marco-de-2005/view#:~:text=Disp%C3%B5e%20sobre%20a%20classifica%C3%A7%C3%A3o%20dos,efluentes%2C%20e%20d%C3%A1%20outras%20provid%C3%AAncias, consulta em 15.mar.2023
Wikipédia: Dia Mundial da Água, disponível em https://pt.wikipedia.org/wiki/Dia_Mundial_da_%C3%81gua#:~:text=O%20Dia%20Mundial%20da%20%C3%81gua,com%20as%20recomenda%C3%A7%C3%B5es%20da%20Confer%C3%AAncia, consulta em 15.mar.2023
__ Agenda 21, disponível em https://pt.wikipedia.org/wiki/Agenda_21, consulta em 15.mar.2023
