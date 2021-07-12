You can find the Grids Settings Configuration File in `MySaveWorldFolder\Storage\1521905890.sbm_ModularEncountersSpawner\Config-Grids.xml`. The settings you can modify are listed below:

|Setting:|EnableGlobalNPCWeaponRandomizer|
|:----|:----|
|XML:|`<EnableGlobalNPCWeaponRandomizer>Value</EnableGlobalNPCWeaponRandomizer>`|
|Chat Command:|`/MES.Settings.Grids.EnableGlobalNPCWeaponRandomizer.Value`|
|Description:|This setting allows you to specify if NPC spawns should all have their weapons randomized. This is the same behavior provided by the `NPC Weapon Upgrades` mod. `Value` can be replaced with `true` or `false`|

|Setting:|EnableGlobalNPCShieldProvider|
|:----|:----|
|XML:|`<EnableGlobalNPCShieldProvider>Value</EnableGlobalNPCShieldProvider>`|
|Chat Command:|`/MES.Settings.Grids.EnableGlobalNPCShieldProvider.Value`|
|Description:|This setting allows you to specify if NPC spawns should have Defense Shield blocks added. This is the same behavior provided by the `NPC Defense Shield Provider` mod. `Value` can be replaced with `true` or `false`|

|Setting:|RandomWeaponSizeVariance|
|:----|:----|
|XML:|`<RandomWeaponSizeVariance>Value</RandomWeaponSizeVariance>`|
|Chat Command:|`/MES.Settings.Grids.RandomWeaponSizeVariance.Value`|
|Description:|This setting allows you to control the size variance of weapons that are replaced with the Weapon Randomizer / NPC Weapon Upgrades. The default value of `-1` does not check for any variance. If set to `0`, then replaced weapons would need to be an exact match in size to be replaced. If set to a value like `2`, then the weapons allowed to be used for replacement can be 2 blocks bigger or smaller in all directions (X,Y,Z).|

|Setting:|WeaponReplacerBlacklist|
|:----|:----|
|XML:|`<WeaponReplacerBlacklist>`<br />   `<string>Value1</string>`<br />   `<string>Value2</string>`<br />`</WeaponReplacerBlacklist>`|
|Chat Command (Add):|`/MES.Settings.Grids.WeaponReplacerBlacklist.Add.Value`|
|Chat Command (Remove):|`/MES.Settings.Grids.WeaponReplacerBlacklist.Remove.Value`|
|Description:|This setting allows you to specify one or more Weapons that will not be used in NPC Weapon Randomization. To add more weapons to the list, simply create a new line between the `<WeaponReplacerBlacklist>` and `</WeaponReplacerBlacklist>` tags and enter the following `<string>Value</string>` - Replace `Value` either the SubtypeName, DefinitionId, or ModID of the weapon(s) you want to Blacklist.

|Setting:|WeaponReplacerWhitelist|
|:----|:----|
|XML:|`<WeaponReplacerWhitelist>`<br />   `<string>Value1</string>`<br />   `<string>Value2</string>`<br />`</WeaponReplacerWhitelist>`|
|Chat Command (Add):|`/MES.Settings.Grids.WeaponReplacerWhitelist.Add.Value`|
|Chat Command (Remove):|`/MES.Settings.Grids.WeaponReplacerWhitelist.Remove.Value`|
|Description:|This setting allows you to specify one or more Weapons that will only be used in NPC Weapon Randomization. To add more weapons to the list, simply create a new line between the `<WeaponReplacerWhitelist>` and `</WeaponReplacerWhitelist>` tags and enter the following `<string>Value</string>` - Replace `Value` either the SubtypeName, DefinitionId, or ModID of the weapon(s) you want to Whitelist.

|Setting:|WeaponReplacerTargetBlacklist|
|:----|:----|
|XML:|`<WeaponReplacerTargetBlacklist>`<br />   `<string>Value1</string>`<br />   `<string>Value2</string>`<br />`</WeaponReplacerTargetBlacklist>`|
|Chat Command (Add):|`/MES.Settings.Grids.WeaponReplacerTargetBlacklist.Add.Value`|
|Chat Command (Remove):|`/MES.Settings.Grids.WeaponReplacerTargetBlacklist.Remove.Value`|
|Description:|This setting allows you to specify one or more Weapons that will not be replaced by random weapons in NPC Weapon Randomization. To add more weapons to the list, simply create a new line between the `<WeaponReplacerTargetBlacklist>` and `</WeaponReplacerTargetBlacklist>` tags and enter the following `<string>Value</string>` - Replace `Value` either the SubtypeName, DefinitionId, or ModID of the weapon(s) you want to Blacklist.

|Setting:|WeaponReplacerTargetWhitelist|
|:----|:----|
|XML:|`<WeaponReplacerTargetWhitelist>`<br />   `<string>Value1</string>`<br />   `<string>Value2</string>`<br />`</WeaponReplacerTargetWhitelist>`|
|Chat Command (Add):|`/MES.Settings.Grids.WeaponReplacerTargetWhitelist.Add.Value`|
|Chat Command (Remove):|`/MES.Settings.Grids.WeaponReplacerTargetWhitelist.Remove.Value`|
|Description:|This setting allows you to specify one or more Weapons that will only be replaced in NPC Weapon Randomization. To add more weapons to the list, simply create a new line between the `<WeaponReplacerTargetWhitelist>` and `</WeaponReplacerTargetWhitelist>` tags and enter the following `<string>Value</string>` - Replace `Value` either the SubtypeName, DefinitionId, or ModID of the weapon(s) you want to Whitelist.

|Setting:|UseGlobalBlockReplacer|
|:----|:----|
|XML:|`<UseGlobalBlockReplacer>Value</UseGlobalBlockReplacer>`|
|Chat Command:|`/MES.Settings.Grids.UseGlobalBlockReplacer.Value`|
|Description:|This setting allows you to enable or disable the Global Block Replacement functionality in MES. With this enabled, you can specify block pairs or profiles that will replace blocks in all prefabs spawned through MES. `Value` can be replaced with `true` or `false`|

|Setting:|GlobalBlockReplacerReference|
|:----|:----|
|XML:|`<GlobalBlockReplacerReference>`<br />   `<string>Value1</string>`<br />   `<string>Value2</string>`<br />`</GlobalBlockReplacerReference>`|
|Chat Command (Add):|`/MES.Settings.Grids.GlobalBlockReplacerReference.Add.Value`|
|Chat Command (Remove):|`/MES.Settings.Grids.GlobalBlockReplacerReference.Remove.Value`|
|Description:|This setting allows you to specify one or more Block Replacement Pairs that will be used if `GlobalBlockReplacer` is enabled. To add more pairs to the list, simply create a new line between the `<GlobalBlockReplacerReference>` and `</GlobalBlockReplacerReference>` tags and enter the following `<string>Value</string>` - `Value` is replaced with two block IDs, separated with the `\|` symbol (eg: `MyObjectBuilder_LargeGatlingTurret/(null)\|MyObjectBuilder_LargeMissileTurret/(null)`). Block IDs can be easily retrieved using the chat command `/MES.GetBlockDefinitions`.

|Setting:|GlobalBlockReplacerProfiles|
|:----|:----|
|XML:|`<GlobalBlockReplacerProfiles>`<br />   `<string>Value1</string>`<br />   `<string>Value2</string>`<br />`</GlobalBlockReplacerProfiles>`|
|Chat Command (Add):|`/MES.Settings.Grids.GlobalBlockReplacerProfiles.Add.Value`|
|Chat Command (Remove):|`/MES.Settings.Grids.GlobalBlockReplacerProfiles.Remove.Value`|
|Description:|This setting allows you to specify one or more Block Replacement Profiles that will be used if `GlobalBlockReplacer` is enabled. To add more profiles to the list, simply create a new line between the `<GlobalBlockReplacerProfiles>` and `</GlobalBlockReplacerProfiles>` tags and enter the following `<string>Value</string>` - `Value` is replaced with the name of the Block Replacement Profile. [Profile names can be found here](https://gist.github.com/MeridiusIX/415b45b53174c608c6486ce06bb58e2c).

|Setting:|UseNonPhysicalAmmoForNPCs|
|:----|:----|
|XML:|`<UseNonPhysicalAmmoForNPCs>Value</UseNonPhysicalAmmoForNPCs>`|
|Chat Command:|`/MES.Settings.Grids.UseNonPhysicalAmmoForNPCs.Value`|
|Description:|This setting allows you to replace all physical ammo in NPC grids with non-physical ammo, meaning they will not drop ammo when weapons are destroyed or hacked. This can be useful for increasing the difficulty of your play-through.  `Value` can be replaced with `true` or `false`|

|Setting:|RemoveContainerInventoryFromNPCs|
|:----|:----|
|XML:|`<RemoveContainerInventoryFromNPCs>Value</RemoveContainerInventoryFromNPCs>`|
|Chat Command:|`/MES.Settings.Grids.RemoveContainerInventoryFromNPCs.Value`|
|Description:|This setting allows you to remove any inventory items in the containers of NPC grids when spawned. This can be useful for increasing the difficulty of your play-through.  `Value` can be replaced with `true` or `false`|