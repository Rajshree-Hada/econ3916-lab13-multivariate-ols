# econ3916-lab13-multivariate-ols

# Multivariate OLS: What "Controlling For" Actually Does

## Objective
I used simulated data to show when adding a control variable fixes a regression, when it breaks one, and when it does neither.

## Methodology
- Simulated wages with an unobserved ability term, then ran the regression with and without ability.
- Checked the omitted-variable-bias formula (the effect of ability on wage times the slope of ability on education) against the bias I measured.
- Ran the Frisch-Waugh-Lovell two-step: removed ability's influence from both wages and education, then regressed one residual on the other, and compared the result with the full regression.
- Simulated a collider and compared the regression with and without it as a control.
- Fitted two highly correlated regressors and looked at their variance inflation factors, standard errors, and joint F-test.
- Fitted an interaction between experience and union membership and read the return to experience for each group from the coefficients.
- Asked an AI to write a specification-table function, revised my prompt once, and checked the function's coefficients against my own regressions.

## Key Findings
- Leaving ability out gave a return to education of 5,126 against a true 2,500. Putting ability in gave 2,546.
- The bias formula predicted a bias of 2,629, and the actual bias was 2,626.
- The Frisch-Waugh-Lovell two-step gave the same coefficient as the full regression, 2,546.4985.
- Controlling for a collider turned a true effect of zero into an estimate of -0.596, with a p-value that printed as 0.000.
- Multicollinearity made the standard errors about 12 times larger, but the estimates stayed on target: the two coefficients summed to 5.009 against a true 5.
- A year of experience was worth 903 to non-union workers and 504 to union members.
- The AI's table function matched my own regressions on the coefficients once I ran it on the lab's data.
