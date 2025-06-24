AVP PREDICTOR TOOL – USER GUIDE
===============================

Overview:
---------
This tool predicts whether a peptide sequence has antiviral activity (AVP)
and estimates its likelihood of inhibiting specific virus types.

It is based on deep learning (BiLSTM) models trained on curated antiviral peptide datasets.

Features:
---------
- Predicts AVP probability for input peptide sequences.
- If the peptide is likely antiviral (probability ≥ 0.5), the tool ranks 12 specific virus targets by their likelihood.
- Supports both single sequence and batch CSV input.
- Lightweight executable for Windows (no installation required).

Getting Started:
----------------
1. Download the `main.exe` file to your computer.
2. Press **Windows + R**, type `cmd`, and hit Enter to open the Command Prompt.
3. In the CMD window, navigate to the folder containing `main.exe`. 

For example:       cd C:\Users\duy\Downloads\peptide_predictor\

4. Run one of the following commands:

   - **Single sequence prediction:**

         main.exe KLWKKLLKKLLKAA

   - **Batch prediction from CSV:**

         main.exe --csv peptides.csv

     Your CSV file must include a column named `sequence`.

Output:
-------
- The terminal will display the AVP probability for each sequence.
- If AVP probability ≥ 0.5, the tool lists all virus types with predicted probability ≥ 0.5, sorted in descending order.
- For batch input, results are also saved as `outputs/predicted_output.csv` in the same folder.

Example Output (Terminal):
--------------------------
    AVP probability: 0.823  
    Likely virus targets (prob ≥ 0.5):
      DENV2     : 0.766
      SNV       : 0.661
      VACV      : 0.534

Example Output (CSV):
---------------------
| sequence        | avp_prob | DENV2 | SNV  | VACV | ... |
|-----------------|----------|-------|------|------|-----|
| KLWKKLLKKLLKAA  | 0.823    | 0.766 | 0.66 | 0.53 | ... |
| ...             | ...      | ...   | ...  | ...  | ... |

Virus Models:
-------------
Supported virus types (12):
- HCV, HSV1, DENV2, RSV, INFVA, SNV, HPIV3, FIV, SARS-CoV2, ANDV, VACV, HBV

Contact & Support:
------------------
- Lead Developer: Huynh Anh Duy
- Research Advisor: Tarapong Srisongkram
- Emails: haduy@ctu.edu.vn | tarasri@kku.ac.th

Version: 1.0  
Last updated: June 2025
