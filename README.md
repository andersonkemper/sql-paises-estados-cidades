# SQL com Todos os Países + Todos os Estados e Cidades Brasileiras
SQL de Tabelas com Registros de Todos os Países e Nações (c/ Código BACEN) + Estados e Federações (c/ DDD e Código do IBGE) Brasileiros + Cidades e Municípios (c/ Código do IBGE) Brasileiros, incluindo as 31 regiões administrativas do DF, Ilhas e Áreas Remotas do Mundo.

*Arquivos separados por tipo de SGBD em Pastas.

*Arquivos separados por tabela.

*Em breve irei incluir estados e cidades estrangeiras.

## Validações

#### Validação do Código de Município

O Código de Município do IBGE tem a composição que segue:
- Composição: UUNNNND
Onde:
UU = Código da UF do IBGE
NNNN = Número de ordem dentro da UF;
D = Dígito de Controle módulo 10

Validação possível:
- Extensão máxima: 7 dígitos;
- Extensão mínima: 7 dígitos;
- Código da UF: deve ser válido, conforme Tabela de UF do IBGE;
- Número de ordem dentro da UF: não pode ser zero;
- Dígito de Controle: módulo 10 (pesos 2 e 1)

Obs 1: Considerar a soma dos algarismos no somatório dos produtos dos pesos. Ou seja, se o produto for superior a 9 os dois algarismos devem ser somados.

Obs 2: Se o resto da divisão for zero, considerar o dígito verificador igual a zero.

O código de Município do IBGE dos seguintes Municípios tem o DV - dígito verificador inválido:
- 4305871 - Coronel Barros/RS;
- 2201919 - Bom Princípio do Piauí/PI;
- 2202251 - Canavieira /PI;
- 2201988 - Brejo do Piauí/PI;
- 2611533 - Quixaba/PE;
- 3117836 - Cônego Marinho/MG;
- 3152131 - Ponto Chique/MG;
- 5203939 - Buriti de Goiás/GO;
- 5203962 - Buritinópolis/GO;

#### Validação do Código de País

Composição do Código de País:
- NNND
Onde:
NNN = Número de ordem do Código do País;
D = Dígito de Controle módulo 11.

Validação possível:
- Extensão máxima: 4 dígitos;
- Extensão mínima: 2 dígitos;
- Dígito de Controle: módulo 11, pesos 2 a 9

Obs.: Se o resto da divisão for zero ou 1, considerar o dígito verificador igual a zero.

O código de País do BACEN dos seguintes países tem o DV - dígito verificador inválido:
- 1504 - GUERNSEY, ILHA DO CANAL (INCLUI ALDERNEY E SARK);
- 1508 - JERSEY, ILHA DO CANAL;
- 4525 - MADEIRA, ILHA DA;
- 3595 - MAN, ILHA DE;
- 4985 - MONTENEGRO;
- 6781 - SAINT KITTS E NEVIS;
- 7370 - SERVIA;

## Dicas e Sugestões de Uso

*Todos os Estados/Distritos e Cidades/Municípios Brasileiros possui um código único de identificação do IBGE, porem nem todos os Países e Nações do mundo possui um código único de identificação do BACEN, devido o BACEN só catalogar Países dos quais ele possui ligação financeira (Agencias Bancarias ou Correspondente bancário), geralmente esses países (ou espaços governados por outras nações) são ilhas inabitadas ou regiões inabitadas próximas das Antártida, não se preocupe com isso, provavelmente sua aplicação nunca irá precisar utilizar essa localização. 

*A tabela de 'pais' possui todos os Países e Nações possíveis com ou sem Sigla, com ou sem Código do BACEN e com Nome Original e o Nome Traduzido para o Português.

## Contribuições

*Caso deseje contribuir adaptando o código sql para outro tipo de SGBD será sempre bem vindo.

## Changelog 
- 27/04/2016 Atualização do README e Commit das Alterações até a data.
- 27/04/2016 Criado um arquivo para CHANGELOG.
- 27/04/2016 Otimização de Colunas das Tabelas, removendo duplicidades, cidades fantasmas e espaço em branco no início e final dos nomes.
- 26/04/2016 Tradução dos Nomes de Países com referência do BACEN, Wikipédia e Google.
- 26/04/2016 Incluído o Código de Identificação Único das Cidades e Municípios com referência do IBGE (Instituto Brasileiro de Geografia e Estatística).
- 26/04/2016 Incluído o Código de Identificação Único dos Estados e Distritos com referência do IBGE (Instituto Brasileiro de Geografia e Estatística).
- 26/04/2016 Incluído o Código de Identificação Único dos Países com referência do BACEN (Banco Central do Brasil).
- 26/04/2016 Separado as tabelas por arquivo.
- 26/04/2016 Reorganizado os arquivos em pastas por tipo de SGBD.

###### v1.1.0

- 25/03/2016 Incluído a versão completa para MySQL por Chinnon Santos.

###### v1.0.0