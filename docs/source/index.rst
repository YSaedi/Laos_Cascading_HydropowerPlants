Cascading Hydropower Plants in OSeMOSYS
==============================================================

This documentation represents modelling cascading hydropower plants using OSeMOSYS, which is part of energy modelling with a representation of the cascading hydro facilities in Lao PDR. It is woth mentIn the following sections, required information to build this model is provided based on the available storage code in OSeMOSYS.

    Note: `OSeMOSYS_2017_11_08 <https://github.com/OSeMOSYS/OSeMOSYS_GNU_MathProg/tree/master/src/>`_ includes storage equations that are essential to make relationships inside the cascading hydropower plant modelling.


RES of Cascading Hydropower Plants
------------------------------------------
The conceptual scheme of the model, named Reference Energy System (RES) is designed to simplify and aggregate the complex real energy system under analysis. RES consists of technologies, energy carriers, fuels, and various levels of energy in the supply-demand chain. 

RES of this case study is presented in Figure1 consisting of two dams. RES starts with Rain technology on the left side of the chain connected to the River Water. All required components of RES to model cascading hydropower plants are represented below:


.. figure:: Figure.jpg
    :alt: alternate text
    :figclass: align-center

    Figure 1: Reference Energy System of Cascading Hydropower Plants





Transformation Technologies
...............................................

1.   **Rain**: Brown boxes represent Rain technologies. This model starts with Rain technology connected to the River Water, which is defined as Rain’s output fuel.  
2.	**River**: Blue boxes illustrate River technologies and River Water is the input fuel for that.
3.	**Hydropower Plant**:  Navy blue boxes show Hydropower technologies connected to the dams and generate electricity.
4.	**Power Transmission**:  Gray box illustrates Transmission technology.

Fuel
........................................

1.        **River Water**: Short lines represent river waters connected to Rivers and Hydropower plants.
2.        **Electricity**: Black lines illustrate electricity from power plants and electricity after transmission.
3.        **Final energy demand**: residential, agricultural, and commercial demand.

Storage
.............................................
This sample of cascading hydropower plants consists of two dames introduced as storage inside the model. Rivers and Hydropower Plants are modelled as Technology To Storage and Technology From Storage respectively. following information related to the storages are imported in order to model cascading hydropower plants using OSeMOSYS model.


*	Dams are defined inside the **STORAGE**.
*	Rivers are added as **Technology To Storage**.
*	Hydropower Plants are  imported into the **Technology From Storage** folder.
*	Capital cost of storage 
*	Operational life of storage
*   Minimum storage Charge
*   Storage Maximum Charge
*   Storage Maximum Discharge







+-----------------------------------------------------------------------------------------------+
|  Table1                                                                                       |
+--------------------+--------------+-----------------------------+-----------------------------+
|Technology          |   Input Fuel |   Output Fuel               |     Description             |
+====================+==============+=============================+=============================+
|Transmission        |Electricity   |Electricity after Tansmission|   Power transmission grid A |
+--------------------+--------------+-----------------------------+-----------------------------+
|Hydropower Plant2   |              |Electricity                  |   Powerplant in DAM2        |
+--------------------+--------------+-----------------------------+-----------------------------+
|Hydropower Plant1   |              |Electricity                  |    Powerplant in DAM1       |
+--------------------+--------------+-----------------------------+-----------------------------+
|Hydropower Plant2   |              |River Water1                 | Cascading Hydropower plant  |
+--------------------+--------------+-----------------------------+-----------------------------+
|River2              |River Water2  |                             |       River in watershed2   |
+--------------------+--------------+-----------------------------+-----------------------------+
|River1              |River Water1  |                             |      River in watershed1    |
+--------------------+--------------+-----------------------------+-----------------------------+
|Rain2               |              | River Water2                |    Rain fall in watershed2  |
+--------------------+--------------+-----------------------------+-----------------------------+
|Rain1               |              | River Water1                |    Rain fall in watershed1  |
+--------------------+--------------+-----------------------------+-----------------------------+

     
+--------------------+
|Model Units         |
+============+=======+
|Water Flows | BCM   |
+------------+-------+
| Energy     | PJ    |
+------------+-------+
| Power      | GW    |
+------------+-------+



Temporal Representation
-----------------------------------------------------
The period of time under analysis in this sample is defined from 2020 to 2025.

Times Slices
...................................................
Time slices are fractions of the year with different characteristics in order to define variability in demand and resource availability. In this sample, a year is divided into two seasons, named Season 1 and Season 2, and each season is classified into three categories (baseload, intermediate, and peak). 
Therefore, there are a total of 6 time slices: Season1 baseload, Season 1 intermediate, Season 1 peak, Season2 baseload, Season 2 intermediate, and Season 2 peak.

Year Split
..................................................
Year split specifies the share of each time slice in a year. It is assumed that these parameters will remain unchanged over the years under analysis, more details are shown in Table 2.

Specified Demand Profile
...................................................
The proportion of energy demand that is required in each time slice of the year is defined as specified annual profile, more information is shown in Table 2.

Specified Annual Demand
........................................................
The values of the total specified demand for electricity of each modelled year are defined based on publicly available data an assumption (Table 3).

+--------------------------------------------------------------------+
| Table 2                                                            |
+----------------------+--------------+------------------------------+
|Time slices           |   Year split |   Specified Demand profile   |
+======================+==============+==============================+
|Season1 baseload      |    0.125     |            0.2               |
+----------------------+--------------+------------------------------+
|Season 1 intermediate |    0.125     |            0.2               |     
+----------------------+--------------+------------------------------+
|Season 1 peak         |    0.25      |            0.1               |     
+----------------------+--------------+------------------------------+
|Season2 baseload      |   0.125      |            0.3               |     
+----------------------+--------------+------------------------------+
|Season 2 intermediate |   0.125      |            0.1               |        
+----------------------+--------------+------------------------------+
|Season 2 peak         |   0.25       |            0.1               |    
+----------------------+--------------+------------------------------+

+-----------------------------------------+
| Table 3                                 |
+-------------+---------------------------+
|     Year    | Specified Annual Demand   |
+=============+===========================+
|     2020    |      18.9                 |
+-------------+---------------------------+
|     2021    |      19.5                 |
+-------------+---------------------------+
|     2022    |     19.72                 |
+-------------+---------------------------+
|     2023    |       20                  |
+-------------+---------------------------+
|     2024    |     20.8                  |
+-------------+---------------------------+
|    2025     |      21                   |
+-------------+---------------------------+

License
------------------------------------------------
This work is licensed under a `Creative Commons Attribution 4.0 International License <http://creativecommons.org/licenses/by/4.0/>`_.

.. image:: https://i.creativecommons.org/l/by/4.0/88x31.png
   :width: 100




