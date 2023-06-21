# Análise de dados (Pandas)

Foi considerada a base de dados de casos COVID registados em animais, atualizada [neste repositório](https://github.com/amel-github/sars-ani), com uma cópia local [aqui](sars_ani_data.csv).

Foram escritos programas Python que respondem às seguintes questões:

* Qual o número de casos reportados com cães?
A função `casosCaes` retorna o número de casos.
  
* Qual o número de eventos reportados para espécies de felídeos (família *Felidae*)?
A função `eventosFelideos` retorna uma lista de pares `(espécie,número_eventos)` por ordem decrescente de número de eventos.
   
* Por cada classe de animal (coluna `living_conditions`), qual o país com mais eventos de contacto com humanos (coluna `source_of_infection` igual a `human`)?
A função `maisHumanos` retorna um dicionário `{ classe : país }`.
  
* Considerando apenas eventos com animais de quinta (coluna `living_conditions` igual a `farm`). Para países com pelo menos dois eventos publicados, qual a periodicidade média (em número de dias) em que novos casos foram publicados?
A função `mediaQuintas` retorna um dicionário `{ país : periodicidade }`.
