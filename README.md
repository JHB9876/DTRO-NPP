# D-TRO-NPP
![](https://img.shields.io/badge/status-work%20in%20progress-blue)

This is a first investigation concerning the potential link between the DfT _D-TRO Service_ and _the National Parking Platform (NPP)_ initiatives. It is meant to help to examine the mapping between D-TRO data concepts and similar concepts in NPP, which conforms to APDS.

It is assumed that the primary flow of data would be from D-TRO to NPP.

It is also assumed that the TRO regulations of interest relate to stationary traffic (e.g. kerbside parking, loading, no parking, etc.).

## General Introductory Remarks
The APDS data model and D-TRO data model are designed for different purposes. However, some elements of both models have been drawn from common heritage of sub-models for specific purposes that have been developed over many years and are now specified in various European standards designed for the coding of road traffic data.

Therefore, there is a strong similarity between the D-TRO and APDS modelling of:

- Date and time periods of applicability
- Conditions (including vehicle characteristics)
- Rates (and tariffs)

These models are not identical.

The Date and Time sub-model for D-TRO, is built on the earlier APDS model.  It has a little more functionality:
![D-TRO_Validity](https://github.com/JHB9876/DTRO-NPP/assets/29631376/25977d7d-c09d-497a-85df-88ede644d6a8)

The Date and Time sub-model for APDS
![APDS_Validity](https://github.com/JHB9876/DTRO-NPP/assets/29631376/59539ff5-ec9e-47d4-aeb6-4e0d87d07de7)

CONDITION/ELIGIBILITY/QUALIFICATIONS MODELS... to be added.

Additionally, the (tariff) Rate model in D-TRO is a simplified version of the Rates model that is found in APDS.

D-TRO Rates sub-model
![D-TRO_Rates](https://github.com/JHB9876/DTRO-NPP/assets/29631376/279e05e0-f246-4f76-bb99-d7d70d8267a3)
 
APDS Rates sub-model
![APDS_Rates](https://github.com/JHB9876/DTRO-NPP/assets/29631376/119cd4c0-f704-4c04-9f58-1c88d0faeb3a)



## Most interesting data to transfer

The D-TRO Regulation type list form a key basis of context for shared D-TRO data. This is specified in the 'regulationType' enumeration list. In addition to the entries in this list different forms of speed limit are available. In addition, and ability to specify an unlisted regulation type also exists in D-TRO by use of the OffListRegulation class.

|D-TRO regulations|
|-----------------|
|kerbside-RuralClearway|
|kerbside-NoLoading|
|kerbside-NoStopping|
|kerbside-NoWaiting|
|kerbside-SchoolKeepClear-YellowZig-zag_mandatory|
|kerbside-OtherYellowZig-zag_mandatory|
|kerbside-UrbanClearway|
|kerbside-RedRouteClearway|
|kerbside-FootwayParkingProhibited|
|kerbside-DisabledBadgeHoldersOnly|
|kerbside-LimitedWaiting|
|kerbside-LoadingPlace|
|kerbside-MotorcycleParkingPlace|
|kerbside-TaxiRank|
|kerbside-LoadingBay|
|kerbside-ParkingPlace|
|kerbside-PaymentParkingPlace|
|kerbside-PermitParkingPlace|
|kerbside-FootwayParking|
|kerbside-PermitParkingArea|
|kerbside-ControlledParkingZone|
|kerbside-RestrictedParkingZone|
|nonOrderKerbside-BusStop|
|nonOrderKerbside-PedestrianCrossing|
|bannedMovement-NoRightTurn|
|bannedMovement-NoEntry|
|bannedMovement-NoLeftTurn|
|bannedMovement-NoU-turn|
|mandatoryDirection-AheadOnly|
|mandatoryDirection-OneWay|
|mandatoryDirection-LeftTurnOnly|
|mandatoryDirection-RightTurnOnly|
|movementOrder-NoOvertaking|
|movementOrder-ProhibitedAccess|
|movementOrder-PriorityOverOncomingTraffic|
|nonOrderMovement-BoxJunction|
|dimension-MaximumHeight_withTRO|
|dimension-MaximumWeight_environmental|
|dimension-MaximumWidth|
|dimension-MaximumHeight_Structural|
|dimension-MaximumLength|
|dimension-MaximumWeight_structural|
|other-BusLane-WithTrafficFlow|
|other-BusOnlyStreet|
|other-BusGate|
|other-ContraflowBusLane|
|other-Congestion-LowEmissionZone|
|other-CycleLane|
|other-PedestrianZone|

APDS Operating Restrictions are specified in the OperatingRestrictionEnum enumeration list.

|Enumerated value name	|Definition|
|-----------|----------|
|busOnly|	only buses are permitted|
|busStop| this is a stopping place of bus pick-up or drop-off; not to be used for parking|
|carpoolOnly|	only carpool vehicles are permitted|
|commercialVehicleOnly| only	only commercial vehicles are permitted
|disabledPersonPermitOnly|	only vehicles of registered disabled person permit holders permitted|
|electricVehicleOnly|	only	only electric vehicles permitted|
|freeParking|	no fee for parking|
|governmentVehicleOnly|	only government vehicles permitted|
|loadingZone|	this is a loading zone; not to be used for parking|
|loadingZoneCommercial|	only government vehicles permitted|
|media	|only for use by the media|
|noParking|	no parking permitted|
|noWaiting|	no waiting or parking of vehicles is permitted|
|parkingTimeLimit|	time limited parking|
|residentialPermitOnly|	only for use by residential permit holders only|
|snow| snow clearing zone; no parking|
|streetCleaning|	street cleansing zone; no parking|
|taxiOnly|	only taxis are permitted|
|valetOnly| only valet service vehicles are permitted|



The second column in the table below indicates whether the regulation type is assumed to be of interest in an NPP context.

| D-TRO Regulation |NPP?|Mapping to APDS|
|------------------|---|------|
|kerbside-RuralClearway |Yes| - none -|
|kerbside-NoLoading |Yes| - none -|
|kerbside-NoStopping |Yes| - none -|
|kerbside-NoWaiting |Yes|'noWaiting' (confirm 'no waiting' is the superset version of 'no parking')|
|kerbside-SchoolKeepClear-YellowZig-zag_mandatory |Yes|- none -|
|kerbside-OtherYellowZig-zag_mandatory |Yes|- none -|
|kerbside-UrbanClearway |Yes| - none (no stopping? no waiting?)|
|kerbside-RedRouteClearway |Yes| - none (no stopping? no waiting?) |
|kerbside-FootwayParkingProhibited |Yes| - none -|
|kerbside-DisabledBadgeHoldersOnly |Yes|'disabledPersonPermitOnly'|
|kerbside-LimitedWaiting |Yes|- none -|
|kerbside-LoadingPlace |Yes|'loadingZone'|
|kerbside-MotorcycleParkingPlace |Yes|- none -|
|kerbside-TaxiRank |Yes| 'taxiOnly'|
|kerbside-LoadingBay |Yes|'loadingZone'|
|kerbside-ParkingPlace |Yes|- none -|
|kerbside-PaymentParkingPlace |Yes|- none -|
|kerbside-PermitParkingPlace |Yes|'residentialPermitOnly' in some cases|
|kerbside-FootwayParking |Yes|- none -|
|kerbside-PermitParkingArea |Yes|'residentialPermitOnly' in some cases|
|kerbside-ControlledParkingZone |Yes|- none -|
|kerbside-RestrictedParkingZone |Yes|- none -|
|nonOrderKerbside-BusStop |Yes|'busStop'|
|nonOrderKerbside-PedestrianCrossing |Yes|- none -|
|bannedMovement-NoRightTurn |No||
|bannedMovement-NoEntry |No||
|bannedMovement-NoLeftTurn |No||
|bannedMovement-NoU-turn |No||
|mandatoryDirection-AheadOnly |No||
|mandatoryDirection-OneWay |No||
|mandatoryDirection-LeftTurnOnly |No||
|mandatoryDirection-RightTurnOnly |No||
|movementOrder-NoOvertaking |No||
|movementOrder-ProhibitedAccess |No||
|movementOrder-PriorityOverOncomingTraffic |No||
|nonOrderMovement-BoxJunction |No||
|dimension-MaximumHeight_withTRO |No||
|dimension-MaximumWeight_environmental |No||
|dimension-MaximumWidth |No||
|dimension-MaximumHeight_Structural |No||
|dimension-MaximumLength |No||
|dimension-MaximumWeight_structural |No||
|other-BusLane-WithTrafficFlow |No||
|other-BusOnlyStreet |No|'busOnly'?|
|other-BusGate |No||
|other-ContraflowBusLane |No||
|other-Congestion-LowEmissionZone |?||
|other-CycleLane |No||
|other-PedestrianZone |No||

_**Observation: those 'kerbside-' entries which have -none- listed against them will require further review.  These entries may be possible to map meaningfully to APDS entries (i.e. multiple-to-one mapping), or may highlight omissions from the APDS specification.**_

APDS Operating Restriction values with no obvious D-TRO source:

| APDS operating restriction | Commentary |
|------------------|---------|
|carpoolOnly| Perhaps more of a vehicle usage or permit type than primary regulation, but it is not clear what the carpoolOnly qualifier in APDS permits or prohibits. It is assumed to relate to permit-limited parking)|
|commercialVehicleOnly| |
|electricVehicleOnly|Both APDS and D-TRO enable qualification by vehicle characteristic [fueltype] to limit to electric vehicles. Again, it is not clear what the electricVehicleOnly qualifier in APDS permits or prohibits|
|freeParking| Parking with no charge an option?|
|governmentVehicleOnly|This feels more like a VehicleUsage type qualifier - again, it does not state what is permitted or prohibited in APDS. D-TRO does not have away of qualifying Government vehicles|
|loadingZoneCommercial|D-TRO 'Loading Place' regulation, but no means to identify commercial usage |
|media|vehicle usage? no equivalent in D-TRO|
|noParking| Checking with TRO experts whether no parking and no waiting are distinct legal regulations|
|parkingTimeLimit| This is permitted parking with a defined rest period limit, and probably stated no return period - not distinct conceptually from 'kerbside-ParkingPlace' or other similar D-TRO regulations|
|snow (clearance route)|Interesting - Will check whether we are aware of any TROs of this nature in UK|
|streetCleaning|Again interesting - Will check whether we are aware of any TROs of this nature in UK|
|valetOnly|Perhaps more of a vehicle usage or permit type than primary regulation, but it is not clear what the valetOnly qualifier in APDS permits or prohibits. It is assumed to relate to permit-limited parking)|

## Other classification of kerbside regulations

As a logical cross-check it is worth reviewing the types of regulations and restrictions that other 'standards' recognise. One industry specification that is regularly mentioned in the Open Curb Specification (https://github.com/openmobilityfoundation/curb-data-specification/tree/main/curbs#activities). 

This presents the following categorisation of 'rules':

_Activities_
_The following activities may be specified for rules within a policy. The reason we have "positive" and "negative" versions of the same activities (like loading and no parking) is due to priorities: a loading rule that is higher priority than a no loading rule, for instance, implies that the Curb Zone does allow loading at the time in question, while a no parking rule would not. If "negative", rate array should be empty._
_
- parking - implies that loading and stopping are also permitted
- no parking - may not stop and leave vehicle unattended
- loading - loading of goods; implies that stopping is also permitted
- no loading - no loading allowed; implies that parking is also prohibited
- unloading - unloading of goods; implies that stopping is also permitted
- no unloading - no unloading allowed; implies that parking is also prohibited
- stopping - stopping briefly to pick up or drop off passengers
- no stopping - stopping, loading, unloading, and parking are all prohibited; not a typical travel lane
- travel - represents curbside lanes typically intended for moving vehicles, like bus lanes, bike lanes, and rush-hour-only travel lanes; implies that parking, loading, unloading, and stopping are prohibited.
- no travel - no travel allowed; implies it could be used for other activities_

This approach might be considered to be a bit simplified in the context of D-TRO data and the complexity of UK TRO regulation types.
