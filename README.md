# MAC5778-sistemas-baseados-em-conhecimento
Repositório para o projeto

# Projeto
Projeto
Condições de conclusão
**Vencimento: domingo, 30 nov. 2025, 23:59**

O objetivo deste projeto é familiarizar vocês com as ferramentas para construção de ontologias e consultas.
O trabalho pode ser feito em grupos de até 4 alunos (Fórmula em lógica de descrição indicando que os grupos têm no máximo quatro integrantes.).

## Primeira fase

Vocês devem criar uma ontologia no Protégé para representar conceitos relevantes ao mundo do cinema. A ontologia deve conter no mínimo os conceitos Filme, Ator, Diretor e Personagem. Outros conceitos podem (e devem) ser criados conforme a necessidade, bem como relações (object properties e data properties). Exemplos de relações: Ator atua em Filme, Diretor dirige Filme e Filme tem ano de lançamento. Sua ontologia deve ter conceitos e propriedades suficientes para responder as questões de competência abaixo:

1. Quais os **títulos** dos filmes que foram dirigidos pelo diretor D, em ordem lexicográfica?
2. Quais os **primeiros nomes** e **últimos nomes** dos atores que participaram do filme de título Ft , em ordem lexicográfica de nome e sobrenome, com seus respectivos **personagens**?
3. Em quais **filmes** os atores X e Y atuaram juntos, com os respectivos **diretores** e **anos** de lançamento, do mais novo para o mais antigo?
4. Quais **filmes** do diretor do filme F possuem X ou Y como atores, com as respectivas **durações** em ordem crescente?
5. Quais **pessoas** atuaram em um **filme** e dirigiram algum **filme** (não necessariamente o mesmo filme, mas obrigatoriamente a mesma pessoa)?
6. Quais **diretores** dirigiram algum **filme** em um **ano** entre os anos N1 e N2 ,  em que os atores X e Y aparecem, do mais antigo para o mais novo?
7. Quais pares formados por uma **atriz** e um **ator<u/> atuaram juntos em algum **filme** de **duração** entre M1 e M2 ?
8. Qual o **diretor<u/> que mais dirigiu filmes em que aparece o ator de primeiro nome Xp e último nome Xu ?
9. Qual o **filme<u/> mais antigo em que o ator X atuou, em que **ano<u/> foi lançado e qual era seu **personagem<u/>? Havendo empate, devolver todos do mesmo ano.
10. Qual o **filme<u/> mais longo dirigido por D, e qual a sua **duração<u/>? Havendo empate, devolver todos da mesma duração.

Sua ontologia deve ser baseada nos conceitos e propriedades descritos pela ontologia FOAF (Friend of a Friend). A versão que deve ser usada está disponível em: http://xmlns.com/foaf/spec/index.rdf.  Por enquanto, usaremos a versão guardada em https://web.archive.org/web/20211024051123/http://xmlns.com/foaf/spec/index.rdf. Em particular, vocês devem utilizar todos os itens abaixo:

foaf:Person

foaf:familyName

foaf:firstName

foaf:made

foaf:maker

O conceito foaf:Person e as propriedades foaf:made e foaf:maker não devem ser instanciados diretamente; em vez disso, as instâncias devem utilizar subconceitos e subpropriedades de acordo com o tipo de indivíduo ou relação.
Além da FOAF, existem diversas outras ontologias disponíveis que podem servir de inspiração e cujos elementos podem ser referenciados na ontologia de vocês. Sintam-se à vontade para compartilhar ontologias públicas encontradas no fórum de discussões.

## Segunda fase


Nesta segunda etapa do projeto, vocês deverão usar o Plugin Cellfie com a planilha de dados sobre filmes disponibilizada. A ideia é criar as regras necessárias para popular as classes criadas na etapa anterior (Filme, Ator, Diretor e Personagem). 


## Terceira fase


A fase final do projeto consiste em fazer as consultas referentes às questões de competência em SPARQL. Nem sempre as consultas funcionam de dentro do Protégé. Fiquem à vontade para usar outras ferramentas para consultas. Minha sugestão é essa aqui, bem simples e funciona para o que precisamos: SPARQL GUI Wrapper

Não há suposição de que X e Y sejam distintos, e os termos “ator” e “diretor” nas perguntas abrangem quaisquer gêneros.

Os termos **sublinhados<u/> indicam as colunas que devem constar na resposta. As figuras abaixo exemplificam o formato esperado de saída das consultas.

Os parâmetros Ft , Xp e Xu das consultas 2 e 8 devem ser fornecidos como strings. Os parâmetros N1, N2, M1 e M2 das consultas 6 e 7 devem ser fornecidos como números inteiros. Os demais parâmetros (F , X, Y e D) devem ser os identificadores dos indivíduos na ontologia, preferencialmente prefixados (a fim de evitar a repetição do URI).

O que deve ser entregue

**Apenas um** membro de cada grupo deverá entregar, obrigatoriamente, três arquivos no eDisciplinas:
1. a ontologia em OWL na sintaxe RDF/XML (entreguem a **ontologia construída**, não a ontologia inferida pelo reasoner);
2. um arquivo de texto puro (TXT) com as consultas em SPARQL (apenas as queries, não os resultados) e as definições de todos os prefixos utilizados (linhas que começam com PREFIX);
3. um relatório em formato PDF contendo: a lista dos nomes de todos os integrantes do grupo, preferencialmente da forma como constam no eDisciplinas; descrições e comentários sobre os conceitos, propriedades e instâncias da ontologia; relação entre conceitos/propriedades da ontologia construída e das ontologias referenciadas (como a FOAF);  consultas feitas em SPARQL (com os respectivos resultados e os parâmetros utilizados).


Observações importantes:

• Vocês podem usar e criar quaisquer ferramentas para interpretar os dados recebidos e gerar a ontologia, contanto que a ontologia final esteja no formato OWL (sintaxe RDF/XML), contenha as entidades necessárias (conceitos, propriedades e todos os indivíduos) e possa ser aberta pelo Protégé. Projetos entregues sem algum dos três arquivos pedidos ou contendo uma ontologia em formato incompatível ou sem indivíduos não serão considerados.

• Ontologias externas devem ser referenciadas (em direct imports na aba principal do Protégé) e seu conteúdo não deve ser replicado na ontologia. Isto significa que a ontologia não deve ser criada editando o arquivo da FOAF e não pode ter o mesmo URI que a FOAF ou outra ontologia utilizada.

• Serão consideradas apenas as queries SPARQL que estiverem no arquivo TXT e cujos respectivos valores dos parâmetros e resultados estiverem no arquivo PDF. Os valores dos parâmetros devem ser escolhidos de modo que os resultados não sejam vazios. Opcionalmente, as queries podem também constar no arquivo PDF, mas é obrigatório que estejam no arquivo TXT. Consultas que utilizarem prefixos não declarados no arquivo TXT também não serão consideradas.

• As informações fornecidas no relatório não podem ser inconsistentes com o conteúdo da ontologia entregue: os conceitos, propriedades e indivíduos mencionados no relatório devem obrigatoriamente fazer parte da ontologia, e os resultados das consultas devem ser reprodutíveis.

• A entrega de todos os arquivos deve ser feita por apenas um integrante de cada grupo. 

Discussões no fórum são fortemente incentivadas!

<img width="1206" height="566" alt="Consulta" src="https://github.com/user-attachments/assets/4fcd349d-8349-4bf4-97aa-8b3b83aa17b6" />



