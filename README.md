**Resumo: **A LÓGICA _FUZZY _É UMA TÉCNICA QUE EMPREGA UM GRAU DE INCERTEZA E GRADIENTES DE VERDADE PARA AVALIAR E CALCULAR O PERTENCIMENTO DE UMA VARIÁVEL DE ENTRADA À UMA OU MAIS VARIÁVEIS DE SAÍDA. É AMPLAMENTE UTILIZADA EM SISTEMAS DE APOIO A DECISÃO, CONTROLADORES E QUALQUER APLICAÇÃO DE ANÁLISE MULTIVALORADA. NESTE PRISMA, PODE SER UTILIZADA PARA IMITAR O PROCESSO DECISÓRIO HUMANO. ESTE ARTIGO PROPÕE ENTÃO UM MÉTODO DE CÁLCULO DO ESTOQUE DE SEGURANÇA LOCAL EM UMA EMPRESA MULTINACIONAL DO RAMO DE SAÚDE, CONSIDERANDO AS EXIGÊNCIAS LOCAIS E CARACTERÍSTICAS PARTICULARES.

**1. Introdução  **

Desde o início da década de 1990 diversas empresas multinacionais se instalaram no país no processo de globalização e internacionalização do capital que foi observado no mundo. Algumas delas montaram escritórios de gestão comercial e suporte técnico localmente, enquanto toda a produção continua sendo importada da matriz. Esse é o caso da empresa abordada, uma empresa jovem porém vigorosa do ramo de ciência da vida (_lifescience_) que importa e comercializa equipamentos e insumos para diagnósticos e pesquisa. Os insumos constituem a parte majoritária do volume de importação da empresa, demandando muitos recursos para o planejamento e controle da logística envolvida. Este processo logístico é totalmente nacional, sujeitos a atrasos e custos administrativos que a matriz não é instrumentalizada para prever. 

Diversos fatores modificam a dinâmica de fornecimento no Brasil, desde o sistema fiscal tributário até as condições do processo aduaneiro. Por isso se justifica uma boa gestão de estoque local, para poder fazer uma entrega rápida e confiável em um cenário onde a importação é difícil, onerosa e lenta.

Para Borges et al (2010), um bom gerenciamento de estoques ajuda na redução do valor comprometido no inventário, de forma a minimizá-lo, mas dentro dos níveis de segurança e dos volumes para o atendimento da demanda. A empresa abordada trabalha com contratos _SLA (Service Level Agreement)_ e contratos de fornecimento estatais, que podem gerar multa e descontinuação onerosa do contrato caso a demanda não seja suprida em um prazo pré-estabelecido, independente do prazo logístico e burocrático envolvido.

No caso estudado, o cálculo do estoque mínimo de segurança é feito de forma discricionária, onde o responsável pela gestão logística despende tempo e recursos para decidir de forma muito subjetiva qual o pedido semanal de cada item no catálogo para garantir o estoque mínimo local (de segurança) para atender a demanda dos clientes, baseado em sua experiência, médias e observações. Esta atividade se provou extremamente laboriosa, e com a expansão do catálogo com lançamentos de novos produtos e expansão das linhas de fornecimento, se tornou inviável. Várias tentativas de cálculo foram feitas utilizando lógica clássica e algoritmos binários porém a característica multivalorada do problema causa uma desproporcionalidade de pesos e as condições para tratamento das variáveis se tornam inviáveis. 

A proposta deste artigo é sistematizar os pontos observados pelo responsável do pedido semanal de importação para compor o estoque mínimo local e poder assim suprir as necessidades dos clientes ao longo do tempo utilizando Lógica _Fuzzy_. Levando em consideração a incerteza da demanda, tendência de aumento ou diminuição, a validade dos itens e o seu custo.

**2. Estoque de segurança**

O estoque de segurança é o estoque mínimo para garantir o fornecimento ininterrupto a uma demanda histórica (Sanjay & Aditya, 2015).

É uma área da gestão de estoques, e ponto de partida para o cálculo do estoque e inventário.


            A gestão de estoques visa elevar o controle de custos e melhorar a qualidade dos produtos guardados na empresa. As teorias sobre o tema normalmente ressaltam a seguinte premissa: é possível definir uma quantidade ótima de estoque de cada componente e dos produtos da empresa, entretanto, só é possível defini-la a partir da previsão da demanda de consumo do produto (DIAS, 2010).

O estoque de segurança tenta prever o nível de serviço e acomodar eventuais picos de demanda do produto. (SANJOY & SHAMS, 2017), no entanto a lógica clássica não consegue prever variações além do binário de forma eficiente, o que torna o cálculo muito mais complexo e extenso.

**3. Metodologia**

Foi desenvolvida uma pesquisa aplicada no que diz respeito ao procedimento empregado no cálculo do estoque de segurança, assim como o acompanhamento de várias semanas de cálculos reais e avaliação de suas implicações para a empresa, valoração e estudo das variáveis.

Antes de aplicar a metodologia e simplesmente retornar um resultado numérico, os dados foram testados e inseridos em um _software _ especializado, _FuzzyLite_, para que os dados fossem visualizados e validados pelo operador.

Após isso, foi gerado então um código para que pudesse interagir com um banco de dados e se integrar ao resto da rotina de cálculo. do estoque.

**3.1 Dados de entrada**

Inicialmente foi feito um levantamento das possíveis variáveis de entrada e que tipos de dados seriam disponibilizados para elaboração do sistema de cálculo, sendo que o único dado recorrente é a demanda semanal, seguido do custo.

Porém, isso nos dava somente um número, sem sua significância no contexto organizacional. Era necessário extrair mais informações dos números dos pedidos, sendo então definido que o custo seria uma variável única, normalizado em relação à lista de importação total e a validade seria uma variável de entrada, um dado bruto, sem normalização ou tratamento paramétrico.

Já o histórico fornecido pela Matriz, dos pedidos semanais de cada item nos últimos seis meses (28 semanas), gera 3 variáveis importantes, com diferentes significados e classificações, o primeiro é a média de pedidos semanais, pois a variável de saída será um coeficiente da média simples observada nos últimos seis meses.

Um outro dado muito valorizado pelo operador é o aumento ou diminuição da demanda pois caso um item seja retirado de linha, ele terá sua demanda gradativamente reduzida e caso um ítem seja introduzido, sua demanda crescerá até atingir um patamar estável, o modelo deve acomodar este tipo de situação (HEATH & JACKSON, 1994**)**. Esta característica foi caracterizada como o ângulo da regressão linear dos números pedidos das últimas 3 semanas, quanto maior o ângulo, maior o crescimento.

A instabilidade ou flutuação na demanda também deve ser considerada e foi medida através do desvio padrão relativo à média, quanto maior o desvio padrão (em porcentagem da média de pedidos) exige um aumento no pedido semanal do ítem para assegurar sua disponibilidade em estoque. (SANJOY & SHAMS 2017)

 

**4. A Lógica Fuzzy**

A lógica fuzzy busca determinar um número que descreve um conjunto elevado de variáveis incertas e vagas associando intervalos a variáveis linguísticas, flexibilizando a aplicação da lógica clássica estendendo e facilitando seu uso em condições multivariadas e multidimensionais agregando valores a variáveis além do conceito binário [0,1] de modo que sua implementação possibilita o tratamento de variáveis antes fugiam ao controle. (SHAW; SIMÕES, 1999).

A primeira ocorrência da expressão "lógica _fuzzy_" (nebulosa) para ser utilizada com base na teoria de conjuntos _fuzzy _foi usada no artigo _Fuzzy Sets_ (ZADEH, 1965).

A característica de lidar com a ambiguidade da informação e a incerteza do mundo real fez com que este raciocínio fosse aplicado em pesquisas de diversas áreas, tais como sistemas de controle e inteligência artificial devido sua capacidade de imitar o raciocínio humano, que considera verdades parciais ou graus de verdade. (GIGCH; PIPINO, 1980)

Na lógica fuzzy, as variáveis são associadas a termos que definem seu pertencimento e as operações são feitas a partir da linguagem natural, cujo maior benefício é a codificação de conhecimentos inexatos, se aproximando de um modelo cognitivo, característicos da mente humana (RUHOFF et al., 2005).  

**4.1 O Modelo Proposto**

**4.1.2 Classificação e valoração das variáveis**

Após definidas as variáveis de entrada (Item 3.1), é importante classificar e associar os intervalos das variáveis a termos linguísticos. Todas as variáveis foram classificadas com 5 graus de intensidade seguindo uma escala psicométrica de valoração (LIKERT, 1932), Muito Baixo, Baixo, Neutro, Alto e Muito Alto.

As variáveis de entrada lineares (desvio_padrao, validade e custo) foram classificadas e valoradas conforme a Figura 1 descreve, em ordem MuitoBaixo (0,0,20,30), Baixo (10,20,30), Neutro (20,40,60,80), Alto (70,80,90), MuitoAlto(70,80,100,100). Sendo que ela varia de 0-100, representando sempre uma porcentagem de extremos, no caso real aplicado o desvio_padrao é uma porcentagem do desvio sobre a média (dados superiores a 100 serão classificados como 100), a validade varia de 3 meses (0) e 18 meses (100) e o custo é normalizado dentro de todo o catálogo de importação da empresa (0 o mais barato e 100 o mais caro).



<p id="gdcalert1" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/A-Inteligencia0.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert2">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/A-Inteligencia0.png "image_tooltip")
 

Figura 1 - Discurso Fuzzy das Variáveis Lineares (desvio_padrao, validade e custo)

A variável que representa a flutuação (aumento ou diminuição da demanda) das últimas 3 ocorrências do estoque é descrita em radianos (varia de -pi/2 a pi/2), portanto não seria numericamente acurado utilizar os mesmos intervalos para sua classificação porém é válido utilizar a mesma escala psicométrica de valoração MuitoBaixo (-1.570, -1.570, -0.392, -0.196), Baixo  (-0.392, -0.196, -0.098), Neutro  (-0.196, 0.000, 0.196), Alto (0.098, 0.196, 0.392), MuitoAlto  (0.196, 0.392, 1.570, 1.570). A Figura 2 descreve graficamente a valoração utilizada para a variável alpha_demanda (análise da variação da demanda).



<p id="gdcalert2" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/A-Inteligencia1.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert3">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/A-Inteligencia1.png "image_tooltip")


Figura 2 - Discurso _Fuzzy _da Variável angular(alpha_demanda)

**4.1.3  Regras _Fuzzy_**

Para que um valor numérico seja calculado é necessário criar regras para que as variáveis possam interagir entre si e gerar um número após a defuzzificação, embora a classificação seja idêntica a todas as variáveis (de entrada e saída), a interação é diversa, conforme a Tabela 1 exemplifica:


<table>
  <tr>
   <td>Número
   </td>
   <td>Regra
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td>SE desvio_padrao é Alto então Estoque é Alto
   </td>
  </tr>
  <tr>
   <td>2
   </td>
   <td>SE desvio_padrao é MuitoAlto então Estoque é MuitoAlto
   </td>
  </tr>
  <tr>
   <td>3
   </td>
   <td>SE alpha_demanda é MuitoBaixo então Estoque é MuitoBaixo
   </td>
  </tr>
  <tr>
   <td>4
   </td>
   <td>SE alpha_demanda é Baixo então Estoque é Baixo
   </td>
  </tr>
  <tr>
   <td>5
   </td>
   <td>SE alpha_demanda é Neutro então Estoque é Neutro
   </td>
  </tr>
  <tr>
   <td>6
   </td>
   <td>SE alpha_demanda é Alto então Estoque é Alto
   </td>
  </tr>
  <tr>
   <td>7
   </td>
   <td>SE alpha_demanda é MuitoAlto então Estoque é MuitoAlto
   </td>
  </tr>
  <tr>
   <td>8
   </td>
   <td>SE validade é MuitoBaixo então Estoque é MuitoBaixo
   </td>
  </tr>
  <tr>
   <td>9
   </td>
   <td>SE validade é Baixo então Estoque é Baixo
   </td>
  </tr>
  <tr>
   <td>10
   </td>
   <td>SE validade é Neutro então Estoque é Neutro
   </td>
  </tr>
  <tr>
   <td>11
   </td>
   <td>SE validade é Alto então Estoque é Alto
   </td>
  </tr>
  <tr>
   <td>12
   </td>
   <td>SE validade é MuitoAlto então Estoque é MuitoAlto
   </td>
  </tr>
  <tr>
   <td>13
   </td>
   <td>SE custo é MuitoBaixo então Estoque é MuitoAlto
   </td>
  </tr>
  <tr>
   <td>14
   </td>
   <td>SE custo é Baixo então Estoque é Baixo
   </td>
  </tr>
  <tr>
   <td>15
   </td>
   <td>SE custo é Neutro então Estoque é Neutro
   </td>
  </tr>
  <tr>
   <td>16
   </td>
   <td>SE custo é Alto então Estoque é Baixo
   </td>
  </tr>
  <tr>
   <td>17
   </td>
   <td>SE custo é MuitoAlto então Estoque é MuitoBaixo
   </td>
  </tr>
</table>


Tabela 1 - Regras _Fuzzy_

As regras 1 e 2 alteram o resultado, pois se o desvio_padrao é alto a incerteza em relação aos dados históricos aumenta, o que acarreta uma maior acumulação do item para o estoque, porém, se seu número for minimizado não há alteração ao número necessário para acumulação (quanto menor o desvio padrão, mais precisa é a média simples).

As regras de 8 a 12 são lineares e diretas, ou seja, quanto maior a validade do item maior o estoque. Embora seja a regra de maior simplicidade é crucial para que o estoque não acarrete perdas e descartes de produtos devido a expiração de sua validade.

As regras 9 a 17 são lineares, porém inversas, ou seja, quanto maior o custo, menor o estoque. A econometria sugere que quanto menor o valor empatado em estoque maior a eficiência financeira da organização. (BORGES et al, 2010)

**4.1.4  Resultado**

Esta combinação gera um número de saída, que é representado pela variável Estoque, com a forma idêntica a Figura 1, porém  variando de -1 a 1 e o intervalo linguístico sendo: MuitoBaixo  (-1.000, -1.000, -0.800, -0.600), Baixo  (-0.800, -0.600, -0.400), Neutro (-0.600, -0.400, 0.400, 0.600), Alto  (0.400, 0.600, 0.800), MuitoAlto  (0.600, 0.800, 1.000, 1.000). 

Após a defuzzificação é gerado um número que nada mais é que o coeficiente de alteração da média semanal dos últimos seis meses, descrito pela Equação abaixo:



<p id="gdcalert3" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert4">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>



Seguindo então a lógica do operador de utilizar a média aritmética semanal do estoque como base e a altera ponderando sobre a flutuação, a tendência, o custo e a validade dos produtos importados.

**5. Conclusão**

Embora o método descrito aqui seja de certa forma simplório, após várias semanas de testes reais, ele comprovou sua validade como automatizador de um processo manual de avaliação de estoque. 

Como todos os sistemas chamados cognitivos ele tem pouca  capacidade de generalização a outros cenários, porém robusto para a aplicação projetada, ainda que tenha sua adaptação facilitada pela própria natureza da técnica. 

Alguns pontos que são facilmente customizáveis a diferentes cenários é a adequação das curvas de pertinência (formato e amplitude), das regras combinatórias (Se .. Então) e a possível adição de pesos às variáveis, onde além de ponderar sobre seu grau de pertinência o sistema se torna hierárquico, com graus de importância entre as variáveis..

O sistema confirma as hipóteses levantadas de um sistema inteligente automatizar a decisão de importação do estoque local de segurança a técnica efetivamente gera um modificador da média considerando pontos que são específicos do local e que é integrado dentro de um processo maior de inventário, porém é capaz de criar uma base de segurança para reduzir os transtornos com falta ou excesso de itens no inventário global da empresa, reduzindo consideravelmente o tempo dispensado para a tarefa.

**Referências**

BORGES C. T.; CAMPOS S. M.; BORGES C. E. Implantação de um sistema para o controle de estoques em uma gráfica/editora de uma universidade. Revista Eletrônica Produção & Engenharia, v. 3, n. 1, p. 236-247, Jul./Dez. 2010.

BOTELHO, T. G. Uma nova proposta para implementação computacional do princípio de extensão de Zadeh. 2002. 77 p. Dissertação (Mestrado em Engenharia de Sistemas) - Universidade Federal de Lavras, Lavras, 2002

DIAS, M. A. P. Administração de materiais: uma abordagem logística. 5.São Paulo: ed. Atlas, 2010

HEATH & JACKSON _Modeling The Evolution Of Demand Forecasts Ith Application To Safety Stock Analysis In Production/Distribution Systems, IIE Transactions_, 26:3, 17-30, DOI: 10.1080/07408179408966604, 1994

GIGCH, J. ; PIPINO, L. Form Absolute to Probable to Fuzzy in Decision Making. Kybernetes, v. 19, p. 433-461, 1980.

LIKERT, R. (1932). _A technique for the measurement of attitudes. Archives of Psychology_, 22(140), 1-55. 

RUHOFF, A. L. et al. Lógica Fuzzy e zoneamento ambiental da Bacia do Arroio Grande. In: SIMPÓSIO BRASILEIRO DE SENSORIAMENTO REMOTO, 12., 2005, São Paulo. Anais… São Paulo: INPA, 2005. p. 2355-2362. 

SANJAY S & ADITYA M (2015) Safety stock calculations and inventory analysis: a practical approach for the FMCG case in a South-East Asian country, International Journal of Advanced Logistics, 4:3, 131-144, DOI: [10.1080/2287108X.2015.1103535](https://doi.org/10.1080/2287108X.2015.1103535)

SANJOY & SHAMS(2017) A quantitative and simulation model for managing sudden supply delay with fuzzy demand and safety stock, International Journal of Production Research, DOI: [10.1080/00207543.2017.1412528](https://doi.org/10.1080/00207543.2017.1412528)

SHAW, I. S.; SIMÕES, M. G. Controle e modelagem Fuzzy. São Paulo: E. Blücher, 1999. 165 p.

ZADEH, L. A. Fuzzy sets. Information and Control, New York, v. 8, p. 338- 353, 1965. 


<!-- GD2md-html version 1.0β13 -->

