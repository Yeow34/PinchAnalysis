# PinchAnalysis
Chemical plants usually comprise several process streams connected to each other in the form of network in order to produce products that can meet the market demand and requirement. Most often, the process streams are supplied by either cold or hot energy for the purpose of energy transport. Thus, the inlet and outlet temperature of each process stream will vary depend on their respective nature. This increase the difficulty to design an optimized heat exchange network for the chemical plants.

This is where Pinch Analysis comes in place. In the industry, Pinch Analysis is often applied to evaluate and enhance the energy system of the chemical plants. Pinch Analysis balances the efficiency of the energy system and total cost related to heat exchange that needs to be incurred to the chemical plants through thermodynamic-based algorithm.

The follow table shows the temperature of the process streams in a chemical plant to be evaluated.
Table 1: Process streams data
|Stream no.|Type|Supply temperature (Ts),°C|Target temperature (Tt), °C|Heat transfer (∆H), MW|Temperature difference (∆T), °C| Heat capacity (CP), MW.K-1|
|---|---|---|---|---|---|---|
|1|Cold|10|150|45|140|0.3214|
|2|Cold|45|290|62|245|0.2531|
|3|Cold|70|110|37|40|0.9250|
|4|Hot|350|240|-42|-110|0.3818|
|5|Hot|270|140|-51.5|-130|0.3962|
|6|Hot|150|100|-55|-50|1.1000|

By using the Python Library, PINA, the results for minimum temperature difference were computed and shown in the following table.
Table 2: Result
|Minimum temperature difference (°C)|10|20|40|
|---|---|---|---|
|Heating demand (MW)|144.0|144.0|144.0|
|Cooling demand (MW)|148.5|148.5|148.5|
|Hot utility target (MW)|0.0|0.0|0.0|
|Cold utility target (MW)|4.50000000000011|4.50000000000016|4.50000000000002|
|Heat recovery target (MW)|144.0|144.0|144.0|
|Pinch temperature (°C)|345|340|330|

In the design of a Heat exchange network (HEN), the heat exchange performance and its economics are highly constrained by the pinch point. In the following context, the heat exchange performance of the HEN is analyzed in relation to its operating cost as well as the capital cost required. Through this, it is identified that the point at which the minimum temperature difference is at 40°C would be the optimum point for this constraint.

As shown in Table 2, the cold utility targets of three sets of pinch analysis are closely identical at 4.5 MW. By looking at the relationship between the minimum temperature difference and cold utility, the trend is actually not physically sound, and it does not comply with the principal of Pinch Analysis. This is because when the thermodynamic efficiency of the heat exchanger is increased (in this case, a smaller minimum temperature difference), the utility required to exchange heat would theoretically be reduced (Castier, 2007). However, in this case, it is observed that when the minimum temperature difference is reduced from 40 to 20 and subsequently further reduced to 10°C, the cold utility surprisingly remains almost constant. It is thus proposed that either the data procured has errors or the pinch point exists at the skewed locations, so that the trend does not obey with the typical pinch analysis. From Table 8, it is identified that the pinch temperature calculated for all three sets of data are 345, 340 and 330 °C. These three sets of pinch temperature are located at the right-end of the composite curve which could be observed in the graph plotted in the Figure 1 unlike the typical pinch analysis where the pinch temperature is located at somewhere left to the center of the entire plot.

<img width="177" alt="image" src="https://user-images.githubusercontent.com/69382649/186195474-d8f37b07-1b0d-4152-bed7-2a3a567cd48e.png">
Figure 1: Composite curve of this dataset

Nevertheless, without looking at the naked data produced from Python, the difference of cold utility for all three sets of pinch analysis are very insignificant. In this case, it would be wise to have a large temperature difference in the HEN as the cold utility required would be the same. Therefore, the minimum temperature difference of 40°C would be the most economical point as it only required the same amount of cold utility to create such heat exchange effect that other two could not have achieved. The trade-off between the minimum temperature difference with the cold utility required is imperative for the estimation of energy cost (one of the operating costs) of the heat exchanger network.

On the other hand, there is another aspect of the overall cost of a HEN that would need to be taken into account which is the capital cost. As discussed in the previous context, the smaller the gap for the minimum temperature difference, the lower the amount of cold utility would be required thus incurring lower operating cost. However, the smaller gap for the minimum temperature difference simply meant that the thermodynamic efficiency of the heat exchanger network would be very low, thus it would require a large surface area available for heat exchange to take place in order to achieve the same level of desired heat exchange, hence larger heat exchangers would be required which incurred higher capital cost (Towler & Sinnott, 2013). In this case, by choosing the largest possible minimum temperature difference, which is at 40°C would also be the most economical point as the surface area required for heat exchange would be comparably smaller as compared to those at 10 and 20 respectively. In the figure below, a simple illustration for the relationship between the total cost required with the trade-off between energy cost and capital cost is shown explicitly.

<img width="261" alt="image" src="https://user-images.githubusercontent.com/69382649/186196128-e755d5dc-fd48-4adf-b6d3-e6043a31a9fd.png">
Figrue 2:Locating the minimum cost require

From the figure, it is understood that only at a certain minimum temperature difference, the lowest amount of total cost required would exist. In this case, the minimum temperature difference at the optimum would be 40°C. By substituting the minimum temperature difference at 10 and 20°C, the point for total cost would shift to the left, which is on an upward trend, simply meaning that higher total cost would be required if both of these minimum temperature differences are to be selected. This is because even though the cold utility required would not alter much as calculated previously, the capital cost would increase when the minimum temperature difference is reduced as shown in Figure 2 due to the requirement for a larger surface area for heat exchange. Therefore, through the contemplate numerical analysis as well as graphical explanation, the statement stating that the optimum point existed at minimum temperature difference of 40°C solidified.

#Reference
Castier, M. (2007). Pinch Analysis Revisited: New Rules for Utility Targeting. Applied Thermal Engineering, 27 (8-9), pp. 1653-1656. https://www.sciencedirect.com/science/article/abs/pii/S135943110600336X

Towler G, & Sinnott R. (2013). Chemical Engineering Design: Principles, Practice and Economics of Plant and Process Design (2nd edition). Boston: Elsevier/
