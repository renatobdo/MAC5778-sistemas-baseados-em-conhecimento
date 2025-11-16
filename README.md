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
7. Quais pares formados por uma **atriz** e um **ator** atuaram juntos em algum **filme** de **duração** entre M1 e M2 ?
8. Qual o **diretor** que mais dirigiu filmes em que aparece o ator de primeiro nome Xp e último nome Xu ?
9. Qual o **filme** mais antigo em que o ator X atuou, em que **ano** foi lançado e qual era seu **personagem**? Havendo empate, devolver todos do mesmo ano.
10. Qual o **filme** mais longo dirigido por D, e qual a sua **duração**? Havendo empate, devolver todos da mesma duração.

Sua ontologia deve ser baseada nos conceitos e propriedades descritos pela ontologia FOAF (Friend of a Friend). A versão que deve ser usada está disponível em: http://xmlns.com/foaf/spec/index.rdf.  Por enquanto, usaremos a versão guardada em https://web.archive.org/web/20211024051123/http://xmlns.com/foaf/spec/index.rdf. Em particular, vocês devem utilizar todos os itens abaixo:

foaf:Person

foaf:familyName

foaf:firstName

foaf:made

foaf:maker

O conceito foaf:Person e as propriedades foaf:made e foaf:maker não devem ser instanciados diretamente; em vez disso, as instâncias devem utilizar subconceitos e subpropriedades de acordo com o tipo de indivíduo ou relação.
Além da FOAF, existem diversas outras ontologias disponíveis que podem servir de inspiração e cujos elementos podem ser referenciados na ontologia de vocês. Sintam-se à vontade para compartilhar ontologias públicas encontradas no fórum de discussões.

## Print com a ontologia

<img width="1366" height="768" alt="Ontologia_Filmes" src="https://github.com/user-attachments/assets/a66a31e8-2a5f-4536-aa62-c4a8be15d46e" />

<img width="1366" height="768" alt="Ontologia_Filmes_OP" src="https://github.com/user-attachments/assets/69291418-70f8-4cbf-94e9-45066b6117b0" />


<img width="1366" height="768" alt="Ontologia_Filmes_OP2" src="https://github.com/user-attachments/assets/7e02387f-cbc8-4b85-8015-e6af0d4ce4c1" />


<img width="1366" height="768" alt="Ontologia_Filmes_DP" src="https://github.com/user-attachments/assets/ae7da5b0-43b5-4267-9a13-9c2c709af425" />


## Segunda fase


Nesta segunda etapa do projeto, vocês deverão usar o Plugin [Cellfie](https://github.com/protegeproject/cellfie-plugin) com a planilha de dados sobre [filmes](https://github.com/renatobdo/MAC5778-sistemas-baseados-em-conhecimento/blob/main/filmes.xlsx) disponibilizada. A ideia é criar as regras necessárias para popular as classes criadas na etapa anterior (Filme, Ator, Diretor e Personagem). 

## Regra de transformação para os filmes:
<img width="1366" height="768" alt="Ontologia_Filmes_TR" src="https://github.com/user-attachments/assets/41e53d8e-3086-4da8-a774-f3ee1360cd8b" />


<img width="1366" height="768" alt="Ontologia_Filmes_FilmesIndividuals" src="https://github.com/user-attachments/assets/98250390-2c98-4047-98d1-2ca0da3106f0" />


<img width="1366" height="768" alt="Ontologia_Filmes_TR2_diretores" src="https://github.com/user-attachments/assets/b1618fef-d060-4496-87f5-588e83e8f00b" />


<img width="1366" height="768" alt="Ontologia_Filmes_TR3_atores" src="https://github.com/user-attachments/assets/1f39fe75-4c1c-4647-ad94-ba88d6eec3d1" />

<img width="1366" height="768" alt="Ontologia_Filmes_TR3_atrizes" src="https://github.com/user-attachments/assets/cf268c06-4173-426d-b450-59f6b4ead259" />






## Terceira fase


A fase final do projeto consiste em fazer as consultas referentes às questões de competência em SPARQL. Nem sempre as consultas funcionam de dentro do Protégé. Fiquem à vontade para usar outras ferramentas para consultas. Minha sugestão é essa aqui, bem simples e funciona para o que precisamos: [SPARQL GUI Wrapper](https://github.com/viniciusbm/sparqlguiwrapper)

Não há suposição de que X e Y sejam distintos, e os termos “ator” e “diretor” nas perguntas abrangem quaisquer gêneros.

Os termos **sublinhados** indicam as colunas que devem constar na resposta. As figuras abaixo exemplificam o formato esperado de saída das consultas.

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

Rodar o servidor apache jena:

<img width="963" height="116" alt="ApacheJenaServer" src="https://github.com/user-attachments/assets/edd4a9bd-9aeb-4ef4-a842-1b08ef578ee6" />



<img width="1206" height="566" alt="Consulta" src="https://github.com/user-attachments/assets/4fcd349d-8349-4bf4-97aa-8b3b83aa17b6" />

**Queries**

1. Quais os **títulos** dos filmes que foram dirigidos pelo diretor D, em ordem lexicográfica?
```
SELECT ?titulo
WHERE {
  BIND(:diretor_sofia_coppola AS ?D) 
  ?f :temDiretor ?D ;
     :titulo ?titulo .
}
ORDER BY STR(?titulo)
```

2. Quais os **primeiros nomes** e **últimos nomes** dos atores que participaram do filme de título Ft , em ordem lexicográfica de nome e sobrenome, com seus respectivos **personagens**?

```
SELECT DISTINCT ?firstName ?familyName ?personagem
WHERE {
  BIND("Lost in Translation" AS ?Ft) 
  ?f a :Filme ; :titulo ?Ft .

  { ?p :atuaEm ?f } UNION { ?f :temElenco ?p }
  ?p foaf:firstName ?firstName ; foaf:familyName ?familyName .

  OPTIONAL {
    ?ch a :Personagem ; :interpretadoPor ?p ; :apareceEm ?f ;
        :nomePersonagem ?personagem .
  }
}
ORDER BY STR(?firstName) STR(?familyName)
```




