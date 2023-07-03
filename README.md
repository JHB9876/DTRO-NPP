# DTRO-NPP
![](https://img.shields.io/badge/status-work%20in%20progress-blue)

This is a first investigation concerning the potential link between the DfT _D-TRO Service_ and _the National Parking Platform (NPP)_ initiatives. It is meant to help to examine the mapping between D-TRO data concepts and similar concepts in NPP, which conforms to APDS.

It is assumed that the primary flow of data would be from D-TRO to NPP.

It is also assumed that the TRO regulations of interest relate to stationary traffic (e.g. kerbside parking, loading, no parking, etc.).

## General Introductory Remarks
The APDS data model and D-TRO data model are designed for different purposes. However, some elements of both models have been drawn from common heritage of sub-models for specific purposes that have been developed over many years and are now specified in various European standards designed for the coding of road traffic data.

Therefore, there is a strong similarity between the D-TRO and APDS modelling of:

- Conditions (including vehicle characteristics)
- Date and time periods

Additionally, the (tariff) Rate model in D-TRO is a simplified version of the Rates model that is found in APDS.

D-TRO Rates sub-model
![image](https://github.com/JHB9876/DTRO-NPP/assets/29631376/f28d3cc3-5da8-4ca8-b0b0-68ad8791c56c)

APDS Rates sub-model
![image](https://github.com/JHB9876/DTRO-NPP/assets/29631376/7131bd7b-b302-44db-b26b-fa0597883b53)


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
|kerbside-NoWaiting |Yes|'noWaiting'|
|kerbside-SchoolKeepClear-YellowZig-zag_mandatory |Yes|- none -|
|kerbside-OtherYellowZig-zag_mandatory |Yes|- none -|
|kerbside-UrbanClearway |Yes| - none -|
|kerbside-RedRouteClearway |Yes| - none -|
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



