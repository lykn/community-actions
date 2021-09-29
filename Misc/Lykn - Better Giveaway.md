**Some Info**

➜ Better than Can's giveaway action.

➜ Made the embeds better(ish), and fixed the args a bit(ish).

➜ [ColorHexa](https://www.colorhexa.com/) will help you out sorting out the colors for the embed, I haven't added any color but you can add the `color` after the `--title`(`--color="<hex>"`).

➜ There is an error message explaining everything needed, when the user leaves the arguments empty, like, `[p]g <nothing>`.

➜ One thing to remember while doing all of this is to change the `GIVEAWAY_PING_ROLE_ID_HERE` with the real role ID because that's the variable which stores the role to be pinged.


**Action Info**

・Command/Action Name: `g`

・Whitelisted Roles/Channels: `Custom`

・Blacklisted Roles/Channels: `Custom`

・Delete Invocation Message: `true`

・Script: 
```
{set;arg1;{find;{args};/(.*)(?:\s?(?:\||,|\/)\s?)(.*)(?:\s?(?:\||,|\/)\s?)(.*)$/;1}}
{set;arg2;{find;{args};/(.*)(?:\s?(?:\||,|\/)\s?)(.*)(?:\s?(?:\||,|\/)\s?)(.*)$/;2}}
{set;arg3;{find;{args};/(.*)(?:\s?(?:\||,|\/)\s?)(.*)(?:\s?(?:\||,|\/)\s?)(.*)$/;3}}
{note;Set the giveaway_ping role to the role you want to ping}
{set;giveaway_ping;GIVEAWAY_PING_ROLE_ID_HERE}
{a!ae; 
 --message="{role.mention;{get;giveaway_ping}}";
 --title="**__:tada: Giveaway! :tada:__**";
 --color="{user.color}";
 --description="Prize: {get;arg1}\nDonor: {get;arg2}\nMessage: **{get;arg3}**";
 --thumbnail="{guild.iconURL}";
 --footer="Pinged by {user.username}#{user.discriminator}";
 --timestamp="true";
 --footer-icon="{user.avatarURL}"
 }

{if;{get;arg1};==;;{if;{get;arg2};==;;{if;{get;arg3};==;;{a!ae; 
 --title="Uh Oh Wrong Usage";
 --description="`[p]` = prefix(`a!` is the default one, if you don't have a custom one)\n> 1. `[p]g <prize> | <donor> | <message>` - `[p]g 1 Nitro Classic | @Lykn#0001 | Just felt generous<3`";
--timpstamp="true";
--footer-icon="{user.avatarURL}";
--thumbnail="{guild.iconURL}";
--footer="Messed up by {user.username}#{user.discriminator} | "
 }}}}
```
