# Thermal Management

## Fundamental Relationships
- Junction temperature: \( T_j = T_a + P_d \times R_{thJA} \) (or more detailed thermal resistance network)
- Thermal resistance network: junction-to-case (\( R_{thJC} \)), case-to-heatsink, heatsink-to-ambient
- Always include self-heating of all dissipating components

## Cooling Methods
- Natural convection (orientation, surface area, emissivity, fins)
- Forced air (airflow rate, pressure drop, fan selection)
- Liquid cooling (cold plates, cold plates with microchannels, dielectric fluids)
- Heat pipes, vapor chambers, and spreaders
- Phase-change materials for transient loads

## Practical Design Steps
1. Calculate total power dissipation and loss distribution
2. Identify hot spots (semiconductors, magnetics, resistors)
3. Establish maximum allowable \( T_j \) and \( T_c \) with margin
4. Select thermal interface material (TIM) — thickness, conductivity, contact pressure
5. Size heatsink or cold plate
6. Verify airflow or coolant flow
7. Account for altitude, ambient extremes, and enclosure effects
8. Iterate with mechanical constraints

## PCB-Level Thermal Techniques
- Thermal vias under power devices (array density, plating thickness)
- Copper pours and planes as heat spreaders
- Component derating based on local board temperature
- Avoid placing temperature-sensitive parts downstream of heat sources

## Verification
- Infrared thermography
- Thermocouple measurements at critical points
- Compare measured temperatures against calculated values and adjust model
- Never rely solely on \( R_{thJA} \) from a datasheet without understanding the test condition
