# Análise de dados (Pandas)

Foi considerada a base de dados de casos COVID registados em animais, atualizada [neste repositório](https://github.com/amel-github/sars-ani), com uma cópia local [aqui](sars_ani_data.csv).

`sars_ani_data.csv` contém os dados brutos do conjunto de dados SARS-ANI, que apresenta informações estruturadas sobre Eventos SARS-CoV-2 em animais (formato .csv, UTF-8 codificado).

## Field dictionary 
Estas foram as colunas utilizadas neste projeto, para mais informações sobre outras colunas contidas neste dataset, é aconselhavel a consulta no repositório de onde os dados foram extraidos. 

`host_com_orig` Most specific designation of the animal host provided by the source(s), in English.

`host_colloq` The colloquial name of the host, i.e. the name commonly used to identify the animal in non-specialist language (e.g. “tiger” for “Sumatran tiger”).

`family` Animal family of the animal host.

`number_cases` Reported number of animal(s) tested positive for SARS-CoV-2 in the event.

`country_name` Name of the country where the SARS-CoV-2 event was reported.

`living_conditions` How/where the animal(s) live(s).

`source_of_infection` Most probable source of SARS-CoV-2 infection.

#### Nota

Foram considerados os dois seguintes valores em todo o conjunto de dados:

- `NS` Não especificado: a informação seria relevante para o evento, mas a informação não foi mencionada no primário ou fonte secundária.
- `NA` Não aplicável: o campo não é aplicável neste caso
    
## Funções  
  
Foram escritos programas Python que respondem às seguintes questões:

* Qual o número de casos reportados com cães?
  
  A função `casosCaes` retorna o número de casos.
  
* Qual o número de eventos reportados para espécies de felídeos (família *Felidae*)?
  
  A função `eventosFelideos` retorna uma lista de pares `(espécie,número_eventos)` por ordem decrescente de número de eventos.
   
* Por cada classe de animal (coluna `living_conditions`), qual o país com mais eventos de contacto com humanos (coluna `source_of_infection` igual a `human`)?
  
  A função `maisHumanos` retorna um dicionário `{ classe : país }`.
  
* Considerando apenas eventos com animais de quinta (coluna `living_conditions` igual a `farm`). Para países com pelo menos dois eventos publicados, qual a periodicidade média (em número de dias) em que novos casos foram publicados?
  
  A função `mediaQuintas` retorna um dicionário `{ país : periodicidade }`.
