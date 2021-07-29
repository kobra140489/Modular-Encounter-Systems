Action Profiles in Rival AI are used in conjunction with **Trigger Profiles**. These profile are what execute specified actions when the conditions in a Trigger Profile are satisfied. It is important that you use a unique SubtypeId for each Action Profile you create, otherwise they may not work correctly.

Here is an example of how an Action Profile definition is setup:

```
<?xml version="1.0"?>
<Definitions xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <EntityComponents>

    <EntityComponent xsi:type="MyObjectBuilder_InventoryComponentDefinition">
      <Id>
          <TypeId>Inventory</TypeId>
          <SubtypeId>RAI-ExampleActionProfile</SubtypeId>
      </Id>
      <Description>

      [RivalAI Action]
      
      [UseChatBroadcast:true]
      [ChatData:RAI-ExampleChatProfile]
	
      [CreateKnownPlayerArea:true]
      [KnownPlayerAreaRadius:15000]
      [KnownPlayerAreaTimer:30]

      </Description>
      
    </EntityComponent>

  </EntityComponents>
</Definitions>
```

Below are the tags you are able to use in your Action Profiles. They are divided into several categories based on what they affect.

**[Behavior](#Behavior)**  
**[Blocks](#Blocks)**  
**[Communication](#Communication)**  
**[Damage](#Damage)**   
**[Effects](#Effects)**  
**[General](#General)**  
**[Grid](#Grid)**  
**[Inventory](#Inventory)**  
**[Reputation](#Reputation)**  
**[Spawning](#Spawning)**  
**[Targeting](#Targeting)**  
**[Trigger](#Trigger)**  
**[Variables](#Variables)**  

***

# Behavior

This section contains actions that relate to changes that can be made to the behavior and auto-pilot.

<!--ChangeAutopilotSpeed  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ChangeAutopilotSpeed|
|:----|:----|
|Tag Format:|`[ChangeAutopilotSpeed:Value]`|
|Description:|This tag specifies if the AutoPilot speed of the current NPC should be changed to a new value.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--NewAutopilotSpeed  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|NewAutopilotSpeed|
|:----|:----|
|Tag Format:|`[NewAutopilotSpeed:Value]`|
|Description:|Specifies the new AutoPilot speed if `ChangeAutopilotSpeed` was set to `true`.|
|Allowed Values:|Any number equal/higher than `0`|
|Multiple Tag Allowed:|No|

<!--ChangeInertiaDampeners  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ChangeInertiaDampeners|
|:----|:----|
|Tag Format:|`[ChangeInertiaDampeners:Value]`|
|Description:|This tag specifies if the AutoPilot should enable or disable the Inertia Dampeners (may only work with some behaviors / modes).|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--InertiaDampenersEnable  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|InertiaDampenersEnable|
|:----|:----|
|Tag Format:|`[InertiaDampenersEnable:Value]`|
|Description:|Specifies the new Inertia Dampeners mode if `ChangeInertiaDampeners` was set to `true`.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--BarrelRoll  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|BarrelRoll|
|:----|:----|
|Tag Format:|`[BarrelRoll:Value]`|
|Description:|This tag specifies if the NPC should perform a roll for a short time. Barrel Roll controls can be found in the Autopilot Profile tags section.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--Ramming  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Ramming|
|:----|:----|
|Tag Format:|`[Ramming:Value]`|
|Description:|This tag specifies if the NPC should attempt to ram a target for a short time. Ramming controls can be found in the Autopilot Profile tags section.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--Retreat  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Retreat|
|:----|:----|
|Tag Format:|`[Retreat:Value]`|
|Description:|This tag specifies if the Retreat function should be activated in the current behavior.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--RecalculateDespawnCoords-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RecalculateDespawnCoords|
|:----|:----|
|Tag Format:|`[RecalculateDespawnCoords:Value]`|
|Description:|This tag specifies if the NPC should recalculate its Despawn Coordinates if it is using coordinates retrieved from MES or generated within RivalAI. The newly generated coordinates will be created from data in the Active Autopilot Profile of the behavior.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--ForceDespawn  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ForceDespawn|
|:----|:----|
|Tag Format:|`[ForceDespawn:Value]`|
|Description:|This tag specifies if the NPC grid should immediately be despawned.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--TerminateBehavior  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|TerminateBehavior|
|:----|:----|
|Tag Format:|`[TerminateBehavior:Value]`|
|Description:|This tag specifies if the current NPC Behavior should be terminated (meaning no more AI processing from that behavior).|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--ChangeRotationDirection  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ChangeRotationDirection|
|:----|:----|
|Tag Format:|`[ChangeRotationDirection:Value]`|
|Description:|This tag specifies if the ship should use a different direction when rotating towards a target. Specify direction using the `RotationDirection` tag|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--RotationDirection  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RotationDirection|
|:----|:----|
|Tag Format:|`[RotationDirection:Value]`|
|Description:|This tag specifies the direction a ship should use when rotating towards a target if `ChangeRotationDirection` is `true`.|
|Allowed Values:|`Forward`<br>`Backward`<br>`Up`<br>`Down`<br>`Left`<br>`Right`|
|Multiple Tag Allowed:|No|

<!--SwitchToBehavior  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SwitchToBehavior|
|:----|:----|
|Tag Format:|`[SwitchToBehavior:Value]`|
|Description:|This tag specifies if the Behavior should switch to a new behavior profile. |
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--NewBehavior  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|NewBehavior|
|:----|:----|
|Tag Format:|`[NewBehavior:Value]`|
|Description:|This tag specifies the ID of the new Behavior Profile that will be used if `SwitchToBehavior` is `true`. |
|Allowed Values:|SubtypeId of New Behavior Profile|
|Multiple Tag Allowed:|No|

<!--PreserveSettingsOnBehaviorSwitch  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|PreserveSettingsOnBehaviorSwitch|
|:----|:----|
|Tag Format:|`[PreserveSettingsOnBehaviorSwitch:Value]`|
|Description:|This tag specifies if the settings from a behavior (stored booleans, counters, etc) should be preserved and used in the new behavior if `SwitchToBehavior` is `true`. |
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--PreserveTriggersOnBehaviorSwitch  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|PreserveTriggersOnBehaviorSwitch|
|:----|:----|
|Tag Format:|`[PreserveTriggersOnBehaviorSwitch:Value]`|
|Description:|This tag specifies if the trigger profiles from a behavior should be preserved and used in the new behavior if `SwitchToBehavior` is `true`. |
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--PreserveTargetDataOnBehaviorSwitch  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|PreserveTargetDataOnBehaviorSwitch|
|:----|:----|
|Tag Format:|`[PreserveTargetDataOnBehaviorSwitch:Value]`|
|Description:|This tag specifies if the target profile from a behavior should be preserved and used in the new behavior if `SwitchToBehavior` is `true`. |
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--ChangeAutopilotProfile-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ChangeAutopilotProfile|
|:----|:----|
|Tag Format:|`[ChangeAutopilotProfile:Value]`|
|Description:|This tag specifies if the Autopilot Profile should be switched to another mode, using another attached Autopilot Profile. |
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--AutopilotProfile-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|AutopilotProfile|
|:----|:----|
|Tag Format:|`[AutopilotProfile:Value]`|
|Description:|This tag specifies the Autopilot Profile Mode that should be switched to. |
|Allowed Values:|`Primary`<br>`Secondary`<br>`Tertiary`|
|Multiple Tag Allowed:|No|

<!--StopAllRotation-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|StopAllRotation|
|:----|:----|
|Tag Format:|`[StopAllRotation:Value]`|
|Description:|This tag will set all Gyroscope Overrides to `0` on the NPC. This is useful when paired with a `Compromised` trigger to stop any gyros that may be stuck rotating when a RivalAI Remote Control is disabled.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--StopAllThrust-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|StopAllThrust|
|:----|:----|
|Tag Format:|`[StopAllThrust:Value]`|
|Description:|This tag will set all Thruster Overrides to `0` on the NPC. This is useful when paired with a `Compromised` trigger to stop any thrusters that may be stuck in override when a RivalAI Remote Control is disabled.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--RandomGyroRotation-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RandomGyroRotation|
|:----|:----|
|Tag Format:|`[RandomGyroRotation:Value]`|
|Description:|This tag will set a random Gyroscopic rotation and apply it to the NPC grid. This is useful when paired with a `Compromised` trigger.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--RandomThrustDirection-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RandomThrustDirection|
|:----|:----|
|Tag Format:|`[RandomThrustDirection:Value]`|
|Description:|This tag will set a random Thruster Override Strength and Direction, and apply it to the NPC grid. This is useful when paired with a `Compromised` trigger.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

***

# <a>Blocks</a>

This section contains actions that affect the state of blocks on the NPC grid.

<!--EnableBlocks  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|EnableBlocks|
|:----|:----|
|Tag Format:|`[EnableBlocks:Value]`|
|Description:|This tag specifies if certain blocks should be turned On or Off.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--EnableBlockNames  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|EnableBlockNames|
|:----|:----|
|Tag Format:|`[EnableBlockNames:Value]`|
|Description:|This tag specifies the name(s) of blocks that you want to toggle on or off.|
|Allowed Values:|Any Block Name|
|Multiple Tag Allowed:|Yes|

<!--EnableBlockStates  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|EnableBlockStates|
|:----|:----|
|Tag Format:|`[EnableBlockStates:Value]`|
|Description:|This tag specifies the On/Off state of blocks that you want to toggle on or off.|
|Allowed Values:|`Off`<br>`On`<br>`Toggle`|
|Multiple Tag Allowed:|Yes|

<!--ChangeAntennaRanges  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ChangeAntennaRanges|
|:----|:----|
|Tag Format:|`[ChangeAntennaRanges:Value]`|
|Description:|This tag specifies if attached antennas should have their range changed.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--AntennaNamesForRangeChange  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|AntennaNamesForRangeChange|
|:----|:----|
|Tag Format:|`[AntennaNamesForRangeChange:Value]`|
|Description:|This tag specifies the name of the antenna(s) that should have their ranges changed. If this tag is not provided, then all antennas will be affected|
|Allowed Values:|Any Antenna Name|
|Multiple Tag Allowed:|Yes|

<!--AntennaRangeChangeType  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|AntennaRangeChangeType|
|:----|:----|
|Tag Format:|`[AntennaRangeChangeType:Value]`|
|Description:|This tag specifies how the antenna range should be changed by using this value with the value of `AntennaRangeChangeAmount`.|
|Allowed Values:|`Set`<br />`Increase`<br />`Decrease`|
|Multiple Tag Allowed:|No|

<!--AntennaRangeChangeAmount  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|AntennaRangeChangeAmount|
|:----|:----|
|Tag Format:|`[AntennaRangeChangeAmount:Value]`|
|Description:|This tag specifies how much the antenna range should be changed by.|
|Allowed Values:|Any Number Greater Than `0`|
|Multiple Tag Allowed:|No|

<!--ChangeAntennaOwnership  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ChangeAntennaOwnership|
|:----|:----|
|Tag Format:|`[ChangeAntennaOwnership:Value]`|
|Description:|This tag specifies if Antenna Blocks on the current NPC grid should have their ownership changed.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--AntennaFactionOwner  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|AntennaFactionOwner|
|:----|:----|
|Tag Format:|`[AntennaFactionOwner:Value]`|
|Description:|Specifies the faction (by faction tag) that antenna blocks get changed to if `ChangeAntennaOwnership` is `true`.|
|Allowed Values:|Any Faction Tag|
|Multiple Tag Allowed:|No|

<!--ChangeBlockNames  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ChangeBlockNames|
|:----|:----|
|Tag Format:|`[ChangeBlockNames:Value]`|
|Description:|This tag specifies if blocks on the NPC grid should have their names changed.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--ChangeBlockNamesFrom  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ChangeBlockNamesFrom|
|:----|:----|
|Tag Format:|`[ChangeBlockNamesFrom:Value]`|
|Description:|This tag specifies a name of a Block that will have its name changed. Ideally you should place this tag before the `ChangeBlockNamesTo` tag, keeping them in pairs in your Action Profile.|
|Allowed Values:|Any text/string excluding `:`, `[`, `]`|
|Multiple Tag Allowed:|Yes|

<!--ChangeBlockNamesTo  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ChangeBlockNamesTo|
|:----|:----|
|Tag Format:|`[ChangeBlockNamesTo:Value]`|
|Description:|This tag specifies the name that a Block specified in `ChangeBlockNamesFrom` will be changed to. Ideally you should place this tag after the `ChangeBlockNamesFrom` tag, keeping them in pairs in your Action Profile.|
|Allowed Values:|Any text/string excluding `:`, `[`, `]`|
|Multiple Tag Allowed:|Yes|

<!--TriggerTimerBlocks  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|TriggerTimerBlocks|
|:----|:----|
|Tag Format:|`[TriggerTimerBlocks:Value]`|
|Description:|This tag specifies if select Timer Blocks on the current NPC grid should be Triggered.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--TimerBlockNames  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|TimerBlockNames|
|:----|:----|
|Tag Format:|`[TimerBlockNames:Value]`|
|Description:|This tag specifies a name of a Timer Block on the current NPC grid should be Triggered.|
|Allowed Values:|Any text/string excluding `:`, `[`, `]`|
|Multiple Tag Allowed:|Yes|

<!--SelfDestruct  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SelfDestruct|
|:----|:----|
|Tag Format:|`[SelfDestruct:Value]`|
|Description:|This tag specifies if all Warhead Blocks on the current NPC grid should be detonated.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!-- StaggerWarheadDetonation -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|StaggerWarheadDetonation|
|:----|:----|
|Tag Format:|`[StaggerWarheadDetonation:Value]`|
|Description:|This tag specifies if warheads should be detonated in 1 second intervals instead of all at once.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!-- SelfDestructTimerPadding -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SelfDestructTimerPadding|
|:----|:----|
|Tag Format:|`[SelfDestructTimerPadding:Value]`|
|Description:|This tag specifies the minimum time that all warheads will start at if countdown is initiated.|
|Allowed Values:|Any number greater or equal to `0`|
|Multiple Tag Allowed:|No|

<!-- SelfDestructTimeBetweenBlasts -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SelfDestructTimeBetweenBlasts|
|:----|:----|
|Tag Format:|`[SelfDestructTimeBetweenBlasts:Value]`|
|Description:|This tag specifies the time between detonations that is applied to warheads if `StaggerWarheadDetonation` is used.|
|Allowed Values:|Any number greater or equal to `0`|
|Multiple Tag Allowed:|No|

<!--ChangeBlockOwnership-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ChangeBlockOwnership|
|:----|:----|
|Tag Format:|`[ChangeBlockOwnership:Value]`|
|Description:|This tag specifies if some blocks should have their ownership changed. Block names and Faction Tags should be provided in the `OwnershipBlockNames` and `OwnershipBlockFactions` tags together.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--OwnershipBlockNames-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|OwnershipBlockNames|
|:----|:----|
|Tag Format:|`[OwnershipBlockNames:Value]`|
|Description:|This tag specifies a name of a Block that gets it's ownership changed.|
|Allowed Values:|Any text/string excluding `:`, `[`, `]`|
|Multiple Tag Allowed:|Yes|

<!--OwnershipBlockFactions-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|OwnershipBlockFactions|
|:----|:----|
|Tag Format:|`[OwnershipBlockFactions:Value]`|
|Description:|This tag specifies a name of a faction that a block ownership should be changed to.|
|Allowed Values:|Any Faction Tag|
|Multiple Tag Allowed:|Yes|

<!--RazeBlocksWithNames-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RazeBlocksWithNames|
|:----|:----|
|Tag Format:|`[RazeBlocksWithNames:Value]`|
|Description:|This tag specifies if some blocks should be destroyed on the NPC grid.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--RazeBlocksNames-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RazeBlocksNames|
|:----|:----|
|Tag Format:|`[RazeBlocksNames:Value]`|
|Description:|This tag specifies names of blocks that are destroyed when the action is executed.|
|Allowed Values:|Any Block Name|
|Multiple Tag Allowed:|Yes|

<!--ToggleBlocksOfType-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ToggleBlocksOfType|
|:----|:----|
|Tag Format:|`[ToggleBlocksOfType:Value]`|
|Description:|This tag specifies if blocks of a matching type should be set to on, off, or toggled from existing state.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--BlockTypesToToggle-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|BlockTypesToToggle|
|:----|:----|
|Tag Format:|`[BlockTypesToToggle:Value]`|
|Description:|This tag specifies the types of block that will be toggled. This tag needs to be paired with a `BlockTypeToggles` tag.|
|Allowed Values:|Any Block DefinitionID<br>Eg: `MyObjectBuilder_Parachute/LgParachute`|
|Multiple Tag Allowed:|Yes|

<!--BlockTypeToggles-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|BlockTypeToggles|
|:----|:----|
|Tag Format:|`[BlockTypeToggles:Value]`|
|Description:|This tag specifies the toggle action that will be applied to a block type. This tag needs to be paired with a `BlockTypesToToggle` tag.|
|Allowed Values:|`Off`<br>`On`<br>`Toggle`|
|Multiple Tag Allowed:|Yes|

<!--BuildProjectedBlocks-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|BuildProjectedBlocks|
|:----|:----|
|Tag Format:|`[BuildProjectedBlocks:Value]`|
|Description:|This tag specifies if a number of blocks currently being projected from the NPC Grid should be built instantly. The projection must already be active at the time this Action is activated (enabling the projector and using this action in the same profile may not work since there is a minor delay when the projection is being created in game).|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--MaxProjectedBlocksToBuild -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|MaxProjectedBlocksToBuild|
|:----|:----|
|Tag Format:|`[MaxProjectedBlocksToBuild:Value]`|
|Description:|Specifies the maximum number of blocks that are built if `BuildProjectedBlocks` is `true`. If this value is not defined, or the value is set to `-1`, then all currently eligible blocks will be built on the projection.|
|Allowed Values:|Any Integer higher than `-1`|
|Multiple Tag Allowed:|No|

***

# Communication

This section contains actions for NPC to NPC communication.

<!--UseChatBroadcast  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|UseChatBroadcast|
|:----|:----|
|Tag Format:|`[UseChatBroadcast:Value]`|
|Description:|This tag specifies if an attached Chat Profile should be activated.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--ChatData  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ChatData|
|:----|:----|
|Tag Format:|`[ChatData:Value]`|
|Description:|This tag specifies which Chat Profile should be activated if `UseChatBroadcast` is `true`.|
|Allowed Values:|Any Chat Profile SubtypeId|
|Multiple Tag Allowed:|Yes|

<!--BroadcastCommandProfiles-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|BroadcastCommandProfiles|
|:----|:----|
|Tag Format:|`[BroadcastCommandProfiles:Value]`|
|Description:|This tag specifies if the Behavior should broadcast one or more Command Profile to other nearby NPCs.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--CommandProfileIds-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|CommandProfileIds|
|:----|:----|
|Tag Format:|`[CommandProfileIds:Value]`|
|Description:|This tag specifies the SubtypeId of a Command Profile that you want to use in your broadcast to other nearby NPCs.|
|Allowed Values:|Any Command Profile SubtypeId|
|Multiple Tag Allowed:|Yes|

<!--AddWaypointFromCommand-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|AddWaypointFromCommand|
|:----|:----|
|Tag Format:|`[AddWaypointFromCommand:Value]`|
|Description:|This tag specifies if the Behavior should add a waypoint received by a command to its list of waypoints. This is mostly for use by the `CargoShip` behavior, but others may use it in the future.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--SwitchToReceivedTarget  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SwitchToReceivedTarget|
|:----|:----|
|Tag Format:|`[SwitchToReceivedTarget:Value]`|
|Description:|This tag specifies if the Behavior should switch to a new target provided by either the damage or broadcast system.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--InheritLastAttackerFromCommand-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|InheritLastAttackerFromCommand|
|:----|:----|
|Tag Format:|`[InheritLastAttackerFromCommand:Value]`|
|Description:|This tag specifies if the Behavior should consider the received target from a command as an entity that attacked it as well. Required for some behavior specific actions.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

***

# Damage

This section contains actions for damaging other entities.

<!--DamageToolAttacker  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|DamageToolAttacker|
|:----|:----|
|Tag Format:|`[DamageToolAttacker:Value]`|
|Description:|This tag specifies if a player or block attacking the current NPC with a Grinder/Drill should receive damage. This tag only works if called from a Trigger Profile that uses `Damage` as a Trigger Type.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--DamageToolAttackerAmount  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|DamageToolAttackerAmount|
|:----|:----|
|Tag Format:|`[DamageToolAttackerAmount:Value]`|
|Description:|Specifies the amount of damage a target receives if `DamageToolAttacker` is `true`.|
|Allowed Values:|Any Number higher than `0`|
|Multiple Tag Allowed:|No|

<!--DamageToolAttackerParticle  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|DamageToolAttackerParticle|
|:----|:----|
|Tag Format:|`[DamageToolAttackerParticle:Value]`|
|Description:|Specifies a particle effect that will display over the attacker if `DamageToolAttacker` is `true`.|
|Allowed Values:|Any Particle Effect SubtypeId|
|Multiple Tag Allowed:|No|

<!--DamageToolAttackerSound  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|DamageToolAttackerSound|
|:----|:----|
|Tag Format:|`[DamageToolAttackerSound:Value]`|
|Description:|Specifies a sound effect that will display over the attacker if `DamageToolAttacker` is `true`.|
|Allowed Values:|Any Audio SubtypeId|
|Multiple Tag Allowed:|No|

<!--GenerateExplosion  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|GenerateExplosion|
|:----|:----|
|Tag Format:|`[GenerateExplosion:Value]`|
|Description:|This tag specifies if an Explosion should be generated at the coordinates of the Remote Control.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--ExplosionOffsetFromRemote  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ExplosionOffsetFromRemote|
|:----|:----|
|Tag Format:|`[ExplosionOffsetFromRemote:Value]`|
|Description:|This tag specifies the Offset from the Remote Control Position that the explosion should be created at if `GenerateExplosion` is `true`.|
|Allowed Values:|A Vector3D Value in the following format:<br />`{X:# Y:# Z:#}`<br />X: Right<br />Y: Up<br />Z: Forward<br />Replace `#` with values in meters.|
|Multiple Tag Allowed:|No|

<!--ExplosionRange  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ExplosionRange|
|:----|:----|
|Tag Format:|`[ExplosionRange:Value]`|
|Description:|Specifies the radius of the Explosion if `GenerateExplosion` is `true`. The particle effect used for the explosion changes depending on this value:<br />0-1: Tiny<br />2-14: Small<br />15-29: Medium<br />30+: Large|
|Allowed Values:|Any Number Greater Than `0`|
|Multiple Tag Allowed:|No|

<!--ExplosionDamage  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ExplosionDamage|
|:----|:----|
|Tag Format:|`[ExplosionDamage:Value]`|
|Description:|Specifies the damage of the Explosion if `GenerateExplosion` is `true`.|
|Allowed Values:|Any Number Greater Than `0`|
|Multiple Tag Allowed:|No|

<!--ExplosionIgnoresVoxels  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ExplosionIgnoresVoxels|
|:----|:----|
|Tag Format:|`[ExplosionIgnoresVoxels:Value]`|
|Description:|This tag specifies if an Explosion should skip damage to voxels if `GenerateExplosion` is `true`.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--CreateRandomLightning  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|CreateRandomLightning|
|:----|:----|
|Tag Format:|`[CreateRandomLightning:Value]`|
|Description:|This tag specifies if a bolt of lightning should be generated near the NPC. Only works on planets that have atmosphere.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--CreateLightningAtAttacker  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|CreateLightningAtAttacker|
|:----|:----|
|Tag Format:|`[CreateLightningAtAttacker:Value]`|
|Description:|This tag specifies if a bolt of lightning should be generated at the position of the entity that caused damage to the NPC. Only works on planets that have atmosphere.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--CreateLightningAtTarget  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|CreateLightningAtTarget|
|:----|:----|
|Tag Format:|`[CreateLightningAtTarget:Value]`|
|Description:|This tag specifies if a bolt of lightning should be generated at the position of current target. Only works on planets that have atmosphere.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--LightningDamage  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|LightningDamage|
|:----|:----|
|Tag Format:|`[LightningDamage:Value]`|
|Description:|Specifies the damage of lightning bolts created by an Action.|
|Allowed Values:|Any Number Greater Than `0`|
|Multiple Tag Allowed:|No|

<!--LightningExplosionRadius  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|LightningExplosionRadius|
|:----|:----|
|Tag Format:|`[LightningExplosionRadius:Value]`|
|Description:|Specifies the explosion radius of lightning bolts created by an Action.|
|Allowed Values:|Any Number Greater Than `0`|
|Multiple Tag Allowed:|No|

<!--LightningColor  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|LightningColor|
|:----|:----|
|Tag Format:|`[LightningColor:Value]`|
|Description:|Specifies the color of lightning bolts created by an Action.|
|Allowed Values:|`{X:0 Y:0 Z:0}`<br>`X` 0 - 100 (Red)<br>`Y` 0 - 100 (Green)<br>`Z` 0 - 100 (Blue)|
|Multiple Tag Allowed:|No|

<!--LightningMinDistance  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|LightningMinDistance|
|:----|:----|
|Tag Format:|`[LightningMinDistance:Value]`|
|Description:|Specifies the minimum distance from the NPC that lightning will be created at if `CreateRandomLightning` is `true`.|
|Allowed Values:|Any Number Greater Than `0`<br>Must be lower than `LightningMaxDistance`|
|Multiple Tag Allowed:|No|

<!--LightningMaxDistance  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|LightningMaxDistance|
|:----|:----|
|Tag Format:|`[LightningMaxDistance:Value]`|
|Description:|Specifies the maximum distance from the NPC that lightning will be created at if `CreateRandomLightning` is `true`.|
|Allowed Values:|Any Number Greater Than `0`<br>Must be higher than `LightningMinDistance`|
|Multiple Tag Allowed:|No|

# Effects

This section contains actions for playing audio and visual effects.

<!--PlayParticleEffectAtRemote  -->


<!--ParticleEffectId  -->


<!--ParticleEffectOffset  -->


<!--ParticleEffectScale  -->


<!--ParticleEffectMaxTime  -->


<!--ParticleEffectColor  -->

# General

This section contains actions that don't quite fit the other sections.  

<!--Chance  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Chance|
|:----|:----|
|Tag Format:|`[Chance:Value]`|
|Description:|Specifies the Chance (out of 100) that this action will be run.|
|Allowed Values:|Any Number `0` to `100`|
|Multiple Tag Allowed:|No|

# Grid

This section contains actions that affect the entire grid.  

<!--RecolorGrid  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RecolorGrid|
|:----|:----|
|Tag Format:|`[RecolorGrid:Value]`|
|Description:|This tag specifies if selected blocks on the grid should be recolored and reskinned.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--RecolorSubGrids  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RecolorSubGrids|
|:----|:----|
|Tag Format:|`[RecolorSubGrids:Value]`|
|Description:|This tag specifies if subgrids should also be considered when using the `RecolorGrid` tag.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--OldBlockColors  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|OldBlockColors|
|:----|:----|
|Tag Format:|`[OldBlockColors:Value]`|
|Description:|This tag specifies the old colors that are targeted for replacement when using the `RecolorGrid` tag. You should also include `NewBlockColors` and `NewBlockSkins` tags together when using this tag.|
|Allowed Values:|A Vector3D Value in the following format:<br />`{X:# Y:# Z:#}`<br />X: Right<br />Y: Up<br />Z: Forward<br />Replace `#` with matching values from ColorMaskHSV|
|Multiple Tag Allowed:|Yes|

<!--NewBlockColors  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|NewBlockColors|
|:----|:----|
|Tag Format:|`[NewBlockColors:Value]`|
|Description:|This tag specifies the new colors that are used for replacement when using the `RecolorGrid` tag. Provide `{X:-10 Y:-10 Z:-10}` to skip replacing color if you only intend to replace skin.|
|Allowed Values:|A Vector3D Value in the following format:<br />`{X:# Y:# Z:#}`<br />X: Right<br />Y: Up<br />Z: Forward<br />Replace `#` with matching values from ColorMaskHSV|
|Multiple Tag Allowed:|Yes|

<!--NewBlockSkins  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|NewBlockSkins|
|:----|:----|
|Tag Format:|`[NewBlockSkins:Value]`|
|Description:|This tag specifies the new skins that are used for replacement when using the `RecolorGrid` tag. Provide a single blank space to skip replacing skin if you only intend to replace color.|
|Allowed Values:|Any Armor Skin SubtypeId|
|Multiple Tag Allowed:|Yes|

<!--GridEditable  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|GridEditable|
|:----|:----|
|Tag Format:|`[GridEditable:Value]`|
|Description:|This tag specifies if the NPC Grid is able to be edited (add/remove/weld/grind blocks).|
|Allowed Values:|`Yes`<br>`No`|
|Multiple Tag Allowed:|No|

<!--GridSubGridsEditableEditable  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SubGridsEditable|
|:----|:----|
|Tag Format:|`[SubGridsEditable:Value]`|
|Description:|This tag specifies if sub-grids editable state should also be changed if `GridEditable` tag is used.|
|Allowed Values:|`Yes`<br>`No`|
|Multiple Tag Allowed:|No|

<!--GridDestructible  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|GridDestructible|
|:----|:----|
|Tag Format:|`[GridDestructible:Value]`|
|Description:|This tag specifies if the NPC Grid should have destructible blocks (can receive damage).|
|Allowed Values:|`Yes`<br>`No`|
|Multiple Tag Allowed:|No|

<!--SubGridsDestructible  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SubGridsDestructible|
|:----|:----|
|Tag Format:|`[SubGridsDestructible:Value]`|
|Description:|This tag specifies if sub-grids destructible state should also be changed if `GridDestructible` tag is used.|
|Allowed Values:|`Yes`<br>`No`|
|Multiple Tag Allowed:|No|

# Inventory

<!--AddDatapadsToSeats-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|AddDatapadsToSeats|
|:----|:----|
|Tag Format:|`[AddDatapadsToSeats:Value]`|
|Description:|This tag specifies if one or more Datapads should be added to seats randomly on the grid.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--DatapadNamesToAdd-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|DatapadNamesToAdd|
|:----|:----|
|Tag Format:|`[DatapadNamesToAdd:Value]`|
|Description:|Specifies one or more RivalAI Datapad Profiles to use when randomly adding Datapads to seats.|
|Allowed Values:|Any RivalAI Datapad Profile|
|Multiple Tag Allowed:|Yes|

<!--DatapadCountToAdd-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|DatapadCountToAdd|
|:----|:----|
|Tag Format:|`[DatapadCountToAdd:Value]`|
|Description:|Specifies the number of random Datapads that get added to seats on the grid.|
|Allowed Values:|Any Number Greater Than `0`|
|Multiple Tag Allowed:|No|

# Reputation

This section contains actions that affect the reputation of players interacting with NPC grids.

<!--ChangeReputationWithPlayers  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ChangeReputationWithPlayers|
|:----|:----|
|Tag Format:|`[ChangeReputationWithPlayers:Value]`|
|Description:|This tag specifies if players within a radius near the current NPC should have their reputation changed with the NPC faction.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--ReputationChangeRadius  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ReputationChangeRadius|
|:----|:----|
|Tag Format:|`[ReputationChangeRadius:Value]`|
|Description:|Specifies the radius that players are detected for reputation change if `ChangeReputationWithPlayers` is `true`.|
|Allowed Values:|Any Number Greater Than `0`|
|Multiple Tag Allowed:|No|

<!--ReputationChangeFactions  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ReputationChangeFactions|
|:----|:----|
|Tag Format:|`[ReputationChangeFactions:Value]`|
|Description:|Specifies one or more Faction Tags that player reputation is changed with. This tag must be paired with a `ReputationChangeAmount` value|
|Allowed Values:|Any Faction Tag|
|Multiple Tag Allowed:|Yes|

<!--ReputationChangeAmount  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ReputationChangeAmount|
|:----|:----|
|Tag Format:|`[ReputationChangeAmount:Value]`|
|Description:|Specifies the amount of reputation that is changed with a faction to eligible players if `ChangeReputationWithPlayers` is `true`. This tag must be paired with a `ReputationChangeFactions` value|
|Allowed Values:|Any Integer between -1500 and 1500|
|Multiple Tag Allowed:|Yes|

<!--ReputationChangesForAllRadiusPlayerFactionMembers  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ReputationChangesForAllRadiusPlayerFactionMembers|
|:----|:----|
|Tag Format:|`[ReputationChangesForAllRadiusPlayerFactionMembers:Value]`|
|Description:|This tag specifies if reputation made to a player should affect all players in that player's faction.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--ChangeAttackerReputation  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ChangeAttackerReputation|
|:----|:----|
|Tag Format:|`[ChangeAttackerReputation:Value]`|
|Description:|This tag specifies if reputation should be changed if a player attacks the NPC.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--ChangeAttackerReputationFaction  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ChangeAttackerReputationFaction|
|:----|:----|
|Tag Format:|`[ChangeAttackerReputationFaction:Value]`|
|Description:|Specifies one or more Faction Tags that player reputation is changed with. This tag must be paired with a `ChangeAttackerReputationAmount` value|
|Allowed Values:|Any Faction Tag|
|Multiple Tag Allowed:|Yes|

<!--ChangeAttackerReputationAmount  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ChangeAttackerReputationAmount|
|:----|:----|
|Tag Format:|`[ChangeAttackerReputationAmount:Value]`|
|Description:|Specifies the amount of reputation that is changed with a faction to attacking players if `ChangeReputationWithPlayers` is `true`. This tag must be paired with a `ChangeAttackerReputationFaction` value|
|Allowed Values:|Any Integer between -1500 and 1500|
|Multiple Tag Allowed:|Yes|

<!--ReputationChangesForAllAttackPlayerFactionMembers  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ReputationChangesForAllAttackPlayerFactionMembers|
|:----|:----|
|Tag Format:|`[ReputationChangesForAllAttackPlayerFactionMembers:Value]`|
|Description:|This tag specifies if reputation made to a player should affect all players in that player's faction.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

***

# Spawning

This section contains actions that allow NPCs to Spawn other NPCs, along with other actions that are triggered via the Modular Encounters Spawner API.

<!--SpawnEncounter  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SpawnEncounter|
|:----|:----|
|Tag Format:|`[SpawnEncounter:Value]`|
|Description:|This tag specifies if an attached Spawn Profile should be activated.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--Spawner  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Spawner|
|:----|:----|
|Tag Format:|`[Spawner:Value]`|
|Description:|This tag specifies which Spawn Profile should be activated if `SpawnEncounter` is `true`.|
|Allowed Values:|Any Spawn Profile SubtypeId|
|Multiple Tag Allowed:|Yes|

<!--CreateKnownPlayerArea  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|CreateKnownPlayerArea|
|:----|:----|
|Tag Format:|`[CreateKnownPlayerArea:Value]`|
|Description:|This tag specifies if the area around the current NPC should be designated as a Known Player Area in the Modular Encounters Spawner mod (this tag is only functional if that mod is loaded in the game world).|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--KnownPlayerAreaRadius  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|KnownPlayerAreaRadius|
|:----|:----|
|Tag Format:|`[KnownPlayerAreaRadius:Value]`|
|Description:|Specifies the radius from the current NPC for the Known Player Area if `CreateKnownPlayerArea` is `true`.|
|Allowed Values:|Any Number higher than `0`|
|Multiple Tag Allowed:|No|

<!--KnownPlayerAreaTimer  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|KnownPlayerAreaTimer|
|:----|:----|
|Tag Format:|`[KnownPlayerAreaTimer:Value]`|
|Description:|Specifies the max area time-limit (in minutes) for the Known Player Area if `CreateKnownPlayerArea` is `true`.|
|Allowed Values:|Any Integer equal/higher than `0`|
|Multiple Tag Allowed:|No|

<!--KnownPlayerAreaMaxSpawns  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|KnownPlayerAreaMaxSpawns|
|:----|:----|
|Tag Format:|`[KnownPlayerAreaMaxSpawns:Value]`|
|Description:|Specifies the max amount of spawns for the Known Player Area if `CreateKnownPlayerArea` is `true`.|
|Allowed Values:|Any Integer equal/higher than `-1`|
|Multiple Tag Allowed:|No|

<!--RemoveKnownPlayerArea  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RemoveKnownPlayerArea|
|:----|:----|
|Tag Format:|`[RemoveKnownPlayerArea:Value]`|
|Description:|This tag specifies if a Known Player Location at the current NPC position should be removed. This will only remove locations that match the faction of the NPC or are not designated to an NPC faction.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--RemoveAllKnownPlayerAreas  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RemoveAllKnownPlayerAreas|
|:----|:----|
|Tag Format:|`[RemoveAllKnownPlayerAreas:Value]`|
|Description:|This tag specifies if all Known Player Locations at the current NPC position should be removed, regardless of faction ownership. `RemoveKnownPlayerArea` must also be `true` for this tag to activate.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

***

# Targeting

This section contains actions that change or affect targeting.

<!--RefreshTarget  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RefreshTarget|
|:----|:----|
|Tag Format:|`[RefreshTarget:Value]`|
|Description:|This tag specifies if the Behavior should refresh its current target using its own Target Profile rules.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--ChangeTargetProfile  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ChangeTargetProfile|
|:----|:----|
|Tag Format:|`[ChangeTargetProfile:Value]`|
|Description:|This tag specifies if the Current Target Profile should be replaced with another. The target evaluation is NOT immediately refreshed when this tag is used, so if you require the new targeting to be used right away, you should also use the `RefreshTarget` tag in your Action.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--NewTargetProfileId  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|NewTargetProfileId|
|:----|:----|
|Tag Format:|`[NewTargetProfileId:Value]`|
|Description:|This tag specifies the new Target Profile you want the behavior to use if `ChangeTargetProfile` is set to `true`.|
|Allowed Values:|Valid Target Profile SubtypeId|
|Multiple Tag Allowed:|No|

***

# Trigger 

This section contains actions that allow you to change properties of Triggers on the current NPC.

<!--ResetCooldownTimeOfTriggers  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ResetCooldownTimeOfTriggers|
|:----|:----|
|Tag Format:|`[ResetCooldownTimeOfTriggers:Value]`|
|Description:|This tag specifies if one or more Trigger Profiles should have their current cooldown timer reset.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--ResetTriggerCooldownNames  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ResetTriggerCooldownNames|
|:----|:----|
|Tag Format:|`[ResetTriggerCooldownNames:Value]`|
|Description:|This tag specifies a name of a Trigger Profile that should have its cooldown timer reset.|
|Allowed Values:|Any text/string excluding `:`, `[`, `]`|
|Multiple Tag Allowed:|Yes|

<!--EnableTriggers  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|EnableTriggers|
|:----|:----|
|Tag Format:|`[EnableTriggers:Value]`|
|Description:|This tag specifies if one or more Trigger Profiles should be enabled (ie, UseTrigger set to true).|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--EnableTriggerNames  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|EnableTriggerNames|
|:----|:----|
|Tag Format:|`[EnableTriggerNames:Value]`|
|Description:|This tag specifies a name of a Trigger Profile that should have be Enabled.|
|Allowed Values:|Any text/string excluding `:`, `[`, `]`|
|Multiple Tag Allowed:|Yes|

<!--DisableTriggers  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|DisableTriggers|
|:----|:----|
|Tag Format:|`[DisableTriggers:Value]`|
|Description:|This tag specifies if one or more Trigger Profiles should be disabled (ie, UseTrigger set to false).|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--DisableTriggerNames  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|DisableTriggerNames|
|:----|:----|
|Tag Format:|`[DisableTriggerNames:Value]`|
|Description:|This tag specifies a name of a Trigger Profile that should have be Disabled.|
|Allowed Values:|Any text/string excluding `:`, `[`, `]`|
|Multiple Tag Allowed:|Yes|

<!--ManuallyActivateTrigger  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ManuallyActivateTrigger|
|:----|:----|
|Tag Format:|`[ManuallyActivateTrigger:Value]`|
|Description:|This tag specifies if one or more Trigger Profiles should be manually triggered.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

<!--ManuallyActivatedTriggerNames  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ManuallyActivatedTriggerNames|
|:----|:----|
|Tag Format:|`[ManuallyActivatedTriggerNames:Value]`|
|Description:|This tag specifies a name of a Trigger Profile that should be Manually Triggered.|
|Allowed Values:|Any text/string excluding `:`, `[`, `]`|
|Multiple Tag Allowed:|Yes|

<!--ForceManualTriggerActivation-->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ForceManualTriggerActivation|
|:----|:----|
|Tag Format:|`[ForceManualTriggerActivation:Value]`|
|Description:|This tag specifies if manually activated triggers should be forcibly activated from the action, regardless of their conditions, cooldowns, etc.|
|Allowed Values:|`true`<br>`false`|
|Multiple Tag Allowed:|No|

***

# Variables

This section contains actions that change local or global variables that can be used by the behavior or spawner.

<!--SetBooleansTrue  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SetBooleansTrue|
|:----|:----|
|Tag Format:|`[SetBooleansTrue:Value]`|
|Description:|This tag specifies a name of a Boolean Variable that you want to set to `true` within the Behavior Profile. If a provided name does not exist in the Behavior Profile, it will be created and saved with the `true` value|
|Allowed Values:|Any text/string excluding `:`, `[`, `]`|
|Multiple Tag Allowed:|Yes|

<!--SetBooleansFalse  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SetBooleansFalse|
|:----|:----|
|Tag Format:|`[SetBooleansFalse:Value]`|
|Description:|This tag specifies a name of a Boolean Variable that you want to set to `false` within the Behavior Profile. If a provided name does not exist in the Behavior Profile, it will be created and saved with the `false` value|
|Allowed Values:|Any text/string excluding `:`, `[`, `]`|
|Multiple Tag Allowed:|Yes|

<!--IncreaseCounters  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|IncreaseCounters|
|:----|:----|
|Tag Format:|`[IncreaseCounters:Value]`|
|Description:|This tag specifies a name of an Integer Variable that you want to increase by `1` within the Behavior Profile. If a provided name does not exist in the Behavior Profile, it will be created and saved with a `1` value|
|Allowed Values:|Any text/string excluding `:`, `[`, `]`|
|Multiple Tag Allowed:|Yes|

<!--DecreaseCounters  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|DecreaseCounters|
|:----|:----|
|Tag Format:|`[DecreaseCounters:Value]`|
|Description:|This tag specifies a name of an Integer Variable that you want to decrease by `1` within the Behavior Profile. If a provided name does not exist in the Behavior Profile, it will be created and saved with a `-1` value|
|Allowed Values:|Any text/string excluding `:`, `[`, `]`|
|Multiple Tag Allowed:|Yes|

<!--SetCounters  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SetCounters|
|:----|:----|
|Tag Format:|`[SetCounters:Value]`|
|Description:|This tag specifies a name of an Integer Variable that you want to set to a specific value within the behavior. If a provided name does not exist in the behavior, it will be created and saved with the provided value. Ensure you also provide the value you want to set the variable to using the `SetCountersValues` tag|
|Allowed Values:|Any text/string excluding `:`, `[`, `]`|
|Multiple Tag Allowed:|Yes|

<!--SetCountersValues  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SetCountersValues|
|:----|:----|
|Tag Format:|`[SetCountersValues:Value]`|
|Description:|This tag specifies the value of an Integer Variable within the behavior. Ensure you also provide the name of the variable you want to set the value of using the `SetCounters` tag.|
|Allowed Values:|Any Integer Value|
|Multiple Tag Allowed:|Yes|

<!--ResetCounters  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ResetCounters|
|:----|:----|
|Tag Format:|`[ResetCounters:Value]`|
|Description:|This tag specifies a name of an Integer Variable that you want to set to a value of `0` within the Behavior Profile. If a provided name does not exist in the Behavior Profile, it will be created and saved with a `0` value|
|Allowed Values:|Any text/string excluding `:`, `[`, `]`|
|Multiple Tag Allowed:|Yes|

<!--SetSandboxBooleansTrue  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SetSandboxBooleansTrue|
|:----|:----|
|Tag Format:|`[SetSandboxBooleansTrue:Value]`|
|Description:|This tag specifies a name of a Boolean Variable that you want to set to `true` within the Save File. If a provided name does not exist in the Save File, it will be created and saved with the `true` value|
|Allowed Values:|Any text/string excluding `:`, `[`, `]`|
|Multiple Tag Allowed:|Yes|

<!--SetSandboxBooleansFalse  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SetSandboxBooleansFalse|
|:----|:----|
|Tag Format:|`[SetSandboxBooleansFalse:Value]`|
|Description:|This tag specifies a name of a Boolean Variable that you want to set to `false` within the Save File. If a provided name does not exist in the Save File, it will be created and saved with the `false` value|
|Allowed Values:|Any text/string excluding `:`, `[`, `]`|
|Multiple Tag Allowed:|Yes|

<!--IncreaseSandboxCounters  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|IncreaseSandboxCounters|
|:----|:----|
|Tag Format:|`[IncreaseSandboxCounters:Value]`|
|Description:|This tag specifies a name of an Integer Variable that you want to increase by `1` within the Save File. If a provided name does not exist in the Save File, it will be created and saved with a `1` value|
|Allowed Values:|Any text/string excluding `:`, `[`, `]`|
|Multiple Tag Allowed:|Yes|

<!--DecreaseSandboxCounters  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|DecreaseSandboxCounters|
|:----|:----|
|Tag Format:|`[DecreaseSandboxCounters:Value]`|
|Description:|This tag specifies a name of an Integer Variable that you want to decrease by `1` within the Save File. If a provided name does not exist in the Save File, it will be created and saved with a `-1` value|
|Allowed Values:|Any text/string excluding `:`, `[`, `]`|
|Multiple Tag Allowed:|Yes|

<!--SetSandboxCounters  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SetSandboxCounters|
|:----|:----|
|Tag Format:|`[SetSandboxCounters:Value]`|
|Description:|This tag specifies a name of an Integer Variable that you want to set to a specific value within the Save File. If a provided name does not exist in the Save File, it will be created and saved with the provided value. Ensure you also provide the value you want to set the variable to using the `SetSandboxCounters` tag|
|Allowed Values:|Any text/string excluding `:`, `[`, `]`|
|Multiple Tag Allowed:|Yes|

<!--SetSandboxCountersValues  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|SetSandboxCountersValues|
|:----|:----|
|Tag Format:|`[SetSandboxCountersValues:Value]`|
|Description:|This tag specifies the value of an Integer Variable within the Save File. Ensure you also provide the name of the variable you want to set the value of using the `SetSandboxCounters` tag.|
|Allowed Values:|Any Integer Value|
|Multiple Tag Allowed:|Yes|

<!--ResetSandboxCounters  -->
|Tag:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|ResetSandboxCounters|
|:----|:----|
|Tag Format:|`[ResetSandboxCounters:Value]`|
|Description:|This tag specifies a name of an Integer Variable that you want to set to a value of `0` within the Save File. If a provided name does not exist in the Save File, it will be created and saved with a `0` value|
|Allowed Values:|Any text/string excluding `:`, `[`, `]`|
|Multiple Tag Allowed:|Yes|