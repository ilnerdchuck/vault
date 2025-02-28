---
id: 1740669411-technology-scaling-ts
aliases:
  - Technology scaling (TS)
tags: []
title: Technology scaling (TS)
---


As the technology is based on [[1740672093-nmos|NMOS]] transistors the trend is to place as many fast switching transistors as possible in a given area (Integration Density). 
To achieve it we can analyze the [[1740672093-nmos|NMOS]] switching capabilities which are measured in the time to rise $t_r$(Time for a signal to become HIGH)
$t_r = \frac{C_l}{I_{ON}}$ and the 
$$
I_D = \mu_n C_{\text{ox}} \frac{W}{L} \left( (V_{GS} - V_{\text{th}}) V_{DS} - \frac{V_{DS}^2}{2} \right)
$$
> [!IMPORTANT]
> Thus to reduce the size of the transistor size while increasing the performance we decrease the channel length $L$ of the NMOS 
> (Ex. TMSC production nodes 4nm)

> [!CHECK] Pros 
> - Lowering the size of the transistor brings => **Higher Integration Density** $\frac{mm^2}{nTr = \text{Number of Transistors}}$
> - Lowering the size of the transistor brings => **Faster Switching Speeds**: reduced time to rise

> [!FAILURE] Cons
> - **Fabrication Cost** increases $\frac{Money}{mm^2}$ => but it is balanced by the Higher Integration Density $\frac{mm^2}{nTr} \times \frac{Money}{mm^2} = \frac{Money}{nTr}$
> - **Power consumption** => switching produces power, more transistor more power consumption (P=VI)
>    - Higher power consumption means more energy needed => as designers we want less   
> - $\text{Power Density} = \frac{Power}{Area}$ increases more than power itself => more heat **Temperature**    
>    - **Thermal issue** => Now a solution to remove heat is needed 
> - **Process Variation** => Usually the channel length in a production node is not the same between NMOS, usually the manufacturer claims an average value of the channel length Ex: 4nm is the peak of a distribution that can vary from \[2nm,6nm\]
>    - The higher length ones have a slow time to rise => **Slow Performance**  
>    - The smaller have narrower channels so they are faster and increase the power consumption
> - [[1740674446-aging|Aging]] could be an issue

# References 
- [[1740671482-bulk-cmos|Bulk CMOS]]
- [[1740671504-fd-soi|FD-SOI]]

