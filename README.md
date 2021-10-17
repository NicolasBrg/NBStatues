# NBStatues - PureForge 1.12.2 - Version 1.10.21.1

PureForge 1.12.2 mod allowing the creation of events of hunting for presents, statues, monsters and even pokemon (if Pixelmon is installed). You can also script events like maps / event adventures, quests and stories to tell. An advanced configuration easily and quickly done in-Game.

## What is a &quot;Collection&quot; in NBStatues?

A collection is a container that contains a list of objects to find, that can be Blocks, Entities, Monster, TileEntities, NPC and Pokemon (Statue or EntityPixelmon). To claim an object, player must right click on it.

## Configuration

This category explains how to set up and use NBStatues. No dependency required. Some features are unlocked if you have Pixelmon installed. Very fast installation, in 5 minutes you&#39;ve the time to add your license, and create a really complete collection.

### Permissions

To configure this mod, users must have OP permission for single player instances, for servers, users will need the &quot;nbstatues.admin&quot; permission to configure the mod.

Players must have permission &quot;nbstatues.base&quot; to see UI. You can also define permission for each collection you create, to see and complete it, players must have theses permissions.

### Licensing

All players have access to the command &quot;/nbstatues\_license&quot; which displays informations about the current license. To configure your license or buy one, please visit this wiki page.

### Reward commands syntax

You&#39;ve two type of commands:

- Commands starting with &quot;/&quot;: The command will be executed by the player
  - Example: &quot;/nbstatues Halloween&quot; will open the Halloween collection for the player.
- Commands starting with &quot;!&quot;: The command will be executed by the server
  - Example: &quot;!give {PLAYER} minecraft:diamond 6&quot; Will give 6 diamond to the player.
- Commands starting with &quot;PM&quot;: Send a private message to the player
  - Example: &quot;PM &amp;aYou should go to the mansion to find this &amp;6artefact&amp;a.&quot; Will send the message below in green and yellow to the player.
- Commands starting with &quot;BROAD&quot;: Will send a message to all player online on the server
  - Example: &quot;BROAD &amp;2Someone found the secret ofthe haunted pumpkin and earns the rank &quot;&amp;6Master of Halloween 2021&amp;2&quot;. &quot; All player will see this message in the chat.
- Commands equal &quot;CLOSE&quot;: Force the UI to be close for the player

The placeholder {PLAYER} is available and will be replaced by the name of the player.

### Configuration files

Configuration files are JSON files. If you&#39;ve any problems with the plugin, please look the error displayed and test your config file on one online JSON verifier (for example: [https://jsonformatter.curiousconcept.com/](https://jsonformatter.curiousconcept.com/)) to found the issue easily, if you don&#39;t found the problems, please open a ticket in my discord and attach config file, errors and an message of what that have happens.

You&#39;ve 5 configurations (you can edit it to customize, but the default configuration is nice to start):

- **Messages.json** : All strings, text and format of the plugin for your player.
- **General.json** : Main configuration of the plugin (World exclusion, Commands alias, and Logs display)
- **License.json** : All information about your license, please don&#39;t share your personal file, else the license will be disabled by the security system.
- **StatuesCollection.json** : All collections data are available here. You can customize format, commands, icons, and object directly here, but you&#39;ve automatic commands to do theses changes without any risk of problems if you write something wrong.
- **PlayerData folder** : Folder who contains the progress of each player, to remove the progress of one player delete the file with his UUID name.

I recommend you to only customize **Messages.json** and **General.json** in a first time because commands are easier.

### Placeholder, formats and features for collections

\*&quot;&lt;&gt;&quot; means that is required, and &quot;{}&quot; optional, if the content of &quot;{}&quot; is in upper case it&#39;s variable data\*

This configuration is automatically made if you make your collection in game, but it&#39;s really good to know.

Bloc arguments:

- Structure: &lt;modid:item\_name&gt;{/meta} or PRESENT&lt;{NBT\_Tag}&gt;
- Example:
  - minecraft:carpet/3 
    - (Light blue carpet)
  - pixelmon:poke\_ball
    - (Pixelmon Pokéball)
  - PRESENT{SkullOwner: &quot;NicolasBrg&quot;} 
    - (NicolasBrg&#39;s Head)
  - PRESENT{SkullOwner: &quot;MHF\_Present2&quot;} 
    - (Present)

For custom skull, you can see the official list of included MHF skull [https://minecraft.fandom.com/wiki/Head](https://minecraft.fandom.com/wiki/Head) or use custom from online website like: [https://minecraft-heads.com/player-heads](https://minecraft-heads.com/player-heads) or [https://minecraft-heads.com/custom-heads](https://minecraft-heads.com/custom-heads) (Please note that for custom heads, you need to use nbt from 1.12.2 version, a wiki is also available)

Pokémon arguments:

- Structure: &lt;PokemonSpecies&gt;{/form\_id}{#custom\_texture}
- Example:
  - Turtwig (Turtwig icon)
  - Giratina/1#Shiny (Shiny Giratina alternative form)

(Please take notes, that Pokémon have priority on Bloc)

Description arguments:

- Structure: &lt;description&gt; (You can use &quot;\\n&quot; to back to the line, and &quot;&amp;&quot; to add color)
- Alias available (Collection only):
  - **{CURRENT}** Number of statues found in the collection
  - **{MAX}** Number of statues in the collection
- Example:
  - &amp;2First Line\n&amp;aSecond Line
  - **&amp;6{CURRENT}**&amp;e/**&amp;6{MAX}**&amp;b statues

Commands arguments:

- **Command**\_**List**: Display all commands attached to the statues or collection
- **Command**\_**Add** &lt;Command&gt; Add a new command
- **Command**\_**Remove**\_**Id** &lt;ID&gt; Remove command from ID (starting to 0)

## Commands

Here is a list of commands available in NBStatues. For each commands you have tab assistance. Keep in mind you can configure the plugin without all theses commands, with UI. See video above or wiki page.

### /nbstatues\_admin &lt;Action&gt;

- **Config**
  - **Load** Load all config files
  - **Save** Save collections file
  - **Refresh** \_String Reload all strings from Messages.json
- **Collection**
  - **List**
    - Display the list of all collection. (Click on an item to edit the collection)
  - **Info**
    - Display if you&#39;re currently editing one collection.
  - **Save**
    - Save the collection and leave the editor mod.
  - **Create** &lt; **Name** &gt;
    - Create a new collection
  - **Edit** &lt; **Name** &gt;
    - **(REQUIRED FOR COMMANDS BELOW)** Edit one collection
  - **Rename** &lt; **NewName** &gt;
    - Rename the selected collection.
  - **Print**
    - Display all statues from a collection
  - **Permission** &lt; **Permission** &gt;
    - Define a new permission for the selected collection
  - **Remove** &lt; **Name** &gt;
    - Remove the collection (You need to have selected it before with edit command)
  - **Pokemon** &lt; **PokemonArg** &gt;
    - Define pokemon icon (see format above)
  - **Bloc** &lt; **BlockArg** &gt;
    - Define block icon (see format above)
  - **Display**\_**Name** &lt; **Name** &gt;
    - Define a new display name to the collection (with color code &quot;&amp;&quot;)
  - **Description** &lt; **Content** &gt;
    - Description with line break and color (see format above)
  - **Delete**\_**statue** &lt; **ID** &gt;
    - Delete the statue from ID (format of name is **WORLD/PosX/PosY/PosZ** tab will auto complete it for you, you&#39;ve also the UI to remove statues without this command; to delete a statue, you need to edit the statue&#39;s collection.
  - **Refresh**\_**collection**
    - Refresh collections and statues from config.
  - **Command**\_**List**
    - Display list of commands after collection completion
  - **Command**\_**Add** &lt; **Value** &gt;
    - Add new command after collection completion
  - **Command**\_**Remove**\_Id** &lt; **ID** &gt;
    - Delete command n°ID of commands after collection completion
- **Statues** (theses commands have the same format that showed above)
  - **Name** &lt;Statue&gt; &lt;Value&gt;
  - **Description** &lt;Statue&gt; {Value}
  - **Bloc** &lt;Statue&gt; &lt;Value&gt;
  - **Pokemon** &lt;Statue&gt; &lt;Value&gt;
  - **Command** \_List &lt;Statue&gt;
  - **Command** \_Add &lt;Statue&gt; &lt;Value&gt;
  - **Command** \_Remove\_Id &lt;Statue&gt; &lt;ID&gt;
  - **Help**
- **Help** : Display help

### /nbstatues {Action}

- &quot; **CollectionName**&quot;: Display UI of the &quot;CollectionName&quot; collection
  - If a player have the admin permission, he can right clicked on one statue in UI to delete it.
- **Info** : Send dev / license information
- **NicolasBrg** : Send dev information
- **License** : Send license information
- **If empty** : Open Main UI of collection

Take note that UI who display all statue have page system, but I recommend you to not exceed 150 statues for each collection.

### /nbstatues\_force &lt;StatueID&gt; {Player}

Force a claim of the selected statue to the player.
