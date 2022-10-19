# FFXIV Raid API

## Data Structure
Element | Description | Type | Notes
------------|-------------|---------|-------------------
name | The name of the raid | string | 
raidTier | The tier of the requested raid | string | To differentiate sets within the same raid series, such as Asphodelos.
questline | The raid questline | string | The questline that unloks the raids, such as Pandaemonium.
shortName | The abbriviation for the specific raid | string | Explained in further detail below. |
minCharLvl | The minimum character level to unlock the raid | integer | |
minILvl | The minimum iLvl needed to enter the raid | integer | |
numTanks | The number of tanks required for a standard queue for the raid | integer | Commonly 2. | 
numHealers | The number of healers requried for a standard queue for the raid | integer | Commonly 2. |
numDPS | The number of DPS required for a standard queue of the raid | integer | Commonly 4.

### Short Name
Rarids are commonly referred to by players, or raiders, by a short name consisting of the first letter of the raid questline name, such as Eden, Omega, etc., and the raid number within the questline. Savage difficulty raids are followed with an S. For example, the 9th raid of the Eden questline on Savage difficulty is referred to as **E9S**. [^1]

## Retrieve Raid by ID
```
GET http://localhost:3000/raids/id/{_id}

where {_id} is the id of the raid.
```
**NOTE** This URL is also used to update and delete data.

## Retrive Raid by Short Name
Displays raid information by using the its short name.
`GET http://localhost:3000/raids/{shortName}`

## Update Raid by ID
Updates the raid data by ID.
```
PUT http://localhost:3000/raids/id/{_id}
```

## Delete Raid by ID
Deletes raid dada by ID.
```
DELETE http://localhost3000:raids/id/{_id}
```

[^1]: Exception for The Coils of Bahamut questline, which uses "T" for "Turn."
