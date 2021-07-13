Spawn Condition Profiles are what control when a SpawnGroup is allowed to be spawned at a certain time or place.

SpawnGroups can have multiple Spawn Condition Profiles. When evaluating the profiles for spawning eligibility, only a single Spawn Condition Profile needs to be satisfied in order for the SpawnGroup to be considered eligible for spawning.

The tags in the Spawn Condition Profiles can be placed directly in the SpawnGroup tags. This is because these tags were once part of the regular SpawnGroup tags, and steps to ensure compatibility were considered.

Here is an example of how a Spawn Condition Profile is created:

```
<?xml version="1.0"?>
<Definitions xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <EntityComponents>

    <EntityComponent xsi:type="MyObjectBuilder_InventoryComponentDefinition">
      <Id>
        <TypeId>Inventory</TypeId>
        <SubtypeId>MES-SpawnProfile-CargoShipExample</SubtypeId>
      </Id>
      <Description>

        [MES Spawn Conditions]

        [SpaceCargoShip:true]
        [LunarCargoShip:true]

		[UseThreatLevelCheck:true]
		[ThreatLevelCheckRange:15000]
		[ThreatScoreMinimum:500]

      </Description>

    </EntityComponent>
    
  </EntityComponents>
</Definitions>
```

To link a profile to your SpawnGroup, simply use the `SpawnConditionsProfiles` tag and provide the SubtypeId of the Spawn Condition Profile you created. Eg: `[SpawnConditionsProfiles:MES-SpawnProfile-CargoShipExample]`. 

Below are several types of condition tags you can include in your Spawn Condition Profile:


[Space-Cargo-Ships](#Space-Cargo-Ships)  
[Random-Encounters](#Random-Encounters)  
[Planetary-Cargo-Ships](#Planetary-Cargo-Ships)  
[Planetary-Installations](#Planetary-Installations)  
[Boss-Encounters](#Boss-Encounters)  
[Creatures](#Creatures)  
[Static-Encounters](#Static-Encounters)  
[Other-NPCs](#Other-NPCs)  
  
[General](#General)  
[Cost](#Cost)  
[Economy](#Economy)  
[Faction](#Faction)  
[Known-Player-Location](#Known-Player-Location)  
[Mods](#Mods)  
[Planetary](#Planetary)  
[Players](#Players)  
[Reputation](#Reputation)  
[Restrictions](#Restrictions)  
[Settings](#Settings)  
[Threat](#Threat)  
[Variables](#Variables)  
[World](#World)  
[Zone](#Zone)  


# Space-Cargo-Ships

<!-- SpaceCargoShip  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SpaceCargoShip|
|:----|:----|
|Tag Format:|`[SpaceCargoShip:Value]`|
|Description:|This tag specifies if the SpawnGroup should spawn as a Space Cargo Ship.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- LunarCargoShip  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|LunarCargoShip|
|:----|:----|
|Tag Format:|`[LunarCargoShip:Value]`|
|Description:|This tag specifies if the SpawnGroup should spawn as a Lunar Cargo Ship.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- UseAutoPilotInSpace  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|UseAutoPilotInSpace|
|:----|:----|
|Tag Format:|`[UseAutoPilotInSpace:Value]`|
|Description:| If set to `true`, Space and Lunar Cargo Ships will instead use Auto-Pilot to fly to their Despawn Coords.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- SpaceCargoShipChance  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SpaceCargoShipChance|
|:----|:----|
|Tag Format:|`[SpaceCargoShipChance:Value]`|
|Description:|This tag specifies the chance (out of 100) this spawngroup has of being selected as eligible if being spawned as a Space Cargo Ship.|
|Allowed Values:|`0` - `100`|
|Default Value(s):|`100`|
|Multiple Tag Allowed:|No|

<!-- LunarCargoShipChance  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|LunarCargoShipChance|
|:----|:----|
|Tag Format:|`[LunarCargoShipChance:Value]`|
|Description:|This tag specifies the chance (out of 100) this spawngroup has of being selected as eligible if being spawned as a Lunar Cargo Ship.|
|Allowed Values:|`0` - `100`|
|Default Value(s):|`100`|
|Multiple Tag Allowed:|No|

# Random-Encounters

<!-- SpaceRandomEncounter  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SpaceRandomEncounter|
|:----|:----|
|Tag Format:|`[SpaceRandomEncounter:Value]`|
|Description:|This tag specifies if the SpawnGroup should spawn as a Random Encounter (Space).|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- RandomEncounterChance  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RandomEncounterChance|
|:----|:----|
|Tag Format:|`[RandomEncounterChance:Value]`|
|Description:|This tag specifies the chance (out of 100) this spawngroup has of being selected as eligible if being spawned as a Random Encounter.|
|Allowed Values:|`0` - `100`|
|Default Value(s):|`100`|
|Multiple Tag Allowed:|No|


# Planetary-Cargo-Ships

<!-- AtmosphericCargoShip  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|AtmosphericCargoShip|
|:----|:----|
|Tag Format:|`[AtmosphericCargoShip:Value]`|
|Description:|This tag specifies if the SpawnGroup should spawn as a Planetary Cargo Ship.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- GravityCargoShip  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|GravityCargoShip|
|:----|:----|
|Tag Format:|`[GravityCargoShip:Value]`|
|Description:|This tag specifies if the SpawnGroup should spawn as a Gravity Cargo Ship. These types of cargo ships will are eligible to spawn when the player is above the `PlayerSurfaceAltitude` altitude of a planet and is still in gravity range. This allows cargo ships to appear in the previously 'dead zone' between where the atmosphere ends and space begins. Consider using `MinGravity` and/or `MaxGravity` spawngroup tags to control what parts of gravity these ships can appear in.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- AtmosphericCargoShipChance  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|AtmosphericCargoShipChance|
|:----|:----|
|Tag Format:|`[AtmosphericCargoShipChance:Value]`|
|Description:|This tag specifies the chance (out of 100) this spawngroup has of being selected as eligible if being spawned as a Planetary Cargo Ship.|
|Allowed Values:|`0` - `100`|
|Default Value(s):|`100`|
|Multiple Tag Allowed:|No|

<!-- GravityCargoShipChance  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|GravityCargoShipChance|
|:----|:----|
|Tag Format:|`[GravityCargoShipChance:Value]`|
|Description:|This tag specifies the chance (out of 100) this spawngroup has of being selected as eligible if being spawned as a Gravity Cargo Ship.|
|Allowed Values:|`0` - `100`|
|Default Value(s):|`100`|
|Multiple Tag Allowed:|No|

<!-- SkipAirDensityCheck-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SkipAirDensityCheck|
|:----|:----|
|Tag Format:|`[SkipAirDensityCheck:Value]`|
|Description:|This tag specifies if the SpawnGroup should skip checks for Air Density when considering spawn eligibility on a planet. This should only be used for ships that primarily use Hydrogen Thrust or have sufficient Ion Thrust in the environment they're spawning in.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- CargoShipTerrainPath-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|CargoShipTerrainPath|
|:----|:----|
|Tag Format:|`[CargoShipTerrainPath:Value]`|
|Description:|This tag specifies if the path that is designated for the Planetary Cargo Ship should be calculated along the surface of the planet instead of in the air. This is useful for RivalAI behaviors that use hover-like flight mechanics so it can be determined if the flight path still meets other requirements such as Air Density.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- CustomPathStartAltitude-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|CustomPathStartAltitude|
|:----|:----|
|Tag Format:|`[CustomPathStartAltitude:Value]`|
|Description:|This tag specifies a custom altitude from the terrain surface that the SpawnGroup will be spawned at instead of the path start point that is initially calculated.|
|Allowed Values:|Any Number Greater or Equal to `0`|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|

<!-- CustomPathEndAltitude-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|CustomPathEndAltitude|
|:----|:----|
|Tag Format:|`[CustomPathEndAltitude:Value]`|
|Description:|This tag specifies a custom altitude from the terrain surface that the Cargo Ship SpawnGroup will attempt to reach instead of the end path point that is initially calculated.|
|Allowed Values:|Any Number Greater or Equal to `0`|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|


# Planetary-Installations

<!-- PlanetaryInstallation  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|PlanetaryInstallation|
|:----|:----|
|Tag Format:|`[PlanetaryInstallation:Value]`|
|Description:|This tag specifies if the SpawnGroup should spawn as a Planetary Installation.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- PlanetaryInstallationType  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|PlanetaryInstallationType|
|:----|:----|
|Tag Format:|`[PlanetaryInstallationType:Value]`|
|Description:|This tag specifies what size category a Planetary Installation SpawnGroup should spawn as.|
|Allowed Values:|`Small`<br>`Medium`<br>`Large`|
|Default Value(s):|`Small`|
|Multiple Tag Allowed:|No|

<!-- PlanetaryInstallationChance  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|PlanetaryInstallationChance|
|:----|:----|
|Tag Format:|`[PlanetaryInstallationChance:Value]`|
|Description:|This tag specifies the chance (out of 100) this spawngroup has of being selected as eligible if being spawned as a Planetary Installation.|
|Allowed Values:|`0` - `100`|
|Default Value(s):|`100`|
|Multiple Tag Allowed:|No|

<!-- RotateInstallations  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RotateInstallations|
|:----|:----|
|Tag Format:|`[RotateInstallations:Value1,Value2,Value3,etc]`|
|Description:|This tag allows you to specify one or more rotations to use on an installation to give it a tilt in the ground. Each Value is replaced by the following: `{X:0 Y:0 Z:0}`. X affects Pitch, Y affects Yaw, Z affects Roll. Each of the X,Y,Z values accept a range between `-45` to `45`. Providing a value of `{X:100 Y:100 Z:100}` will result in a randomized rotation being used. When providing multiple values, the first value will affect the first prefab, second value affects second prefab, etc.|
|Allowed Values:|Rotation (see above for example)<br>If providing multiple values, use comma with no spaces as shown in `Tag Format`|
|Default Value(s):|`none`|
|Multiple Tag Allowed:|No|

<!-- ReverseForwardDirections  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ReverseForwardDirections|
|:----|:----|
|Tag Format:|`[ReverseForwardDirections:Value]`|
|Description:|This tag allows you to specify one or more of the spawned prefabs should have their 'Forward' direction reversed at spawn. When providing multiple values, the first value will affect the first prefab, second value affects second prefab, etc.|
|Allowed Values:|`true`<br>`false`<br>If providing multiple values, use comma with no spaces as shown in `Tag Format`|
|Default Value(s):|`none`|
|Multiple Tag Allowed:|No|

<!-- InstallationTerrainValidation  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|InstallationTerrainValidation|
|:----|:----|
|Tag Format:|`[InstallationTerrainValidation:Value]`|
|Description:|This tag specifies if the SpawnGroup should only spawn on one of a few specified terrain types as defined by the `AllowedTerrainTypes` tag.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- InstallationSpawnsOnDryLand  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|InstallationSpawnsOnDryLand|
|:----|:----|
|Tag Format:|`[InstallationSpawnsOnDryLand:Value]`|
|Description:|This tag specifies if the SpawnGroup should spawn on Dry Land if you are using the [Water Mod](https://steamcommunity.com/sharedfiles/filedetails/?id=2200451495) by Jakaria|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`true`|
|Multiple Tag Allowed:|No|

<!-- InstallationSpawnsUnderwater  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|InstallationSpawnsUnderwater|
|:----|:----|
|Tag Format:|`[InstallationSpawnsUnderwater:Value]`|
|Description:|This tag specifies if the SpawnGroup should spawn Underwater if you are using the [Water Mod](https://steamcommunity.com/sharedfiles/filedetails/?id=2200451495) by Jakaria|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- InstallationSpawnsOnWaterSurface  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|InstallationSpawnsOnWaterSurface|
|:----|:----|
|Tag Format:|`[InstallationSpawnsOnWaterSurface:Value]`|
|Description:|This tag specifies if the SpawnGroup should spawn on the Water Surface if you are using the [Water Mod](https://steamcommunity.com/sharedfiles/filedetails/?id=2200451495) by Jakaria. Installations spawned on the Water Surface will not be considered static grids. You should also ensure they are able to float as per the buoyancy rules of the Water Mod.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- CutVoxelsAtAirtightCells  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|CutVoxelsAtAirtightCells|
|:----|:----|
|Tag Format:|`[CutVoxelsAtAirtightCells:Value]`|
|Description:|This tag specifies if the spawned station should have voxel material removed at any cell that is determined to be Air-Tight. Please note this is still experimental and not completely functional in some cases.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|


# Boss-Encounters

<!-- BossEncounterSpace  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|BossEncounterSpace|
|:----|:----|
|Tag Format:|`[BossEncounterSpace:Value]`|
|Description:|This tag specifies if the SpawnGroup should spawn as a Boss Encounter that only appears in Space.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- BossEncounterAtmo  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|BossEncounterAtmo|
|:----|:----|
|Tag Format:|`[BossEncounterAtmo:Value]`|
|Description:|This tag specifies if the SpawnGroup should spawn as a Boss Encounter that only appears in planetary atmosphere.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- BossEncounterAny  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|BossEncounterAny|
|:----|:----|
|Tag Format:|`[BossEncounterAny:Value]`|
|Description:|This tag specifies if the SpawnGroup should spawn as a Boss Encounter that can spawn in any environment.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- BossEncounterChance  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|BossEncounterChance|
|:----|:----|
|Tag Format:|`[BossEncounterChance:Value]`|
|Description:|This tag specifies the chance (out of 100) this spawngroup has of being selected as eligible if being spawned as a Boss Encounter.|
|Allowed Values:|`0` - `100`|
|Default Value(s):|`100`|
|Multiple Tag Allowed:|No|

<!-- BossCustomAnnounceEnable  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|BossCustomAnnounceEnable|
|:----|:----|
|Tag Format:|`[BossCustomAnnounceEnable:Value]`|
|Description:|This tag specifies if a custom chat message is broadcast to players when a Boss Encounter GPS signal is created.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`none`|
|Multiple Tag Allowed:|No|

<!-- BossCustomAnnounceAuthor  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|BossCustomAnnounceAuthor|
|:----|:----|
|Tag Format:|`[BossCustomAnnounceAuthor:Value]`|
|Description:|This tag specifies the `Author` name that appears with the chat message if `BossCustomAnnounceEnable` is set to `true`.|
|Allowed Values:|Any String Value|
|Default Value(s):|`none`|
|Multiple Tag Allowed:|No|

<!-- BossCustomAnnounceMessage  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|BossCustomAnnounceMessage|
|:----|:----|
|Tag Format:|`[BossCustomAnnounceMessage:Value]`|
|Description:|This tag specifies the 'Message' that appears with the chat message if `BossCustomAnnounceEnable` is set to `true`.|
|Allowed Values:|Any String Value|
|Default Value(s):|`none`|
|Multiple Tag Allowed:|No|

<!-- BossCustomGPSLabel  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|BossCustomGPSLabel|
|:----|:----|
|Tag Format:|`[BossCustomGPSLabel:Value]`|
|Description:|This tag specifies the name of the GPS signal that gets created when a Boss Encounter spawns.|
|Allowed Values:|Any String Value|
|Default Value(s):|`Dangerous Encounter`|
|Multiple Tag Allowed:|No|


# Creatures

Creature spawning is a little bit different than using SpawnGroups for Grid Spawning. Because we are still using a SpawnGroup to spawn the creatures, we still need to include a Prefab in the SpawnGroup, otherwise the game will throw an error.

Below is an example SpawnGroup you can use for spawning creatures:

```
    <SpawnGroup>
      <Id>
        <TypeId>SpawnGroupDefinition</TypeId>
        <SubtypeId>Example-SpawnGroup-CreatureTest</SubtypeId>
      </Id>
      <Description>

        [Modular Encounters SpawnGroup]

        [CreatureSpawn:true]
        [CreatureIds:SpaceSpider]
        [MinCreatureCount:2]
        [MaxCreatureCount:5]
        [MinCreatureDistance:25]
        [MaxCreatureDistance:30]

      </Description>
      <IsPirate>true</IsPirate>
      <Frequency>5.0</Frequency>
      <Prefabs>
        <Prefab SubtypeId="MES-CreaturePrefabDummy">
          <Position>
            <X>0.0</X>
            <Y>0.0</Y>
            <Z>0.0</Z>
          </Position>
        </Prefab>
      </Prefabs>
    </SpawnGroup>
```

Below are the SpawnGroup tags are specific to Creature Spawning (you can also use many of the tags in the Common section with Creature Spawns as well):

<!-- CreatureSpawn -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|CreatureSpawn|
|:----|:----|
|Tag Format:|`[CreatureSpawn:Value]`|
|Description:|This tag specifies if the SpawnGroup should spawn as a Creature / Bot that appears on the planet surface. It's important to note that you must still include a prefab with your spawngroup (the game requires this), but it will not be used to spawn the creatures.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- CreatureIds -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|CreatureIds|
|:----|:----|
|Tag Format:|`[CreatureIds:Value]`|
|Description:|This tag specifies one or more Creature / Bot SubtypeIds that get used for spawning. If multiple Ids are provided, then each creature spawned will be chosen at random from the provided tags.|
|Allowed Values:|Any Creature / Bot SubtypeId|
|Default Value(s):|`N/A`|
|Multiple Tag Allowed:|Yes|

<!-- MinCreatureCount-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|MinCreatureCount|
|:----|:----|
|Tag Format:|`[MinCreatureCount:Value]`|
|Description:|This tag specifies the minimum amount of Creatures that are spawned if `CreatureSpawn` is `true`.|
|Allowed Values:|Any integer `1` or higher<br>Value should be equal or lower than `MaxCreatureCount`|
|Default Value(s):|`1`|
|Multiple Tag Allowed:|No|

<!-- MaxCreatureCount-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|MaxCreatureCount|
|:----|:----|
|Tag Format:|`[MaxCreatureCount:Value]`|
|Description:|This tag specifies the maximum amount of Creatures that are spawned if `CreatureSpawn` is `true`.|
|Allowed Values:|Any integer `1` or higher<br>Value should be equal or higher than `MinCreatureCount`|
|Default Value(s):|`1`|
|Multiple Tag Allowed:|No|

<!-- MinCreatureDistance-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|MinCreatureDistance|
|:----|:----|
|Tag Format:|`[MinCreatureDistance:Value]`|
|Description:|This tag specifies the minimum distance from the player Creatures that are spawned at if `CreatureSpawn` is `true`.|
|Allowed Values:|Any integer `1` or higher<br>Value should be equal or lower than `MaxCreatureDistance`|
|Default Value(s):|`100`|
|Multiple Tag Allowed:|No|

<!-- MaxCreatureDistance-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|MaxCreatureDistance|
|:----|:----|
|Tag Format:|`[MaxCreatureDistance:Value]`|
|Description:|This tag specifies the maximum distance from the player Creatures that are spawned at if `CreatureSpawn` is `true`.|
|Allowed Values:|Any integer `1` or higher<br>Value should be equal or higher than `MinCreatureDistance`|
|Default Value(s):|`150`|
|Multiple Tag Allowed:|No|


# Static-Encounters


# Other-NPCs

<!-- RivalAiSpaceSpawn  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RivalAiSpaceSpawn|
|:----|:----|
|Tag Format:|`[RivalAiSpaceSpawn:Value]`|
|Description:|This tag specifies if a RivalAI Spawned Encounter should spawn in Space (No gravity or atmosphere). Please note this tag is only used for encounters spawned by the Spawning System in RivalAI.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- RivalAiAtmosphericSpawn  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RivalAiAtmosphericSpawn|
|:----|:----|
|Tag Format:|`[RivalAiAtmosphericSpawn:Value]`|
|Description:|This tag specifies if a RivalAI Spawned Encounter should spawn in Atmosphere. Please note this tag is only used for encounters spawned by the Spawning System in RivalAI.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- RivalAiAnySpawn  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RivalAiAnySpawn|
|:----|:----|
|Tag Format:|`[RivalAiAnySpawn:Value]`|
|Description:|This tag specifies if a RivalAI Spawned Encounter should spawn in any environment. Please note this tag is only used for encounters spawned by the Spawning System in RivalAI.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- UseRivalAi  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|UseRivalAi|
|:----|:----|
|Tag Format:|`[UseRivalAi:Value]`|
|Description:|This tag allows you to specify if a RivalAI Behavior Profile should be used in the prefabs included in your SpawnGroup. With this tag being set to `true`, the spawner will look for a RivalAI Behavior with a SubtypeId matching what was provided in the Prefab `<Behaviour>` tags, and will automatically add it to a valid RivalAI Remote Control block.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- RivalAiReplaceRemoteControl  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RivalAiReplaceRemoteControl|
|:----|:----|
|Tag Format:|`[RivalAiReplaceRemoteControl:Value]`|
|Description:|This tag allows you to specify if the first valid Vanilla Remote Control block in each Prefab should be replaced with a RivalAI Remote Control.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- ApplyBehaviorToNamedBlock  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ApplyBehaviorToNamedBlock|
|:----|:----|
|Tag Format:|`[ApplyBehaviorToNamedBlock:Value]`|
|Description:|This tag allows you to specify the specific block name of a Remote Control block that you want to have used/replaced with a RivalAI control block.|
|Allowed Values:|Any Remote Control Block Name|
|Default Value(s):|`none`|
|Multiple Tag Allowed:|No|

<!-- ConvertAllRemoteControlBlocks  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ConvertAllRemoteControlBlocks|
|:----|:----|
|Tag Format:|`[ConvertAllRemoteControlBlocks:Value]`|
|Description:|This tag allows you to specify if all remote control blocks should be converted to RivalAI control blocks. Only the first or primary (or named, if you use the option above) block will receive the behavior specified in your prefab, other blocks will need to use RivalAI Trigger/Action to assign behaviors to them.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|


# General

<!-- ChanceCeiling-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ChanceCeiling|
|:----|:----|
|Tag Format:|`[ChanceCeiling:Value]`|
|Description:|This tag specifies the maximum value to use when applying a chance tag to an encounter type. Example: If this tag was set to `200` and you had a `SpaceCargoShipChance` tag set to `100`, then that encounter would have a 50% chance of appearing.|
|Allowed Values:|Any Integer Greater Than `0`|
|Default Value(s):|`100`|
|Multiple Tag Allowed:|No|

<!-- ForceStaticGrid  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ForceStaticGrid|
|:----|:----|
|Tag Format:|`[ForceStaticGrid:Value]`|
|Description:|This tag specifies if a SpawnGroup should be set to static when spawned.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- RotateFirstCockpitToForward  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RotateFirstCockpitToForward|
|:----|:----|
|Tag Format:|`[RotateFirstCockpitToForward:Value]`|
|Description:|This tag allows you to specify if a grid should be spawned with its first valid cockpit facing the spawn travel path.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`true`|
|Multiple Tag Allowed:|No|

<!-- SpawnRandomCargo  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SpawnRandomCargo|
|:----|:----|
|Tag Format:|`[SpawnRandomCargo:Value]`|
|Description:|This tag specifies if the ship should spawn with random cargo in specified containers. This is the same system as what is used in the ContainerTypes.sbc file.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`true`|
|Multiple Tag Allowed:|No|

<!-- DisableDampeners  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|DisableDampeners|
|:----|:----|
|Tag Format:|`[DisableDampeners:Value]`|
|Description:|This tag specifies whether or not the grid should spawn with Inertia Dampeners enabled or disabled.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- ReactorsOn  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ReactorsOn|
|:----|:----|
|Tag Format:|`[ReactorsOn:Value]`|
|Description:|This tag specifies if the grid should spawn with Reactors on or off.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`true`|
|Multiple Tag Allowed:|No|

<!-- RemoveVoxelsIfGridRemoved  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RemoveVoxelsIfGridRemoved|
|:----|:----|
|Tag Format:|`[RemoveVoxelsIfGridRemoved:Value]`|
|Description:|This tag specifies if any Voxels that are spawned with the encounter should be removed if the grid is no longer present (only works for Random Encounters and Planetary Installations).|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`true`|
|Multiple Tag Allowed:|No|


# Cost

<!-- UseSandboxCounterCosts-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|UseSandboxCounterCosts|
|:----|:----|
|Tag Format:|`[UseSandboxCounterCosts:Value]`|
|Description:|This tag specifies if the SpawnGroup should check the values of specified Sandbox Counters. If the minimum values are met, then the spawn would become eligible and those values are then subtracted from the Sandbox Counters|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`true`|
|Multiple Tag Allowed:|No|

<!-- SandboxCounterCostNames-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SandboxCounterCostNames|
|:----|:----|
|Tag Format:|`[SandboxCounterCostNames:Value]`|
|Description:|This tag specifies the name of the Sandbox Counter you want to check the amount of. This tag should be paired with the `SandboxCounterCostAmounts` tag to prevent confusion.|
|Allowed Values:|Any Sandbox Counter Name|
|Default Value(s):|`N/A`|
|Multiple Tag Allowed:|Yes|

<!-- SandboxCounterCostAmounts-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SandboxCounterCostAmounts|
|:----|:----|
|Tag Format:|`[SandboxCounterCostAmounts:Value]`|
|Description:|This tag specifies the minimum Sandbox Counter value that must be met for the spawn to be eligible. This is also the amount that will be subtracted from the counter at spawn. This tag should be paired with the `SandboxCounterCostNames` tag to prevent confusion.|
|Allowed Values:|Any Integer Greater or Equal to `0`|
|Default Value(s):|`0`|
|Multiple Tag Allowed:|Yes|


# Economy

<!-- UsePlayerCredits  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|UsePlayerCredits|
|:----|:----|
|Tag Format:|`[UsePlayerCredits:Value]`|
|Description:|This tag allows you to specify if a check should be done to determine how many Space Credits (currency) one or more players in the spawn area have before allowing the spawn.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- IncludeAllPlayersInRadius  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|IncludeAllPlayersInRadius|
|:----|:----|
|Tag Format:|`[IncludeAllPlayersInRadius:Value]`|
|Description:|This tag allows you to specify if all players within an area are counted when calculating how many credits players have.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- IncludeFactionBalance  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|IncludeFactionBalance|
|:----|:----|
|Tag Format:|`[IncludeFactionBalance:Value]`|
|Description:|This tag allows you to specify if player Faction Credit Balance should also be considered when calculating how many credits players have.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- PlayerCreditsCheckRadius  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|PlayerCreditsCheckRadius|
|:----|:----|
|Tag Format:|`[PlayerCreditsCheckRadius:Value]`|
|Description:|This tag allows you to specify the distance from the proposed spawn location that is checked for players when calculating total credits.|
|Allowed Values:|Any Number Greater Than `0`|
|Default Value(s):|`15000`|
|Multiple Tag Allowed:|No|

<!-- MinimumPlayerCredits  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|MinimumPlayerCredits|
|:----|:----|
|Tag Format:|`[MinimumPlayerCredits:Value]`|
|Description:|This tag specifies the minimum amount of credits that player(s) must have before the SpawnGroup is allowed to spawn.|
|Allowed Values:|Any Number Equal or Greater Than `0`<br>Value Should Be Lower Than `MaximumPlayerCredits` If Tag is Provided|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|

<!-- MaximumPlayerCredits  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|MaximumPlayerCredits|
|:----|:----|
|Tag Format:|`[MaximumPlayerCredits:Value]`|
|Description:|This tag specifies the maximum amount of credits that player(s) must have before the SpawnGroup is allowed to spawn.|
|Allowed Values:|Any Number Equal or Greater Than `0`<br>Value Should Be Higher Than `MinimumPlayerCredits` If Tag is Provided|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|


# Known-Player-Location

<!-- UseKnownPlayerLocations  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|UseKnownPlayerLocations|
|:----|:----|
|Tag Format:|`[UseKnownPlayerLocations:Value]`|
|Description:|This tag specifies if a SpawnGroup should only spawn if the area was designated as a 'Player Known Location' (by RivalAI or other mod).|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- KnownPlayerLocationMustMatchFaction  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|KnownPlayerLocationMustMatchFaction|
|:----|:----|
|Tag Format:|`[KnownPlayerLocationMustMatchFaction:Value]`|
|Description:|This tag specifies if a SpawnGroup should only spawn in a Known Player Location if the 'FactionOwner' tag matches the faction of the created Location.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- KnownPlayerLocationMinSpawnedEncounters  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|KnownPlayerLocationMinSpawnedEncounters|
|:----|:----|
|Tag Format:|`[KnownPlayerLocationMinSpawnedEncounters:Value]`|
|Description:|This tag allows you to specify the Minimum number of spawns that must have occured in a Known Player Location before this SpawnGroup is allowed to spawn.|
|Allowed Values:|Any Number Equal or Greater Than `0`<br>Value should be lower than `KnownPlayerLocationMaxSpawnedEncounters` if tag is used.|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|

<!-- KnownPlayerLocationMaxSpawnedEncounters  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|KnownPlayerLocationMaxSpawnedEncounters|
|:----|:----|
|Tag Format:|`[KnownPlayerLocationMaxSpawnedEncounters:Value]`|
|Description:|This tag allows you to specify the Maximum number of spawns that are allowed to have occured in a Known Player Location before this SpawnGroup is allowed to spawn.|
|Allowed Values:|Any Number Equal or Greater Than `0`<br>Value should be higher than `KnownPlayerLocationMinSpawnedEncounters` if tag is used.|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|


# Mods

<!-- RequireAllMods  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RequireAllMods|
|:----|:----|
|Tag Format:|`[RequireAllMods:Value1,Value2,etc]`|
|Description:|This tag allows you to specify what mods must be loaded in the game world in order for a SpawnGroup to appear. If all mods provided are loaded, the SpawnGroup can appear. Mods are identified by their Steam Workshop IDs. If tag is not included, then no mods requirements will be used by default.|
|Allowed Values:|Any Steam Workshop ID<br>If providing multiple values, use comma with no spaces as shown in `Tag Format`|
|Default Value(s):|`none`|
|Multiple Tag Allowed:|No|

<!-- RequireAnyMods  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RequireAnyMods|
|:----|:----|
|Tag Format:|`[RequireAnyMods:Value1,Value2,etc]`|
|Description:|This tag allows you to specify what mods must be loaded in the game world in order for a SpawnGroup to appear. If any of the mods provided are loaded, the SpawnGroup can appear.|
|Allowed Values:|Any Steam Workshop ID<br>If providing multiple values, use comma with no spaces as shown in `Tag Format`|
|Default Value(s):|`none`|
|Multiple Tag Allowed:|No|

<!-- ExcludeAllMods  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ExcludeAllMods|
|:----|:----|
|Tag Format:|`[ExcludeAllMods:Value1,Value2,etc]`|
|Description:|This tag allows you to specify what mods cannot be loaded in the game world in order for a SpawnGroup to appear. If all mods provided are not loaded, this Spawn Group can appear.|
|Allowed Values:|Any Steam Workshop ID<br>If providing multiple values, use comma with no spaces as shown in `Tag Format`|
|Default Value(s):|`none`|
|Multiple Tag Allowed:|No|

<!-- ExcludeAnyMods  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ExcludeAnyMods|
|:----|:----|
|Tag Format:|`[ExcludeAnyMods:Value1,Value2,etc]`|
|Description:|This tag allows you to specify what mods cannot be loaded in the game world in order for a SpawnGroup to appear. If any of the mods provided are not loaded, this SpawnGroup can appear.|
|Allowed Values:|Any Steam Workshop ID<br>If providing multiple values, use comma with no spaces as shown in `Tag Format`|
|Default Value(s):|`none`|
|Multiple Tag Allowed:|No|

<!-- ModBlockExists  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ModBlockExists|
|:----|:----|
|Tag Format:|`[ModBlockExists:Value1,Value2,etc]`|
|Description:|This tag allows you to specify one or more Block SubtypeIds that must be present in the game session for the SpawnGroup to be able to appear.|
|Allowed Values:|Any Modded Block SubtypeId<br>If providing multiple values, use comma with no spaces as shown in `Tag Format`|
|Default Value(s):|`none`|
|Multiple Tag Allowed:|No|


# Planetary

<!-- MinAirDensity  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|MinAirDensity|
|:----|:----|
|Tag Format:|`[MinAirDensity:Value]`|
|Description:|This tag allows you to specify the minimum Air Density at the spawn coordinates before it is allowed to spawn.|
|Allowed Values:|Floating Point Value Between `0` and `1`<br>Value must be lower than `MaxAirDensity` if tag is used.|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|

<!-- MaxAirDensity  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|MaxAirDensity|
|:----|:----|
|Tag Format:|`[MaxAirDensity:Value]`|
|Description:|This tag allows you to specify the maximum Air Density at the spawn coordinates before it is allowed to spawn.|
|Allowed Values:|Floating Point Value Between `0` and `1`<br>Value must be higher than `MinAirDensity` if tag is used.|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|

<!-- MinGravity  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|MinGravity|
|:----|:----|
|Tag Format:|`[MinGravity:Value]`|
|Description:|This tag allows you to specify the minimum Gravity at the spawn coordinates before it is allowed to spawn.|
|Allowed Values:|Floating Point Value Between `0` and `1`<br>Value must be lower than `MaxGravity` if tag is used.|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|

<!-- MaxGravity  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|MaxGravity|
|:----|:----|
|Tag Format:|`[MaxGravity:Value]`|
|Description:|This tag allows you to specify the maximum Gravity at the spawn coordinates before it is allowed to spawn.|
|Allowed Values:|Floating Point Value Between `0` and `1`<br>Value must be higher than `MinGravity` if tag is used.|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|

<!-- MinSpawnFromPlanetSurface  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|MinSpawnFromPlanetSurface|
|:----|:----|
|Tag Format:|`[MinSpawnFromPlanetSurface:Value]`|
|Description:|This tag allows you to specify how far from the nearest planet's surface the player must be before this encounter can spawn. If the player is within this distance, the encounter will not appear.|
|Allowed Values:|Any Number Greater Than `0`<br>Value must be lower than `MaxSpawnFromPlanetSurface` if tag is used|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|

<!-- MaxSpawnFromPlanetSurface  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|MaxSpawnFromPlanetSurface|
|:----|:----|
|Tag Format:|`[MaxSpawnFromPlanetSurface:Value]`|
|Description:|This tag allows you to specify how far from the nearest planet's surface the player must be within for this encounter can spawn. If the player is further than this distance, the encounter will not appear.|
|Allowed Values:|Any Number Greater Than `0`<br>Value must be higher than `MinSpawnFromPlanetSurface` if tag is used|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|

<!-- MinWaterDepth  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|MinWaterDepth|
|:----|:----|
|Tag Format:|`[MinWaterDepth:Value]`|
|Description:|This tag allows you to specify how deep underwater an encounter must spawn if eligible to spawn udnerwater. This is used with the [Water Mod](https://steamcommunity.com/sharedfiles/filedetails/?id=2200451495) by Jakaria|
|Allowed Values:|Any Number Greater Than `0`|
|Default Value(s):|`0`|
|Multiple Tag Allowed:|No|

<!-- UseDayOrNightOnly  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|UseDayOrNightOnly|
|:----|:----|
|Tag Format:|`[UseDayOrNightOnly:Value]`|
|Description:|This tag will specify if a spawn should only appear if it is either day or night on a planet (specified in `SpawnOnlyAtNight`).|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- SpawnOnlyAtNight  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SpawnOnlyAtNight|
|:----|:----|
|Tag Format:|`[SpawnOnlyAtNight:Value]`|
|Description:|This tag will specify if a spawn should only appear at night on a planet if `true`, otherwise it will only appear during the day if `false`.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- UseWeatherSpawning  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|UseWeatherSpawning|
|:----|:----|
|Tag Format:|`[UseWeatherSpawning:Value]`|
|Description:|This tag will specify if a spawn should only appear while the player is inside of one or more specified Weather events.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- AllowedWeatherSystems  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|AllowedWeatherSystems|
|:----|:----|
|Tag Format:|`[AllowedWeatherSystems:Value1,Value2,etc]`|
|Description:|This tag allows you to specify what weather systems are valid for spawning if `UseWeatherSpawning` is enabled.|
|Allowed Values:|Any Weather SubtypeId<br>If providing multiple values, use comma with no spaces as shown in `Tag Format`|
|Default Value(s):|`none`|
|Multiple Tag Allowed:|No|

<!-- UseTerrainTypeValidation  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|UseTerrainTypeValidation|
|:----|:----|
|Tag Format:|`[UseTerrainTypeValidation:Value]`|
|Description:|This tag will specify if a spawn should only appear while the player is in an area that contains a certain type of terrain. Terrain is check in random spots around the player, and the most commonly found is what is considered for spawning purposes.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- AllowedTerrainTypes  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|AllowedTerrainTypes|
|:----|:----|
|Tag Format:|`[AllowedTerrainTypes:Value1,Value2,etc]`|
|Description:| This tag allows you to specify what terrain types near the player are valid for spawning if `UseTerrainTypeValidation` is enabled.|
|Allowed Values:|Any Voxel Material SubtypeId<br>Acceptable values can be found in VoxelMaterials_planetary.sbc Game File<br>If providing multiple values, use comma with no spaces as shown in `Tag Format`<br>`false`|
|Default Value(s):|`none`|
|Multiple Tag Allowed:|No|

<!-- PlanetBlacklist  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|PlanetBlacklist|
|:----|:----|
|Tag Format:|`[PlanetBlacklist:Value1,Value2,etc]`|
|Description:|This tag allows you to specify what planets the encounter is not allow to spawn on/near (for applicable encounters).|
|Allowed Values:|Any Planet SubtypeId<br>If providing multiple values, use comma with no spaces as shown in `Tag Format`|
|Default Value(s):|`none`|
|Multiple Tag Allowed:|No|

<!-- PlanetWhitelist  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|PlanetWhitelist|
|:----|:----|
|Tag Format:|`[PlanetWhitelist:Value1,Value2,etc]`|
|Description:|This tag allows you to specify what planets the encounter will only spawn on/near (for applicable encounters).|
|Allowed Values:|Any Planet SubtypeId<br>If providing multiple values, use comma with no spaces as shown in `Tag Format`|
|Default Value(s):|`none`|
|Multiple Tag Allowed:|No|

<!-- PlanetRequiresVacuum  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|PlanetRequiresVacuum|
|:----|:----|
|Tag Format:|`[PlanetRequiresVacuum:Value]`|
|Description:|This tag will restrict the SpawnGroup to only spawn on/near planets without atmosphere.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- PlanetRequiresAtmo  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|PlanetRequiresAtmo|
|:----|:----|
|Tag Format:|`[PlanetRequiresAtmo:Value]`|
|Description:|This tag will restrict the SpawnGroup to only spawn on/near planets with atmosphere.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- PlanetRequiresOxygen  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|PlanetRequiresOxygen|
|:----|:----|
|Tag Format:|`[PlanetRequiresOxygen:Value]`|
|Description:|This tag will restrict the SpawnGroup to only spawn on/near planets with atmosphere and breathable oxygen.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- PlanetMinimumSize  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|PlanetMinimumSize|
|:----|:----|
|Tag Format:|`[PlanetMinimumSize:Value]`|
|Description:|This tag will restrict the SpawnGroup to only spawn on/near planets larger than the provided diameter (in meters).|
|Allowed Values:|Any Number Greater Than `0`<br>Value Should Be Lower Than `PlanetMaximumSize` If Tag is Provided|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|

<!-- PlanetMaximumSize  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|PlanetMaximumSize|
|:----|:----|
|Tag Format:|`[PlanetMaximumSize:Value]`|
|Description:|This tag will restrict the SpawnGroup to only spawn on/near planets no larger than the provided diameter (in meters).|
|Allowed Values:|Any Number Greater Than `0`<br>Value Should Be Higher Than `PlanetMinimumSize` If Tag is Provided|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|


# Players

<!-- UsePlayerCountCheck  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|UsePlayerCountCheck|
|:----|:----|
|Tag Format:|`[UsePlayerCountCheck:Value]`|
|Description:|This tag allows you to specify if the spawner should do a count of the active players in the area or in the game world before spawning.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- PlayerCountCheckRadius  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|PlayerCountCheckRadius|
|:----|:----|
|Tag Format:|`[PlayerCountCheckRadius:Value]`|
|Description:|This tag allows you to specify the radius from the spawn area that the spawner should check for active players. If this tag is not used, then it will count all players currently online.|
|Allowed Values:|Any Number Greater Than `0`|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|

<!-- MinimumPlayers  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|MinimumPlayers|
|:----|:----|
|Tag Format:|`[MinimumPlayers:Value]`|
|Description:|This tag specifies the minimum amount of players that need to be detected to allow the spawn.|
|Allowed Values:|Any Number Greater Than `0`<br>Value Should Be Lower Than `MaximumPlayers` If Tag is Provided|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|

<!-- MaximumPlayers  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|MaximumPlayers|
|:----|:----|
|Tag Format:|`[MaximumPlayers:Value]`|
|Description:|This tag specifies the maximum amount of players that need to be detected to allow the spawn.|
|Allowed Values:|Any Number Greater Than `0`<br>Value Should Be Higher Than `MinimumPlayers` If Tag is Provided|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|

<!-- RequiredPlayersOnline  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RequiredPlayersOnline|
|:----|:----|
|Tag Format:|`[RequiredPlayersOnline:Value1]`|
|Description:|This tag allows you to specify one or more PLayer Steam User IDs that must be online in the game session for the SpawnGroup to be able to appear. If all the listed players are online, then the spawn is eligible|
|Allowed Values:|Any Steam User Id (64 bit)|
|Default Value(s):|`none`|
|Multiple Tag Allowed:|Yes|

<!-- RequiredAnyPlayersOnline-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RequiredAnyPlayersOnline|
|:----|:----|
|Tag Format:|`[RequiredAnyPlayersOnline:Value1]`|
|Description:|This tag allows you to specify one or more PLayer Steam User IDs that must be online in the game session for the SpawnGroup to be able to appear. If any of the listed players are online, then the spawn is eligible.|
|Allowed Values:|Any Steam User Id (64 bit)|
|Default Value(s):|`none`|
|Multiple Tag Allowed:|Yes|


# Reputation

<!-- UsePlayerFactionReputation  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|UsePlayerFactionReputation|
|:----|:----|
|Tag Format:|`[UsePlayerFactionReputation:Value]`|
|Description:|This tag specifies if player reputation should be considered when spawning a SpawnGroup nearby. If any player meets the conditions you provide, the SpawnGroup will be valid for spawn.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- PlayerReputationCheckRadius  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|PlayerReputationCheckRadius|
|:----|:----|
|Tag Format:|`[PlayerReputationCheckRadius:Value]`|
|Description:|This tag allows you to specify the distance from the proposed spawn location that is checked for players when checking reputation.|
|Allowed Values:|Any Number Greater Than `0`|
|Default Value(s):|`15000`|
|Multiple Tag Allowed:|No|

<!-- CheckReputationAgainstOtherNPCFaction  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|CheckReputationAgainstOtherNPCFaction|
|:----|:----|
|Tag Format:|`[CheckReputationAgainstOtherNPCFaction:Value]`|
|Description:|This tag allows you to provide a separate faction Tag to check reputation against instead of the faction this SpawnGroup would use.|
|Allowed Values:|Any FactionTag|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- MinimumReputation  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|MinimumReputation|
|:----|:----|
|Tag Format:|`[MinimumReputation:Value]`|
|Description:|This tag allows you to specify the Minimum Reputation a player must have for the SpawnGroup to be able to spawn.|
|Allowed Values:|Any Number Between `-1500` and `1500`<br>Value Should Be Lower Than `MaximumReputation` If Tag is Provided|
|Default Value(s):|`-1501`|
|Multiple Tag Allowed:|No|

<!-- MaximumReputation  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|MaximumReputation|
|:----|:----|
|Tag Format:|`[MaximumReputation:Value]`|
|Description:|This tag allows you to specify the Maximum Reputation a player must have for the SpawnGroup to be able to spawn.|
|Allowed Values:|Any Number Between `-1500` and `1500`<br>Value Should Be Higher Than `MinimumReputation` If Tag is Provided|
|Default Value(s):|`1501`|
|Multiple Tag Allowed:|No|


# Restrictions

<!-- UniqueEncounter  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|UniqueEncounter|
|:----|:----|
|Tag Format:|`[UniqueEncounter:Value]`|
|Description:|This tag specifies if a SpawnGroup should only spawn once per world instance. After the group spawns, it would not be selected for spawning again.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- AdminSpawnOnly  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|AdminSpawnOnly|
|:----|:----|
|Tag Format:|`[AdminSpawnOnly:Value]`|
|Description:|This tag specifies if a SpawnGroup should only be spawned when an admin triggers the spawn via chat command.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- UseRemoteControlCodeRestrictions -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|UseRemoteControlCodeRestrictions|
|:----|:----|
|Tag Format:|`[UseRemoteControlCodeRestrictions:Value]`|
|Description:|This tag specifies if a SpawnGroup should check the area for active Remote Control blocks that have registered a specific code, and then apply a Min/Max distance requirement from that block to determine eligiblility.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- RemoteControlCode-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RemoteControlCode|
|:----|:----|
|Tag Format:|`[RemoteControlCode:Value]`|
|Description:|This tag specifies the Remote Control code that will be searched for if you've enabled the `UseRemoteControlCodeRestrictions` tag.|
|Allowed Values:|Any Remote Control Code Name|
|Default Value(s):|`none`|
|Multiple Tag Allowed:|No|

<!-- RemoteControlCodeMinDistance-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RemoteControlCodeMinDistance|
|:----|:----|
|Tag Format:|`[RemoteControlCodeMinDistance:Value]`|
|Description:|This tag specifies the minimum distance from an eligible Remote Control block that this SpawnGroup is allowed to spawn at if you've enabled the `UseRemoteControlCodeRestrictions` tag. If tag is not provided, or a value of `-1` is used, then minimum distance is not considered.|
|Allowed Values:|Any Number Greater or Equal to `-1`<br />Must be `less` than `RemoteControlCodeMaxDistance` if tag exists|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|

<!-- RemoteControlCodeMaxDistance-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RemoteControlCodeMaxDistance|
|:----|:----|
|Tag Format:|`[RemoteControlCodeMaxDistance:Value]`|
|Description:|This tag specifies the maximum distance from an eligible Remote Control block that this SpawnGroup is allowed to spawn at if you've enabled the `UseRemoteControlCodeRestrictions` tag. If tag is not provided, or a value of `-1` is used, then maximum distance is not considered.|
|Allowed Values:|Any Number Greater or Equal to `-1`<br />Must be `greater` than `RemoteControlCodeMinDistance` if tag exists|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|


# Settings


# Threat

<!-- UseThreatLevelCheck  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|UseThreatLevelCheck|
|:----|:----|
|Tag Format:|`[UseThreatLevelCheck:Value]`|
|Description:|This tag will restrict the SpawnGroup to only spawn if the threat level near a player is within specified parameters. Threat score is specified in `ThreatScoreMinimum` and `ThreatScoreMaximum`. For more information on how Threat Scoring works, [Click Here](https://gist.github.com/MeridiusIX/52fbf5679e67107a8cf37706205b5812).|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- ThreatLevelCheckRange  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ThreatLevelCheckRange|
|:----|:----|
|Tag Format:|`[ThreatLevelCheckRange:Value]`|
|Description:|This tag specifies the radius (in meters) near the player that will be scanned by the spawner to determine the player threat level.|
|Allowed Values:|Any Number Greater Than `0`|
|Default Value(s):|`5000`|
|Multiple Tag Allowed:|No|

<!-- ThreatIncludeOtherNpcOwners  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ThreatIncludeOtherNpcOwners|
|:----|:----|
|Tag Format:|`[ThreatIncludeOtherNpcOwners:Value]`|
|Description:|This tag specifies if a threat scan should also include grids owned by other NPCs in the scan radius.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- ThreatScoreMinimum  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ThreatScoreMinimum|
|:----|:----|
|Tag Format:|`[ThreatScoreMinimum:Value]`|
|Description:|This tag allows you to specify the minimum threat score within the player area before the spawn group is able to spawn. If the score is lower, then the spawn group will not appear.|
|Allowed Values:|Any Number Greater Than `0`<br>Value Should Be Lower Than `ThreatScoreMaximum` If Tag is Provided|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|

<!-- ThreatScoreMaximum  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ThreatScoreMaximum|
|:----|:----|
|Tag Format:|`[ThreatScoreMaximum:Value]`|
|Description:|This tag allows you to specify the maximum threat score within the player area before the spawn group is able to spawn. If the score is higher, then the spawn group will not appear.|
|Allowed Values:|Any Number Greater Than `0`<br>Value Should Be Higher Than `ThreatScoreMinimum` If Tag is Provided|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|

<!-- UsePCUCheck  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|UsePCUCheck|
|:----|:----|
|Tag Format:|`[UsePCUCheck:Value]`|
|Description:|This tag will restrict the SpawnGroup to only spawn if the PCU total near a player is within specified parameters. PCU score is specified in `PCUMinimum` and `PCUMaximum`.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- PCUCheckRadius  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|PCUCheckRadius|
|:----|:----|
|Tag Format:|`[PCUCheckRadius:Value]`|
|Description:|This tag specifies the radius (in meters) near the player that will be scanned by the spawner to determine the PCU level.|
|Allowed Values:|Any Number Greater Than `0`|
|Default Value(s):|`5000`|
|Multiple Tag Allowed:|No|

<!-- PCUMinimum  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|PCUMinimum|
|:----|:----|
|Tag Format:|`[PCUMinimum:Value]`|
|Description:|This tag allows you to specify the minimum PCU score within the player area before the spawn group is able to spawn. If the score is lower, then the spawn group will not appear.|
|Allowed Values:|Any Number Greater Than `0`<br>Value Should Be Lower Than `PCUMaximum` If Tag is Provided|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|

<!-- PCUMaximum  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|PCUMaximum|
|:----|:----|
|Tag Format:|`[PCUMaximum:Value]`|
|Description:|This tag allows you to specify the maximum PCU score within the player area before the spawn group is able to spawn. If the score is higher, then the spawn group will not appear.|
|Allowed Values:|Any Number Greater Than `0`<br>Value Should Be Higher Than `PCUMinimum` If Tag is Provided|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|


# Variables

<!-- SandboxVariables  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SandboxVariables|
|:----|:----|
|Tag Format:|`[SandboxVariables:Value1,Value2,Value3,etc]`|
|Description:| This tag allows you to specify the names of Sandbox Boolean Varibles (via IMyUtilities) that must be `true` in order for the group to spawn.|
|Allowed Values:|Any Variable Name<br>If providing multiple values, use comma with no spaces as shown in `Tag Format`|
|Default Value(s):|`none`|
|Multiple Tag Allowed:|No|

<!-- FalseSandboxVariables-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|FalseSandboxVariables|
|:----|:----|
|Tag Format:|`[FalseSandboxVariables:Value1,Value2,Value3,etc]`|
|Description:| This tag allows you to specify the names of Sandbox Boolean Varibles (via IMyUtilities) that must be `false` in order for the group to spawn. If the Sandbox variable is not defined yet, this counts as `false` as well.|
|Allowed Values:|Any Variable Name<br>If providing multiple values, use comma with no spaces as shown in `Tag Format`|
|Default Value(s):|`none`|
|Multiple Tag Allowed:|No|

<!-- AttachModStorageComponentToGrid  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|AttachModStorageComponentToGrid|
|:----|:----|
|Tag Format:|`[AttachModStorageComponentToGrid:Value]`|
|Description:|This tag allows you to specify whether or not a custom ModStorageComponent Dictionary Key/Value should be added to your grid(s). Please ensure that the Guid you plan to use is also defined in your mod's EntityContainers.sbc file.|
|Allowed Values:|`true`<br>`false`|
|Default Value(s):|`false`|
|Multiple Tag Allowed:|No|

<!-- StorageKey  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|StorageKey|
|:----|:----|
|Tag Format:|`[StorageKey:Value]`|
|Description:|If `AttachModStorageComponentToGrid` is set to true, this tag will allow you to specify the Guid that is used as the Key in your Key/Value entry.|
|Allowed Values:|Any valid Guid String<br>eg `F778FB78-3400-44A8-AEF4-16B5525A0B54`|
|Default Value(s):|`none`|
|Multiple Tag Allowed:|No|

<!-- StorageValue  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|StorageValue|
|:----|:----|
|Tag Format:|`[StorageValue:Value]`|
|Description:| If `AttachModStorageComponentToGrid` is set to true, this tag will allow you to specify the String that is used as the Value in your Key/Value entry.|
|Allowed Values:|Any String Value|
|Default Value(s):|`none`|
|Multiple Tag Allowed:|No|


# World

<!-- MinSpawnFromWorldCenter  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|MinSpawnFromWorldCenter|
|:----|:----|
|Tag Format:|`[MinSpawnFromWorldCenter:Value]`|
|Description:|This tag allows you to specify how far from the world center (0,0,0) the player must be before this encounter can spawn. If the player is within this distance, the encounter will not appear.|
|Allowed Values:|Any Number Greater Than `0`<br>Value must be lower than `MaxSpawnFromWorldCenter` if tag is used|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|

<!-- MaxSpawnFromWorldCenter  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|MaxSpawnFromWorldCenter|
|:----|:----|
|Tag Format:|`[MaxSpawnFromWorldCenter:Value]`|
|Description:|This tag allows you to specify how far from the world center (0,0,0) the player must be within for this encounter can spawn. If the player is further than this distance, the encounter will not appear.|
|Allowed Values:|Any Number Greater Than `0`<br>Value must be higher than `MinSpawnFromWorldCenter` if tag is used|
|Default Value(s):|`-1`|
|Multiple Tag Allowed:|No|


# Zone










