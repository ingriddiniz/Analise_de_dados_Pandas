# Análise de dados (Pandas)

Foi considerada a base de dados de casos COVID registados em animais, atualizada [neste repositório](https://github.com/amel-github/sars-ani), com uma cópia local [aqui](sars_ani_data.csv).

## Columns Dict 
  `ID` Unique identifier for each unique event of SARS-CoV-2 infection/exposure in animal(s).

`primary_source` Primary source of information to document the event. Possible pre-defined string values are: ProMED; WAHIS.

`archive_event_number` Unique identifier for the report, as provided by the primary source. Also corresponds to the name of the PDF file describing the event in the sars_ani_PDF_archives folder.

`link_web` Link to the online primary source to document the event.

secondary_source Secondary source of information to document the event. Possible pre-defined string values are: ProMED; WAHIS.

secondary_source_ID Unique identifier for the report, as provided by the secondary source. Also corresponds to the name of the PDF file describing the event in the sars_ani_PDF_archives folder.

secondary_source_web Link to the online secondary source for the event.

host_com_orig Most specific designation of the animal host provided by the source(s), in English.

host_sci_orig Scientific name of the animal host as mentioned in the source(s) (scientific names are harmonized so that only the first letter of the genus is capitalized).

host_com_res Common name of the animal host, harmonized against the National Center for Biotechnology Information (NCBI) taxonomic backbone.

host_sci_res Scientific name of the animal host (resolved to species or subspecies level), harmonized against the National Center for Biotechnology Information (NCBI) taxonomic backbone.

host_colloq The colloquial name of the host, i.e. the name commonly used to identify the animal in non-specialist language (e.g. “tiger” for “Sumatran tiger”).

host_sci_spec_res The scientific name of the host resolved to the species level.

family Animal family of the animal host.

epidemiological_unit The epidemiological unit considered to describe the event. Possible pre-defined string values are: animal = one individual; group = a group of animals housed/living together (excluding farm animals), e.g. zoo animals, pets; survey group = animals that have been sampled in different locations within the same surveillance programme or survey study; farm: a group of animals belonging to the same species and bred for commercial purposes.

number_cases Reported number of animal(s) tested positive for SARS-CoV-2 in the event.

number_susceptible Reported number of susceptible animal(s) of the same species in the event.

number_tested Reported number of animal(s) of the same species tested in the event.

number_deaths Reported number of direct and indirect death(s) related to the event. If death is not related to SARS-CoV-2 (see field outcome), number_deaths = 0.

age Age of the animal(s) when tested, in years.

sex Sex of the animal(s). Possible pre-defined values are: f = female; m = male.

country_iso3 Three-digit ISO country code for the country where the SARS-CoV-2 event was reported.

country_name Name of the country where the SARS-CoV-2 event was reported.

subnational_administration The subnational administrative region where the SARS-CoV-2 event was reported.

city The city where the SARS-CoV-2 event was reported.

location_detail Specification of the geographic location enabling to discriminate SARS-CoV-2 events occurring in the same species, at the same date and geolocation (subnational_administration, city), when the report(s) clearly stipulates that animal(s) were not geolocated at the same place (e.g. different farms or households).

date_confirmed When the SARS-CoV-2 infection or exposure was laboratory confirmed.

date_reported When the SARS-CoV-2 event was reported by the WAHIS.

date_published When the primary source published the SARS-CoV-2 event (date_published = date_reported when WAHIS is the primary source).

related_to_other_entries Relationship with another record (see field related_ID) in the dataset. Possible pre-defined string values are: new = the event is not related to any event previously entered in the dataset and no follow-up event exists but it can be related to an event that was reported on the same day or later in time with one of the following values: related_to_other_entries = living together or related_to_other_entries = connected or related_to_other_entries = same study; updated by = the event has a follow-up event in the dataset, which itself presents the value update of. Therefore, a new event gets the value updated by when a follow-up related event is entered; update of = the event is a follow-up of an event previously entered in the dataset; living together = the animal(s) described in the event share(s) the same geolocation (e.g. farm, household, pet store) as another (other) animal(s) that has/have been previously entered in the dataset; same study = the event reports infection in animal(s) belonging to a study that was previously entered in the dataset; connected = the event is epidemiologically related to a previously reported event in the dataset (e.g. SARS-CoV-2 events in pet hamsters in pet shops in Hong Kong, following a single importation of infected individuals from the Netherlands).

related_ID Unique identifier of the related entry in the dataset.

test First type of laboratory test performed to detect infection with (presence of the virus is evidenced) or exposure to (presence of antibodies is evidenced) SARS-CoV-2.

sampling_type Type of sample collected to perform the test (test).

test_2 Second type of laboratory test performed to detect infection with (presence of the virus is evidenced) or exposure to (presence of antibodies is evidenced) SARS-CoV-2.

sampling_type_2 Type of sample collected to perform the second test (test_2).

test_3 Third type of laboratory test performed to detect infection with (presence of the virus is evidenced) or exposure to (presence of antibodies is evidenced) SARS-CoV-2.

sampling_type_3 Type of sample collected to perform the third test (test_3).

negative_test First type of laboratory test mentioned in the report, which outcome was negative.

negative_sampling_type Type of sample collected to perform the first test (negative_test) that led to negative result.

negative_test_2 Second type of laboratory test mentioned in the report, which outcome was negative.

negative_sampling_type_2 Type of sample collected to perform the second test (negative_test_2) that led to negative result.

reason_for_testing Rationale for testing the animal(s).

symptoms Reported clinical signs allegedly associated to SARS-CoV-2.

outcome Issue of the SARS-CoV-2 infection (or exposure).

living_conditions How/where the animal(s) live(s).

source_of_infection Most probable source of SARS-CoV-2 infection.

variant SARS-CoV-2 genetic variant.

control_measures Main intervention(s) implemented to mitigate further spread of the virus.

original_source Information source cited by the primary source.

link_original_source Link to the online source cited by the primary source (when applicable).
  
Foram escritos programas Python que respondem às seguintes questões:

* Qual o número de casos reportados com cães?
  
  A função `casosCaes` retorna o número de casos.
  
* Qual o número de eventos reportados para espécies de felídeos (família *Felidae*)?
  
  A função `eventosFelideos` retorna uma lista de pares `(espécie,número_eventos)` por ordem decrescente de número de eventos.
   
* Por cada classe de animal (coluna `living_conditions`), qual o país com mais eventos de contacto com humanos (coluna `source_of_infection` igual a `human`)?
  
  A função `maisHumanos` retorna um dicionário `{ classe : país }`.
  
* Considerando apenas eventos com animais de quinta (coluna `living_conditions` igual a `farm`). Para países com pelo menos dois eventos publicados, qual a periodicidade média (em número de dias) em que novos casos foram publicados?
  
  A função `mediaQuintas` retorna um dicionário `{ país : periodicidade }`.
