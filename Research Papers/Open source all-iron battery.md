# Open source all-iron battery
## Hardware in context
### Past batteries
- iron chemistries in flow batteries(?)
	- flow batteries: "use solutions of redox-active materials pumped through an electrochemical cell"
- all-iron soluble flow battery [](https://pubs.acs.org/doi/10.1021/acsenergylett.6b00049)
- flow battery w/ iron powder slurry anode [](https://www.sciencedirect.com/science/article/abs/pii/S0378775315010848)
- flow battery for of grid usage [](https://chemistry-europe.onlinelibrary.wiley.com/doi/abs/10.1002/cssc.201500845)
- non-reversible iron battery made from sraps [](https://pubs.acs.org/doi/10.1021/acsenergylett.6b00295)
- more disposable iron battery for "low resource" setting [](https://iopscience.iop.org/article/10.1149/MA2016-02/1/37/meta)


### this battery
![[Pasted image 20210127223458.png]]
iron metal anode and an iron (III) sulfate cathode, aqueous chemistry

## Hardware description
Anode: steel wool
Cathod: precipitated ferric iron salt (?)
### Simple explanation
Anode: Fe -> $Fe^{2+} + 2e^{-}$
Cathode: $e^{-}+Fe^{3+} \rightarrow Fe^{2+}$

### (a possible) Complexer explanation
Anode (0.45V): Fe -> $Fe^{2+} + 2e^{-}$
Cathode(0.16V): $Fe_{2}0_{3}+2e^{-}+4H^{+} \rightarrow FeOH^{+}+H_{2}O$
netting a 0.61V

### Iron sulfate salt chemistry
- "Iron chloride was mixed with a saturated potassium sulfate solution and then pH was adjusted"
	- created a "precipitate" (???)
	- sulfate "precursor" (?) had the best available coulombic capacity

- Iron (II) chloride was used to produce the **anode** electrolyte 
	-	electrolyte: produces an electrically conducting solution when dissolved in a polar solvent
- Iron (III) chloride was used as the **cathode** electrolyte
- iron (II) is always present which the author claims prevents irreversible loss of the iron

### Sodium polyacrylate membrane
- galvanic cells (what are separator membranes?) are what seperates the anode and the cathode (?)
	- aims to keep balance by passing ions but not allowing discharge
	- also tries to prevent cross-contamination but that doesn't matter since all iron
		- "the diffusion of the iron species through the membrane does discharge the cell", so wait does it or doesn't it matter
- sodium polyacrylate was best cost vs preformance vs saftey

### carbon-felt electrode
needed to interface between the reaction and the load (an interface appears to be needed to reduce corrosion... maybe more reasons?)

### possible application
"where weight is less important, cheaper and safer chemistry may be preferred"
- open source wind turbines, charge controllers
- might be better for power data loggers or remote cameras