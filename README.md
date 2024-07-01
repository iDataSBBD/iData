# Sobre
REPOSITÓRIO AUXILIAR DO ARTIGO _iData: uma Proposta para Modelagem e Persistência de Dados de Relacionamentos entre Objetos na SIoT_

## JSONS
> **ambiente_ona.json:** Exemplos de documentos referentes a ambientes ONA.
> **amizade_pagerank.json:** Exemplos de documentos referentes a amizades.
> **classe.json:** Exemplos de documentos referentes a classes de objeto.
> **interacao.json:** Exemplos de documentos referentes a interações.
> **objeto.json:** Exemplos de documentos referentes a objetos.
> **Namizades.json:** N documentos referentes a amizades.
> **Nobjetos.json:** N documentos referentes a objetos.

## Scripts
> **iDataPerformance.py:** Script que realiza inserção, leitura e exclusão de um volume massivo de documentos, permitindo identificar se o desempenho do sistema se mantém ou é degradado conforme a variação da quantidade de dados.
> **iDataBuscaAmizade.py:** Script que executa uma busca aprofundada em documentos que correspondem às amizades estabelecidas entre objetos, permitindo verificar a eficiência do banco de dados ao executar consultas mais específicas e com finalidade útil para a abordagem.

### Execução
> **iDataPerformance.py:** python .\iDataPerformance.py
> **iDataBuscaAmizade.py:** python .\iDataBuscaAmizade.py
Invocada a execução de algum destes scripts, deve-se informar uma instância do MongoDB local (**mongodb://localhost:27017/**) ou em nuvem.

## Figuras
> **iDataPerformance_metricas.png:** Apresenta as três principais métricas de interesse relativas à execução do script _iDataPerformance.py_. A taxa de inserção de registros no banco de dados atinge um aumento de, aproximadamente, 80 inserções por segundo a medida que a quantidade de documentos carregados cresce. A taxa média de consultas permanece em 0.08 consultas por segundo devido à invocação de apenas uma operação **read** para cada coleção, sendo linear independentemente do número de registros buscados. O gráfico relativo à rede está intrinsecamente ligado a infraestrutura que hospeda o banco de dados, assim, seu comportamento pode ser variável. Todavia, a taxa média de bytes enviadas do servidor ou ao servidor apresentam comportamento dentro do esperado, aumentando proporcionalmente às requisições.
> **iDataBuscaAmizade_metricas.png:** Apresenta as duas principais métricas de interesse relativas à execução do script _iDataBuscaAmizade.py_. Nos testes, foram considerados cenários com 10, 50, 100 e 1000 documentos. Com 10, 50 e 100 objetos, a taxa média de bytes enviados praticamente dobra de um para outro, atingindo cerca 400 bytes/s, enquanto a taxa média de consultas permanece baixa. Com 1000 documentos relativos a cada coleção, a taxa média de saída de bytes atinge mais de 290000 bytes/s, um aumento significativo devido as matrizes de adjacência substancialmente maiores. Contudo, a taxa média de consultas não sofre aumento expressivo, sendo necessárias apenas 6 consultas ao banco de dados para realização da busca.
> **iDataBuscaAmizade_saida.png:** Ilustra a saída do script _iDataBuscaAmizade.py_, apresentando os objetos envolvidos nas relações retornadas pela busca juntamente com o número de documentos considerado em cada iteração e o número de consultas necessárias para conclusão da busca desejada.