**Model name**

DBPM - Dynamic Benthic Pelagic Model

**Contacts**

Julia Blanchard - [julia.blanchard\@utas.edu.au](mailto:julia.blanchard@utas.edu.au)

Camilla Novaglio - [camilla.novaglio\@utas.edu.au](mailto:camilla.novaglio@utas.edu.au) 

Ryan Heneghan - [r.heneghan\@qut.edu.au](mailto:r.heneghan@qut.edu.au) 

**Spatial scale forcing**

[For example: scale: global or region, resolution: ¼ and 1 degree model runs]

We will be running the model at both ¼ and 1 degree resolution. Additionally we are calibrating the model at the LME scale, using the catch calibration time series provided on the ISIMIP server (data: Watson & Tidd).

**Levels of gear disaggregation**

[Which gears are used in the model, how was the effort aggregated or disaggregated?]

We will use the total effort in aggregated form, across gears. We are planning to model industrial and artisanal fleets separately.

**Spatial grid-cell allocation method**

[How was fishing effort allocated across grid-cells? Please provide equations as well as description]

To spatially allocate effort (E) at each time step (t) for each sector (s) within LMEs to grid-cells (g), we will spread effort out in proportion to the total biomass, in the previous time step (t-1), of each grid cell relative to the biomass summed across all grid cells for each LME (and above the minimum size selected, 10 grams?) :

\
$$Esgt=\frac{Bgt-1} {\sum$Bt-1} * Est$$

For the artisanal sector,  we additionally limit to the grid cells with depths of \< 100 or 200m [check gridded map of artisanal effort to work out what the max depth is, could do this by LME or just a single global max depth?], and excluding high seas LME = 0.

This gives us the total effort of each sector in each grid cell, within an LME.

To further allocate effort to each functional group in the model (see below), we similarly spread across functional groups within each grid cell as follows: \

E~fsgt~= $\frac{Bfgt-1 }{{\sum}Bgt-1 }* Esgt$

**Levels of functional group disaggregation**

[Which functional groups are used in the model, how was effort allocated across groups?]

Currently the model has two functionally distinct size spectra: Benthic (seafloor, primarily detritivores)  and Pelagic (water column, all size-based predators, including demersal fish that feed on animals in the Benthic size spectrum). 

We plan to distribute effort across these groups as a proportion of their relative total biomass (see above equation).

**Fishing mortality rate equation**

[How are fishing mortality and catch rates calculated in your model? Please provide equations as well as description]

The instantaneous fishing mortality rate (calculated within each grid cell of each  LME) is calculated as:

F~m,f,s,g,t~=Q~fst~\* Sel~mf~\* E~fsgt~

Where Qfst = creep (% annual rate of increase of each sector) is applied to the catchability_coefficient (per unit effort previous year, t-1, for each functional group and sector) and assuming both creep and catchability_coefficient in the initial year are tuning parameters.

Initially, we do not assume changes in catchability through time  Qst depend on the changes in the biomasses of the functional groups, but this may be explored in our calibration.

**Selectivity (size,age,species)**

[If you have a selectivity term please describe it, with equation]

Since we aggregate across meany gear types, we assume a knife-edge weight-based selectivity, where a different minimum weight fished, wsel,  is based on minimum sizes caught for each functional group:

Sel~mf~ $\geq$ 1 w~sel~, else 0

**Model calibration**

[Catchability terms can be used to calibrate the model to catches, using data ONLY UP TO 2004. Please state how you estimate these parameters and the metrics and criteria you use to calibrate your model. Please provide details and equations]

We plan to calibrate

**Catchability and Creep (yearly rate of change catchability) Estimates**

[Please provide details on the specific estimated parameters from the calibration, e.g. range of creep of 2-5% per year; and catchability coefficients per gear / functional group as necessary]

N/A\

**Further details on calibration**

[Have you used other metrics or data in your calibration?]

N/A\

**Statistical metrics**

[Please provide detail on the statistical method used in your calibration - E.g. optimisation, error terms]

**Statistical results (summary)**

[Please provide a summary of the metrics and results associated with your model calibration - E.g. RMSE with observed catches and any other process-based or theoretical criteria used to calibrate the model, comparison of modelled biomass, growth rates, P"B ratios etc]

N/A

**Model changes or  improvements(s) made as a result of calibration**

[Please provide detail of any other parameters or model changes since the last round as a result of this calibration]

N/A\
**ADDITIONAL DETAILS FOR REGIONAL MODELS ONLY:**

**Downscaling method**

[Please describe further details how the LME level fishing effort was downscaled to your region, providing further information on what data, if any were used, E.g. ]

N/A

**The "base" year range of the regional model**

N/A\
[If you expressed effort relative to the effort in your base model, which year was the base year and how was this done]\
