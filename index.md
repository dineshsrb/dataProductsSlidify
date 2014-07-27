---
title       : Replacement of fossil fuel
subtitle    : By renewable producer gas from biomass
author      : Dinesh SRB
job         : Data science specialization, Coursera
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## About the application

1. This app can be used by any biomass energy companies or Industrial consumers who wish to replace their fossil fuels like LPG, Diesel, Furnace oil etc., with renewable producer gas
2. Producer gas,  mixture of flammable gases (principally carbon monoxide and hydrogen) and nonflammable gases (mainly nitrogen and carbon dioxide) made by the partial combustion of renewable carbonaceous substances like wood, coconut shell etc
3. The app takes 3 inputs  
        a. Type of fuel  
        b. Daily consumption of fuel  
        c. Units of fuel consumption
4. The output of the app is
        a. Equivalent producer gas required to replace their fuel  
        b. Required size of producer gas plant or gasifier
5. To replace the liquid or gaseous fuel, this is the best and most optimal solutions to reduce energy cost by at least 10%

--- .class #id 

## Application Input and Output 1
The code shown below gives you output of the function that is used to calculate equivalent producer gas required to replace fuel based on inputs, fuel, qty, and units


```r
equivBiomass <- function (fuel, qty, units) {
        if (fuel == "LPG") {
                ifelse (units == "tons/day", op <- qty*12000/1100, 
                        ifelse (units == "kL/day", op <- qty * 0.54 * 12000/1100,
                                op <- qty*(12000/1100)/1000
                        ))
        }
        print(paste(round (op, digits = 2), "tons/day"))
}
equivBiomass("LPG", 10, "tons/day") ## Sample input to the function
```

```
## [1] "109.09 tons/day"
```

---

## Application Input and Output 2  
The code shown below gives you output of the function that is used to calculate required gasifier plant size to replace fuel based on inputs, fuel, qty, and units


```r
plantCapacity <- function (fuel, qty, units) {
        if (fuel == "LPG") {
                ifelse (units == "tons/day", op <- qty*12000/1100, 
                        ifelse (units == "kL/day", op <- qty * 0.54 * 12000/1100,
                                op <- qty*(12000/1100)/1000
                        ))
        }  
        op1 <- (op *1000* 1100/3900)/(0.7*24)
        print(paste (round (op1, digits = 2), "kg/hr"))
}
plantCapacity("LPG", 10, "tons/day") ## Sample input to the function
```

```
## [1] "1831.5 kg/hr"
```

---
## Summary

1. This application gives the user a lot of clarity on increase in volume of gas and the required raw material input for the specified gasifier plant size.
2. This would be the first level of calculation to find out the feasibility for replacement of fuel.
3. This app can be extended with other features based on requirement.



