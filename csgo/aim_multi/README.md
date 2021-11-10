## aim_multi
A 1v1 aim map where you can pre-select what weapon you want to 1v1 with.

This was done by having a wall of `prop_dynamic_override` for each weapon with a `func_button` over it. Basic input/output system:
`func_button` `OnPressed equip_weapon AddOutput model weapon_weaponName 0.00 No` 
`info_target` named `equip_weapon`: `OnUser1 equip RunScriptCode self.ValidateScriptScope() 0.00 No` and `OnUser1 equip RunScriptCode self.__KeyValueFromInt(caller.GetModelName(), 1) 0.01 No`
`game_player_equip` named `equip`
`logic_auto`: `OnMapSpawn equip_weapon FireUser1 0.00 Yes` and `OnMapSpawn equip TriggerForAllPlayers 0.02 No`