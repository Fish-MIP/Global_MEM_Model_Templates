# Model name

ZooMSS - Zooplankton Model of Size Spectra

# Contacts

Primary contact: Jason Everett - Jason.Everett@uq.edu.au
Secondary contact: Kieran Murphy - kieran.murphy@uq.edu.au
Other: Anthony Richardson - a.richardson1@uq.edu.au
Other: Ryan Heneghan - r.heneghan@griffith.edu.au

# Model ecology overview

The Zooplankton Model of Size Spectrum (ZooMSS) is a dynamic size-spectrum model that represents the marine ecosystem as a static phytoplankton community, nine dynamic zooplankton groups and three fish groups. Energy moves from small to large size classes through the size-dependent process of predation-fuelled growth. Energy is lost from the system due to inefficiencies in predators converting prey biomass into new predator biomass, and mortality. 

ZooMSS resolves phytoplankton, two microzooplankton groups (heterotrophic flagellates and ciliates), seven mesozooplankton and macrozooplankton groups (omnivorous and carnivorous copepods, larvaceans, euphausiids, salps, chaetognaths and jellyfish) and three size-based fish groups (broadly representing small pelagic fish (SPF) ≤100 g; medium pelagic fish 100 g ≤ 10 kg and large pelagic fish 10 kg ≤ 1 t). ZooMSS resolves the nine zooplankton groups on the basis of several traits: the size range of the group, feeding characteristics (PPMR and feeding kernel width) and carbon content. Other than their asymptotic size, the three fish groups share the same functional traits (feeding characteristics and carbon content), which are unique from the zooplankton groups.

Zooplankton and fish growth at any size class is driven by the density of smaller organisms within their preferred prey size range. For predators, growth conversion efficiency—the proportion of consumed food converted into new wet weight biomass—is affected by the carbon content of their prey. Prey groups with larger carbon contents (for example, copepods) contribute more to the growth of their predators when they are consumed than other groups with less carbon (for example, jellyfish). From the perspective of the prey, total predation from larger size classes is the primary source of mortality. Since individuals grow and age over time, senescence mortality is also included, which increases with body size.

# Spatial scale forcing

We will be running the model at both 0.25°  and 1° resolution.

# Levels of gear disaggregation

We will use the total effort in aggregated form, across gears. We are planning to model industrial and artisanal fleets separately.

# Levels of functional group disaggregation

ZooMSS has a single pelagic size spectra comprised of zooplankton and three size-based fish groups (broadly representing small pelagic fish (SPF) ≤100 g; medium pelagic fish 100 g ≤ 10 kg and large pelagic fish 10 kg ≤ 1 t).

# Spatial grid-cell allocation method

To spatially allocate effort (E) at each time step (t) for each sector (s) within LMEs to grid-cells (g), we will spread effort out in proportion to the total biomass, in the previous time step (t-1), of each grid cell relative to the biomass summed across all grid cells for each LME (and above the minimum size selected, 10 grams?):

$$E_{sgt} = \frac{B_{gt-1}} {\sum B_{t-1}} * E_{st}$$

For the artisanal sector,  we additionally limit to the grid cells with depths of < 100 or 200m (check gridded map of artisanal effort to work out what the max depth is, could do this by LME or just a single global max depth?), and excluding high seas LME = 0.

This gives us the total effort of each sector in each grid cell, within an LME.

To further allocate effort to each functional group in the model (see below), we similarly spread across functional groups within each grid cell as follows:

$$ E_{fsgt} = \frac{B_{fgt-1}} {\sum B_{gt-1}} * E_{sgt} $$

# Fishing mortality rate equation

Fish mortality is currently not implemented in the model but we are currently working on including it. We expect this to be completed shortly. The details below reflect what is planned for incorporation.

The instantaneous fishing mortality rate (calculated within each grid cell of each  LME) is calculated as:

$$ F_{m,f,s,g,t} = Q_{fst} * Sel_{mf} * E_{fsgt} $$

Where $Q_{fst}$ = creep (% annual rate of increase of each sector) is applied to the catchability_coefficient (per unit effort previous year, t-1, for each functional group and sector) and assuming both creep and catchability_coefficient in the initial year are tuning parameters.

Initially, we do not assume changes in catchability through time $`Q_{fst}`$ depend on the changes in the biomasses of the functional groups, but this may be explored in our calibration.

# Selectivity (size, age, species)

Since we aggregate across meany gear types, we assume a knife-edge weight-based selectivity, where a different minimum weight fished, $w_{sel}$, is based on minimum sizes caught for each functional group:

$$ Sel_{mf} \geq 1 w_{sel}, else 0 $$

# Model calibration

We plan to calibrate.

# Catchability and creep (yearly rate of change catchability) estimates

N/A

# Further details on calibration

N/A

# Statistical metrics

N/A

# Statistical results (summary)

N/A

# Model changes or improvements made as a result of calibration

N/A
