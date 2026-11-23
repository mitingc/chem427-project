# Judgment log: Olivia Chuang

## How I used AI in this project


## Entry 1: Reference Averaging

**What the assistant suggested:** The assistant initially used column-specific averaging for the dark and white references to account for differences between detector columns.

**What I did:** I asked the assistant to compare column-specific averaging with global averaging. After reviewing the results, I decided to keep column-specific averaging because it better accounts for differences in detector sensitivity.

**Why, from my data:** In the notebook's "Check: column-specific against global reference averaging" section, the main ratio difference changed from 0.1116 with global averaging to 0.1093 with column-specific averaging. The control difference decreased from 0.0367 to 0.0254, while the right-region reflectance at 1300 nm changed from 0.7571 to 0.7180. The white-minus-dark reference also varied by 4.5% across columns at 1300 nm. Although the main ratio difference changed very little, the other measurements were more affected, supporting the use of column-specific averaging.

## Entry 2: Wavelength Selection

**What the assistant suggested:** The assistant suggested restricting the analysis to 1000–2500 nm to exclude wavelengths with weak reference signals.

**What I did:** I accepted this wavelength range after examining the white-minus-dark reference signals and confirming that the lower wavelengths had weaker signals.

**Why, from my data:** Twelve bands between 896 and 959 nm had white-minus-dark signals below 1,000 counts. Since reflectance is calculated by dividing by the white-minus-dark signal, low values can amplify noise and make the results less reliable. Keeping 268 of the 288 bands allowed me to focus on the documented camera range while excluding potentially unreliable measurements.