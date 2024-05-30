# Normalized Match Incrementality ![Version](https://img.shields.io/badge/python-3.10.12-blue)

Normalized Match Incrementality is a Python notebook to visualize and measure an incrementality test.

- Only basic coding skills required.
- Does not use advanced statistical methods so all steps can be validated.
- Focus on visual output so the results can be interpreted based on context.

## Instructions

### Data preparation

The data preparation part is currently not included, since the data can originate from many sources, but it follows these basic steps:

- Create A/B pairs that correlate based on _trend_ and not necessarily based on volume.
- Perform an intervention on the B group and run it for 4-6 weeks.

### Data format

The data format used for the notebook is very basic. Not that (usually) the `cost` is for the intervention and `response` is usually the total response (e.g. sessions or conversion value).

**Example data `head`:**

| date       | geo  | response    | cost     | pair | assignment | Region        |
| ---------- | ---- | ----------- | -------- | ---- | ---------- | ------------- |
| 2023-12-01 | 3.0  | 374.779999  | 0.0      | 3.0  | 2.0        | Friesland     |
| 2023-12-01 | 1.0  | 76.42       | 0.84     | 2.0  | 1.0        | Drenthe       |
| 2023-12-01 | 8.0  | 4432.929997 | 0.0      | 5.0  | 2.0        | North Holland |
| 2023-12-01 | 4.0  | 972.620001  | 0.0      | 4.0  | 2.0        | Gelderland    |
| 2023-12-01 | 10.0 | 2469.579999 | 12.42    | 5.0  | 1.0        | South Holland |
| 2023-12-01 | 11.0 | 1214.31     | 4.690252 | 4.0  | 1.0        | Utrecht       |
| 2023-12-01 | 6.0  | 69.96       | 0.0      | 2.0  | 2.0        | Limburg       |
| 2023-12-01 | 5.0  | 160.19      | 4.39     | 3.0  | 1.0        | Groningen     |
| 2023-12-01 | 2.0  | 174.31      | 0.0      | 1.0  | 2.0        | Flevoland     |
| 2023-12-02 | 8.0  | 2404.19     | 0.0      | 5.0  | 2.0        | North Holland |

### Notebook instructions

Firstly, upload the results csv into the same folder as the notebook.

The only part that needs to be configured is the config variable, which contains:

- `design_eval_start_date`: start of the period used for correlation
- `design_eval_end_date`: end of the period used for correlation
- `test_start_date`: start of the period for the intervention
- `test_end_date`: end of the period for the intervention
- `cooldown_end_date`: typically the last day of the dataset, otherwise the last day of the effects after stopping the intervention
- `pairs_include`: pairs that should be used for the analysis
- `file_name`: full name of the csv, no paths
- `response_name`: used for the visuals
