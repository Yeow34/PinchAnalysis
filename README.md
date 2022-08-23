# PinchAnalysis
Chemical plants usually comprise several process streams connected to each other in the form of network in order to produce products that can meet the market demand and requirement. Most often, the process streams are supplied by either cold or hot energy for the purpose of energy transport. Thus, the inlet and outlet temperature of each process stream will vary depend on their respective nature. This increase the difficulty to design an optimized heat exchange network for the chemical plants.

This is where Pinch Analysis comes in place. In the industry, Pinch Analysis is often applied to evaluate and enhance the energy system of the chemical plants. Pinch Analysis balances the efficiency of the energy system and total cost related to heat exchange that needs to be incurred to the chemical plants through thermodynamic-based algorithm.

The follow table shows the temperature of the process streams in a chemical plant to be evaluated.
|Stream no.|Type|Supply temperature (Ts),°C|Target temperature (Tt), °C|Heat transfer (∆H), MW|Temperature difference (∆T), °C| Heat capacity (CP), MW.K-1|
|---|---|---|---|---|---|---|
|1|Cold|10|150|45|140|0.3214|
|2|Cold|45|290|62|245|0.2531|
|3|Cold|70|110|37|40|0.9250|
|4|Hot|350|240|-42|-110|0.3818|
|5|Hot|270|140|-51.5|-130|0.3962|
|6|Hot|150|100|-55|-50|1.1000|

By using the Python Library, PINA, the results for minimum temperature difference were computed and shown in the following table.
|Minimum temperature difference (°C)|10|20|40|
|Heating demand (MW)|144.0|144.0|144.0|
|Cooling demand (MW)|148.5|148.5|148.5|
|Hot utility target (MW)|0.0|0.0|0.0|
|Cold utility target (MW)|4.50000000000011|4.50000000000016|4.50000000000002|
|Heat recovery target (MW)|144.0|144.0|144.0|
|Pinch temperature (°C)|345|340|330|

