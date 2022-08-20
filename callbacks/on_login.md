# On login callback

first you need to create an `minecraft.custom:minecraft.leave_game` scoreboard:

```mcfunction
scoreboard objectives add leave minecraft.custom:minecraft.leave_game
```

Then in the loop:

```mcfunction
execute as @a[scores={leave=1..}] run tag @s add logon
#replace with your function:
execute as @a[tag=logon] run function namespace:on_login 
scoreboard players set @a leave 0
tag @a remove logon
```
