Download Link: https://assignmentchef.com/product/solved-economics7103-hw9
<br>
This assignment builds upon the data from homework assignments 4-6.

You have imaginary data on the monthly yields for Pacific fish trawling companies. An environmental nonprofit targeted these firms and implemented a program designed to reduce bycatch. As part of the program, the nonprofit contacted firm managers and provided information about best practices to reduce bycatch. The program was implemented in two phases. In January 2018, the nonprofit contacted half of the firms. The next year in January 2019, the nonprofit contacted the remaining firms.

Previously you had access to the data from 2017-2018. You now have an updated dataset with data from 2019 as well. This data is called fishbycatchupdated.csv.

You are interested in whether the program worked or not and decide to use this panel data to empirically estimate the effect of the program. You now realize that you have a staggered adoption design and that to incorporate the new data you will have to use something different than the standard two-way fixed effects approach. You have the following data:

<table width="492">

 <tbody>

  <tr>

   <td width="67">Variable</td>

   <td width="425">Description</td>

  </tr>

  <tr>

   <td width="67"><em>firm</em></td>

   <td width="425">Firm identification number</td>

  </tr>

  <tr>

   <td width="67"><em>shrimp*</em></td>

   <td width="425">Pounds of shrimp in month *</td>

  </tr>

  <tr>

   <td width="67"><em>salmon*</em></td>

   <td width="425">Pounds of salmon in month *</td>

  </tr>

  <tr>

   <td width="67"><em>bycatch*</em></td>

   <td width="425">Pounds of bycatch in month *</td>

  </tr>

  <tr>

   <td width="67"><em>firmsize</em></td>

   <td width="425">Size of fishing fleet</td>

  </tr>

  <tr>

   <td width="67"><em>treated</em></td>

   <td width="425">=1 if firm received information treatment in January 2018 (month 13)=0 if firm received information treatment in January 2019 (month 25)</td>

  </tr>

 </tbody>

</table>

Table 1: Variable descriptions for homework 5.

Use Stata/MP 16 on the IAC VLab (<a href="https://it.iac.gatech.edu/services/vlab">https://it.iac.gatech.edu/services/vlab</a><a href="https://it.iac.gatech.edu/services/vlab">)</a>. Instead of turning in a Python script, you will turn in a .do file that generates your output. Note that to convert these panel data from wide to long form, you can use the Stata command reshape.

<ol>

 <li>Visually inspect the bycatch by treatment group as the treatment rolled out to each group over time.Do this by creating a line plot for months in 2017, 2018, and 2019. (Hint: Use twoway line in Stata).</li>

 <li>Using Stata’s xtreg, fe command, estimate the following two-way fixed effects regression (using the pre-coded within-estimator):</li>

</ol>

<em>bycatch</em><em>i,t </em>= <em>c</em><em>i </em>+ <em>λ</em><em>t </em>+ <em>δtreat</em><em>i,t </em>+ <em>βX</em><em>i,t </em>+ <em>u</em><em>i,t.</em>

Cluster the standard errors at the firm level using the command’s built-in standard errors. Report the coefficient estimates <em>δ</em><sup>ˆ </sup>and <em>β</em><sup>ˆ </sup>and clustered standard errors in a nicely-formatted LaTeX table using the Stata command outreg2.

<ol start="3">

 <li>Using Stata’s reghdfe command, estimate the same two-way fixed effects regression by absorbing the firm and month indicator variables. Cluster the standard errors on both firm and month. Report the coefficient estimates <em>δ</em><sup>ˆ </sup>and <em>β</em><sup>ˆ </sup>and two-way clustered standard errors in the same table as your results from 2. (Note that this command is INCREDIBLY fast with very large datasets with many indicator variables. In this small dataset it is slower than a standard FE regression).</li>

</ol>

1

<ol start="4">

 <li>Intuitively, what is the problem with the two-way fixed effects regressions specified above? Make references to the papers from class in your answers.</li>

 <li>Install and use the command twowayfeweights from de Chaisemartin and D’Haultfoeuille, 2020 to estimate how many of the TWFE weights are negative. Report the number of negative weights.</li>

 <li>Install and use the command did_multiplegt from de Chaisemartin and D’Haultfoeuille, 2020 to estimate the <em>DID<sub>M </sub></em> Use 50 bootstrap replications for the standard errors and use the cluster bootstrap at the firm level. Report the coefficient estimates <em>δ</em><sup>ˆ </sup>and <em>β</em><sup>ˆ </sup>and two-way clustered standard errors in the same table as your results from 2 and 3.</li>

 <li>Drop the months from 2019 and recalculate how many TWFE weights are negative. What has changedand why?</li>

</ol>