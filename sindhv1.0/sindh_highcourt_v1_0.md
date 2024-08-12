This dataset is published under the project "[Pakistan Justice Data](../README.md)".

## Case Data Sindh High Court 2011 v1.0

The case-wise data was extracted in Summer 2023 from the [Sindh High Court website](htts://shc.gov.pk). The dataset contains information on cases filed in the Sindh High Court in 2011, including details on case type, case status, nature of cases, and case disposal.

### Collection Methodology

The data was extracted from the website using web scraping techniques. It was then cleaned and processed to make it usable for analysis. The following diagram provides an overview of the data collection methodology:

[Diagram to show data gahtering methodology](images/data_gathering.jpg)

### Data Repository

The dataset can be accessed at [https://doi.org/10.5281/zenodo.13152745](https://doi.org/10.5281/zenodo.13152745).

1. The data repository contains a CSV file named sindh_highcourt_2011.csv with the following columns:
    - `Case_Code` `(number)`: Unique identifier for each case in the case management system of the Sindh High Court.
    - `Case_Number` `(number)`: A number assigned to a case within a given year, aiding in case identification and organization. This can be used to search for a specific case on the court's website.
    - `Case_Year` `(number)`: The year in which the case was registered or submitted to the court.
    - `Case_Type` `(string)`: The type of legal case being referred to. Each entry in this column represents a distinct category of legal proceedings, indicating the nature of the judicial review or action being sought.
    - `Court` `(string)`: The court in which the case is being heard. This column specifies the judicial body responsible for adjudicating the case. The Sindh High Court has its principal seat in Karachi with benches and circuit courts in other cities.
    - `Description` `(string)`: A brief description of the case, providing context or background information on the legal matter at hand.
    - `FIR_Number` `(number)`: The First Information Report (FIR) number associated with the case, which is a unique identifier for criminal complaints filed with the police.
    - `FIR_Year` `(number)`: The year in which the FIR was registered.
    - `FIR_Location` `(character)`: The location  where the FIR was registered, which may indicate the police station or jurisdiction responsible for the investigation.
    - `Case_Status` `(character)`: The current status of the case, indicating the stage of proceedings or the outcome of the case.
    - `Last_Hearing_Date` `(character)`: The date of the most recent hearing in the case.
    - `Hearing_Stage` `(character)`: The current stage or status of the case as of the last hearing date, indicating its progress within the legal process.
    - `Disposal_Date` `(character)`: The date on which the case was disposed of or concluded, indicating the final resolution or outcome of the case.
    - `Description_of_Disposal` `(character)`: A description of how the case was resolved or disposed of, including any verdicts, judgments, or actions taken.
    - `Consigned_Date` `(character)`: The date on which the case was consigned to record, indicating the official archival or closure of the case.
2. The repository also contains `rules_for_discharge_status.R` which includes the rules used to clean the `Description_of_Disposal` column. You can read more about it [here](#case-disposals)

### Data Summary

The dataset contains information on 17,074 cases filed in the Sindh High Court in 2011, of which 15,841 (92.78%) cases are disposed of, 1,224 (7.17%) cases are pending, and 9 (0.05%) cases are adjourned without a future date (status 'Sine die').

The cases are distributed as follows:

- 12,584 (73.7%) cases are submitted to the Karachi court.
- 4,428 (25.93%) cases to the Larkana court.
- 13 (0.08%) cases to the Sukkur court.
- 12 (0.07%) cases to the Hyderabad court.
- 37 (0.22%) cases are submitted to the Appellate Tribunal In Land Revenue court.

#### Case Types

There are 59 unique values in the Case_Type column. The most common case types are:

- **Constitutional Petitions (Const. P.)**: 49.7% of the total cases.
- **Criminal Bail (Cr. Bail)**: 12.9% of the total cases.
- **Dispute Cases or Suits (Suit)**: 9.26% of the total cases.
- The remaining 56 types account for 28.08% of the cases.

#### Case Disposals

The `Description_of_Disposal` column describes the reasoning for case disposal, such as whether the case is dismissed, adjourned, or transferred to another court. Significant effort has been made to clean this data, as it was likely entered as free text. The rules to fix the values are defined in the code available in the [data repository](https://doi.org/10.5281/zenodo.13152745).

- The most common reason for disposal is "_main case disposed of_" which accounts for 20.63% (3,522) of the total cases.
- However, 29.01% of cases do not have any value for this attribute.
- Other common values are "_next waiting_" (18.23%), "_disposed of_" (9.42%) (different from "_main case disposed of_"), and "adjourned" (9.28%).

#### FIR Information

FIR information is available for 1,549 cases (9.07% of the total cases). Not all cases have FIR information, as not all cases are criminal cases. The extracted FIR details include `FIR Number`, `FIR Year`, and `FIR Location` (police station).

- 57.71% of FIRs are registered in 2011.
- 29.18% are registered in 2010.
- 4.97% are registered in 2009.
- The remaining 8.14% are registered in other years.
- The oldest FIR is registered in 1994.

#### Hearing Stage

This column describes the current stage of the case as of the last hearing date. The most common value is "For Katcha Peshi," which accounts for 27.12% of the cases. Katcha Peshi refers to an informal hearing within the legal proceedings of Pakistan's judiciary system. Unfortunately, 28.99% of cases do not have any value for this attribute.

### Data Validation

The data has been validated by comparing it with the original data available on the Sindh High Court website at <https://cases.shc.gov.pk/> using `Case_Number`, `Case_Year`, and `Case_Type`. You can validate the first row of the dataset by visiting the link [here](https://cases.shc.gov.pk/khi/web/index.php?r=cases%2Fsearch-result&CasesSearch%5BCASENO%5D=7&CasesSearch%5BCASEYEAR%5D=2011&CasesSearch%5BCASENAMECODE%5D=&CasesSearch%5BBENCH%5D=&CasesSearch%5BCIRCUITCODE%5D=&CasesSearch%5BMATTERCODE%5D=&CasesSearch%5BPARTY%5D=&CasesSearch%5BGOVT_AGENCY_CODE%5D=&CasesSearch%5BFIRNO%5D=&CasesSearch%5BFIRYEAR%5D=&CasesSearch%5BPOLICESTATIONCODE%5D=&CasesSearch%5BADVOCATECODE%5D=&CasesSearch%5BisPending%5D=&CasesSearch%5BisPending%5D=3&CasesSearch%5BCASENO%5D=13&CasesSearch%5BCASEYEAR%5D=2011&CasesSearch%5BCASENAMECODE%5D=&CasesSearch%5BBENCH%5D=&CasesSearch%5BCIRCUITCODE%5D=&CasesSearch%5BMATTERCODE%5D=&CasesSearch%5BPARTY%5D=&CasesSearch%5BGOVT_AGENCY_CODE%5D=&CasesSearch%5BADVOCATECODE%5D=&CasesSearch%5BFIRNO%5D=&CasesSearch%5BFIRYEAR%5D=&CasesSearch%5BPOLICESTATIONCODE%5D=&CasesSearch%5BisPending%5D=&CasesSearch%5BisPending%5D=3&CasesSearch%5BCASENO%5D=13&CasesSearch%5BCASEYEAR%5D=2011&CasesSearch%5BCASENAMECODE%5D=&CasesSearch%5BBENCH%5D=&CasesSearch%5BCIRCUITCODE%5D=4&CasesSearch%5BMATTERCODE%5D=&CasesSearch%5BPARTY%5D=&CasesSearch%5BGOVT_AGENCY_CODE%5D=&CasesSearch%5BADVOCATECODE%5D=&CasesSearch%5BFIRNO%5D=&CasesSearch%5BFIRYEAR%5D=&CasesSearch%5BPOLICESTATIONCODE%5D=&CasesSearch%5BisPending%5D=&CasesSearch%5BisPending%5D=3&CasesSearch%5BCASENO%5D=13&CasesSearch%5BCASEYEAR%5D=2011&CasesSearch%5BCASENAMECODE%5D=7&CasesSearch%5BBENCH%5D=&CasesSearch%5BCIRCUITCODE%5D=4&CasesSearch%5BMATTERCODE%5D=&CasesSearch%5BPARTY%5D=&CasesSearch%5BGOVT_AGENCY_CODE%5D=&CasesSearch%5BADVOCATECODE%5D=&CasesSearch%5BFIRNO%5D=&CasesSearch%5BFIRYEAR%5D=&CasesSearch%5BPOLICESTATIONCODE%5D=&CasesSearch%5BisPending%5D=&CasesSearch%5BisPending%5D=3)

### Status

In Progress

- To do: Labeling of data for further analysis

### License

The data is available under the [Creative Commons Attribution Non Commercial 4.0 International](https://creativecommons.org/licenses/by-nc/4.0/legalcode) license.

### Cite as

````(bibtex)
@dataset{pasta_2024_13152745,
  author       = {Pasta, Muhammad Qasim and
                  Azfar, Iqra and
                  Abidi, Rija Hasan and
                  Sheikh, Sahaab Badar},
  title        = {Case Data Sindh High Court 2011 v1.0},
  month        = aug,
  year         = 2024,
  publisher    = {Data Research Lab Pakistan},
  version      = {1.0},
  doi          = {10.5281/zenodo.13152745},
  url          = {https://darlab-pakistan.github.io/pakistan-justice-data/}
}
````

### Team Members

#### Principal Investigators (Corresoonding Members)

- [Muhammad Qasim Pasta](https://habib.edu.pk/SSE/muhammad-qasim-pasta/)
- [Sahaab Badar Sheikh](https://habib.edu.pk/AHSS/sahaab-sheikh/)

#### Student Researchers

- Iqra Azfar
- Syeda Rija Hasan Abidi

## Acknowledgements

We would like to thank [Habib University](http://habib.edu.pk) for providing funding for this part of the project under the grant [Summer Tehqiq (Research) Program 2023](https://habib.edu.pk/research-at-habib/summer-tehqiq-research-program/).
