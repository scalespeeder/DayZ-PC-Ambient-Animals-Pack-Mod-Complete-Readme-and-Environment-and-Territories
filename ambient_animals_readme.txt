Readme Instructions For HunterZ's Ambient Animals PC DayZ Mod Mission Files (Chernarus)

All credit to HunterZ for making this amazing Mod.

https://steamcommunity.com/sharedfiles/filedetails/?id=3114410963

Included in Github repository are the animal territory files for Chernarus (1.23 compatible), so you have them in one place
to easily upload to your mission /env directory & also a ready-to-go cfgenvironment.xml file
(correct as update 1.23) so you don't have to carry out all of the steps below, you can just skip to the
Events section and start there.

If when you come to install the mod beyond update 1.23, you may well want to follow the individual steps
below to add the code snippets to your Chernarus Mission files.

Add these code snippets to cfgEnvironments.cfg
↓↓↓ under <file path="env/bear_territories.xml" />

<file path="env/otter_territories.xml" />
<file path="env/rabbit_territories.xml" />
<file path="env/rat_territories.xml" />
<file path="env/raven_territories.xml" />
<file path="env/seagull_territories.xml" />
<file path="env/snake_territories.xml" />
<file path="env/squirrel_territories.xml" />

↓↓↓ add this under (<territory type="Ambient" name="AmbientHen" behavior="DZAmbientLifeGroupBeh">) class

<!-- OTTER -->
<territory type="Ambient" name="AmbientOtter" behavior="DZOtterGroupBeh">
    <file usable="otter_territories" />	
    <!-- different agent types - class has to begin with AgentType:w -->
    <agent type="Male" chance="1">
        <spawn configName="Animal_Otter" chance="1" />
    </agent>
    <agent type="Female" chance="3">
        <spawn configName="Animal_Otter" chance="10" />
    </agent>

    <item name="globalCountMax" val="50" />
    <item name="zoneCountMin" val="1" />
    <item name="zoneCountMax" val="1" />
    <item name="playerSpawnRadiusNear" val="25" />
    <item name="playerSpawnRadiusFar" val="75" />
</territory>

<!-- RABBIT -->
<territory type="Ambient" name="AmbientRabbit" behavior="DZRabbitGroupBeh">
    <file usable="rabbit_territories" />
    <!-- different agent types - class has to begin with AgentType:w -->
    <agent type="Male" chance="1">
        <spawn configName="Animal_Rabbit_Grey" chance="1" />
    </agent>
    <agent type="Female" chance="3">
        <spawn configName="Animal_Rabbit_Brown" chance="10" />
    </agent>

    <item name="globalCountMax" val="50" />
    <item name="zoneCountMin" val="1" />
    <item name="zoneCountMax" val="1" />
    <item name="playerSpawnRadiusNear" val="25" />
    <item name="playerSpawnRadiusFar" val="75" />
</territory>

<!-- RAT -->
<territory type="Ambient" name="AmbientRat" behavior="DZRatGroupBeh">
    <file usable="rat_territories" />
    <!-- different agent types - class has to begin with AgentType:w -->
    <agent type="Male" chance="1">
        <spawn configName="Animal_Rat_Grey" chance="1" />
    </agent>
    <agent type="Female" chance="3">
        <spawn configName="Animal_Rat_White" chance="10" />
    </agent>

    <item name="globalCountMax" val="50" />
    <item name="zoneCountMin" val="1" />
    <item name="zoneCountMax" val="1" />
    <item name="playerSpawnRadiusNear" val="25" />
    <item name="playerSpawnRadiusFar" val="75" />
</territory>

<!-- RAVEN -->
<territory type="Ambient" name="AmbientRaven" behavior="DZRavenGroupBeh">
    <file usable="raven_territories" />
    <!-- different agent types - class has to begin with AgentType:w -->
    <agent type="Male" chance="1">
        <spawn configName="Animal_Raven_Airborne" chance="1" />
    </agent>
    <agent type="Female" chance="3">
	<spawn configName="Animal_Raven" chance="10" />
        <spawn configName="Animal_Raven2" chance="10" />
    </agent>

    <item name="globalCountMax" val="50" />
    <item name="zoneCountMin" val="1" />
    <item name="zoneCountMax" val="1" />
    <item name="playerSpawnRadiusNear" val="25" />
    <item name="playerSpawnRadiusFar" val="75" />
</territory>

<!-- SEAGULL -->
<territory type="Ambient" name="AmbientSeagull" behavior="DZSeagullGroupBeh">
    <file usable="seagull_territories" />
    <!-- different agent types - class has to begin with AgentType:w -->
    <agent type="Male" chance="3">
        <spawn configName="Animal_Seagull_Airborne" chance="10" />
    </agent>
    <agent type="Female" chance="1">
		<spawn configName="Animal_Seagull" chance="10" />
    </agent>

    <item name="globalCountMax" val="50" />
    <item name="zoneCountMin" val="1" />
    <item name="zoneCountMax" val="1" />
    <item name="playerSpawnRadiusNear" val="25" />
    <item name="playerSpawnRadiusFar" val="75" />
</territory>


<territory type="Herd" name="Snake" behavior="DZSnakeGroupBeh">
	<file usable="snake_territories" />
</territory>

<!-- SQUIRREL -->
<territory type="Ambient" name="AmbientSquirrel" behavior="DZSquirrelGroupBeh">
    <file usable="squirrel_territories" />
    <!-- different agent types - class has to begin with AgentType:w -->
    <agent type="Male" chance="1">
        <spawn configName="Animal_Squirrel" chance="1" />
    </agent>
    <agent type="Female" chance="3">
        <spawn configName="Animal_Squirrel" chance="10" />
    </agent>

    <item name="globalCountMax" val="50" />
    <item name="zoneCountMin" val="1" />
    <item name="zoneCountMax" val="1" />
    <item name="playerSpawnRadiusNear" val="25" />
    <item name="playerSpawnRadiusFar" val="75" />
</territory>

Add to Events.xml
↓↓↓ add under (<event name="AmbientHen">) class

<event name="AmbientOtter">
    <nominal>3</nominal>
    <min>0</min>
    <max>20</max>
    <lifetime>33</lifetime>
    <restock>15</restock>
    <saferadius>40</saferadius>
    <distanceradius>0</distanceradius>
    <cleanupradius>0</cleanupradius>
    <flags deletable="0" init_random="0" remove_damaged="0"/>
    <position>fixed</position>
    <limit>mixed</limit>
    <active>1</active>
    <children>
        <child lootmax="0" lootmin="0" max="2" min="1" type="Animal_Otter"/>
    </children>
</event>

<event name="AmbientRabbit">
    <nominal>3</nominal>
    <min>0</min>
    <max>50</max>
    <lifetime>33</lifetime>
    <restock>15</restock>
    <saferadius>40</saferadius>
    <distanceradius>0</distanceradius>
    <cleanupradius>0</cleanupradius>
    <flags deletable="0" init_random="0" remove_damaged="0"/>
    <position>fixed</position>
    <limit>mixed</limit>
    <active>1</active>
    <children>
        <child lootmax="0" lootmin="0" max="2" min="1" type="Animal_Rabbit_Brown"/>
        <child lootmax="0" lootmin="0" max="4" min="1" type="Animal_Rabbit_Grey"/>
    </children>
</event>

<event name="AmbientRat">
    <nominal>3</nominal>
    <min>0</min>
    <max>50</max>
    <lifetime>33</lifetime>
    <restock>15</restock>
    <saferadius>40</saferadius>
    <distanceradius>0</distanceradius>
    <cleanupradius>0</cleanupradius>
    <flags deletable="0" init_random="0" remove_damaged="0"/>
    <position>fixed</position>
    <limit>mixed</limit>
    <active>1</active>
    <children>
        <child lootmax="0" lootmin="0" max="2" min="1" type="Animal_Rat_Grey"/>
        <child lootmax="0" lootmin="0" max="4" min="1" type="Animal_Rat_White"/>
    </children>
</event>

<event name="AmbientRaven">
    <nominal>3</nominal>
    <min>0</min>
    <max>50</max>
    <lifetime>33</lifetime>
    <restock>15</restock>
    <saferadius>40</saferadius>
    <distanceradius>0</distanceradius>
    <cleanupradius>0</cleanupradius>
    <flags deletable="0" init_random="0" remove_damaged="0"/>
    <position>fixed</position>
    <limit>mixed</limit>
    <active>1</active>
    <children>
        <child lootmax="0" lootmin="0" max="2" min="1" type="Animal_Raven"/>
        <child lootmax="0" lootmin="0" max="4" min="1" type="Animal_Raven2"/>
	<child lootmax="0" lootmin="0" max="2" min="1" type="Animal_Raven_Airborne"/>
    </children>
</event>

<event name="AmbientSeagull">
    <nominal>3</nominal>
    <min>0</min>
    <max>50</max>
    <lifetime>33</lifetime>
    <restock>15</restock>
    <saferadius>40</saferadius>
    <distanceradius>0</distanceradius>
    <cleanupradius>0</cleanupradius>
    <flags deletable="0" init_random="0" remove_damaged="0"/>
    <position>fixed</position>
    <limit>mixed</limit>
    <active>1</active>
    <children>
        <child lootmax="0" lootmin="0" max="2" min="1" type="Animal_Seagull"/>
		<child lootmax="0" lootmin="0" max="2" min="1" type="Animal_Seagull_Airborne"/>
    </children>
</event>

<event name="AnimalSnake">
<nominal>6</nominal>
<min>4</min>
<max>6</max>
<lifetime>180</lifetime>
<restock>0</restock>
<saferadius>200</saferadius>
<distanceradius>0</distanceradius>
<cleanupradius>0</cleanupradius>
<flags deletable="0" init_random="0" remove_damaged="1"/>
<position>fixed</position>
<limit>child</limit>
<active>1</active>
<children>
<child lootmax="0" lootmin="0" max="4" min="0" type="Animal_Snake"/>
</children>
</event>

<event name="AmbientSquirrel">
    <nominal>3</nominal>
    <min>0</min>
    <max>50</max>
    <lifetime>33</lifetime>
    <restock>15</restock>
    <saferadius>40</saferadius>
    <distanceradius>0</distanceradius>
    <cleanupradius>0</cleanupradius>
    <flags deletable="0" init_random="0" remove_damaged="0"/>
    <position>fixed</position>
    <limit>mixed</limit>
    <active>1</active>
    <children>
        <child lootmax="0" lootmin="0" max="4" min="1" type="Animal_Squirrel"/>
    </children>
</event>

add to Types.xml (anywhere)

<type name="Animal_Otter">
    <nominal>0</nominal>
    <lifetime>1800</lifetime>
    <restock>0</restock>
    <min>0</min>
    <quantmin>-1</quantmin>
    <quantmax>-1</quantmax>
    <cost>100</cost>
    <flags count_in_cargo="0" count_in_hoarder="0" count_in_map="1" count_in_player="0" crafted="0" deloot="0"/>
</type>
<type name="OtterSteakMeat">
	<nominal>0</nominal>
	<lifetime>14400</lifetime>
	<restock>0</restock>
	<min>0</min>
	<quantmin>-1</quantmin>
	<quantmax>-1</quantmax>
	<cost>100</cost>
	<flags count_in_cargo="0" count_in_hoarder="0" count_in_map="1" count_in_player="0" crafted="1" deloot="0"/>
	<category name="food"/>
</type>
<type name="OtterPelt">
	<nominal>0</nominal>
	<lifetime>14400</lifetime>
	<restock>0</restock>
	<min>0</min>
	<quantmin>-1</quantmin>
	<quantmax>-1</quantmax>
	<cost>100</cost>
	<flags count_in_cargo="0" count_in_hoarder="0" count_in_map="1" count_in_player="0" crafted="1" deloot="0"/>
	<category name="food"/>
</type>

<type name="Animal_Rabbit_Grey">
    <nominal>0</nominal>
    <lifetime>1800</lifetime>
    <restock>0</restock>
    <min>0</min>
    <quantmin>-1</quantmin>
    <quantmax>-1</quantmax>
    <cost>100</cost>
    <flags count_in_cargo="0" count_in_hoarder="0" count_in_map="1" count_in_player="0" crafted="0" deloot="0"/>
</type>
<type name="Animal_Rabbit_Brown">
    <nominal>0</nominal>
    <lifetime>1800</lifetime>
    <restock>0</restock>
    <min>0</min>
    <quantmin>-1</quantmin>
    <quantmax>-1</quantmax>
    <cost>100</cost>
    <flags count_in_cargo="0" count_in_hoarder="0" count_in_map="1" count_in_player="0" crafted="0" deloot="0"/>
</type>

<type name="Animal_Rat_Grey">
    <nominal>0</nominal>
    <lifetime>1800</lifetime>
    <restock>0</restock>
    <min>0</min>
    <quantmin>-1</quantmin>
    <quantmax>-1</quantmax>
    <cost>100</cost>
    <flags count_in_cargo="0" count_in_hoarder="0" count_in_map="1" count_in_player="0" crafted="0" deloot="0"/>
</type>
<type name="Animal_Rat_White">
    <nominal>0</nominal>
    <lifetime>1800</lifetime>
    <restock>0</restock>
    <min>0</min>
    <quantmin>-1</quantmin>
    <quantmax>-1</quantmax>
    <cost>100</cost>
    <flags count_in_cargo="0" count_in_hoarder="0" count_in_map="1" count_in_player="0" crafted="0" deloot="0"/>
</type>
<type name="SkinnedRat">
	<nominal>0</nominal>
	<lifetime>14400</lifetime>
	<restock>0</restock>
	<min>0</min>
	<quantmin>-1</quantmin>
	<quantmax>-1</quantmax>
	<cost>100</cost>
	<flags count_in_cargo="0" count_in_hoarder="0" count_in_map="1" count_in_player="0" crafted="1" deloot="0"/>
	<category name="food"/>
</type>
<type name="DeadRat_Grey">
	<nominal>0</nominal>
	<lifetime>14400</lifetime>
	<restock>0</restock>
	<min>0</min>
	<quantmin>-1</quantmin>
	<quantmax>-1</quantmax>
	<cost>100</cost>
	<flags count_in_cargo="0" count_in_hoarder="0" count_in_map="1" count_in_player="0" crafted="1" deloot="0"/>
	<category name="food"/>
</type>
<type name="DeadRat_White">
	<nominal>0</nominal>
	<lifetime>14400</lifetime>
	<restock>0</restock>
	<min>0</min>
	<quantmin>-1</quantmin>
	<quantmax>-1</quantmax>
	<cost>100</cost>
	<flags count_in_cargo="0" count_in_hoarder="0" count_in_map="1" count_in_player="0" crafted="1" deloot="0"/>
	<category name="food"/>
</type>

<type name="Animal_Raven">
    <nominal>0</nominal>
    <lifetime>1800</lifetime>
    <restock>0</restock>
    <min>0</min>
    <quantmin>-1</quantmin>
    <quantmax>-1</quantmax>
    <cost>100</cost>
    <flags count_in_cargo="0" count_in_hoarder="0" count_in_map="1" count_in_player="0" crafted="0" deloot="0"/>
</type>
<type name="Animal_Raven2">
    <nominal>0</nominal>
    <lifetime>1800</lifetime>
    <restock>0</restock>
    <min>0</min>
    <quantmin>-1</quantmin>
    <quantmax>-1</quantmax>
    <cost>100</cost>
    <flags count_in_cargo="0" count_in_hoarder="0" count_in_map="1" count_in_player="0" crafted="0" deloot="0"/>
</type>
<type name="Animal_Raven_Airborne">
    <nominal>0</nominal>
    <lifetime>1800</lifetime>
    <restock>0</restock>
    <min>0</min>
    <quantmin>-1</quantmin>
    <quantmax>-1</quantmax>
    <cost>100</cost>
    <flags count_in_cargo="0" count_in_hoarder="0" count_in_map="1" count_in_player="0" crafted="0" deloot="0"/>
</type>

<type name="Animal_Seagull">
    <nominal>0</nominal>
    <lifetime>1800</lifetime>
    <restock>0</restock>
    <min>0</min>
    <quantmin>-1</quantmin>
    <quantmax>-1</quantmax>
    <cost>100</cost>
    <flags count_in_cargo="0" count_in_hoarder="0" count_in_map="1" count_in_player="0" crafted="0" deloot="0"/>
</type>
<type name="Animal_Seagull_Airborne">
    <nominal>0</nominal>
    <lifetime>1800</lifetime>
    <restock>0</restock>
    <min>0</min>
    <quantmin>-1</quantmin>
    <quantmax>-1</quantmax>
    <cost>100</cost>
    <flags count_in_cargo="0" count_in_hoarder="0" count_in_map="1" count_in_player="0" crafted="0" deloot="0"/>
</type>

<type name="Animal_Snake">
        <nominal>0</nominal>
        <lifetime>1800</lifetime>
        <restock>0</restock>
        <min>0</min>
        <quantmin>-1</quantmin>
        <quantmax>-1</quantmax>
        <cost>100</cost>
        <flags count_in_cargo="0" count_in_hoarder="0" count_in_map="1" count_in_player="0" crafted="0" deloot="0"/>
    </type>
	
	<type name="Animal_Squirrel">
    <nominal>0</nominal>
    <lifetime>1800</lifetime>
    <restock>0</restock>
    <min>0</min>
    <quantmin>-1</quantmin>
    <quantmax>-1</quantmax>
    <cost>100</cost>
    <flags count_in_cargo="0" count_in_hoarder="0" count_in_map="1" count_in_player="0" crafted="0" deloot="0"/>
</type>
<type name="SkinnedSquirrel">
	<nominal>0</nominal>
	<lifetime>14400</lifetime>
	<restock>0</restock>
	<min>0</min>
	<quantmin>-1</quantmin>
	<quantmax>-1</quantmax>
	<cost>100</cost>
	<flags count_in_cargo="0" count_in_hoarder="0" count_in_map="1" count_in_player="0" crafted="1" deloot="0"/>
	<category name="food"/>
</type>
<type name="DeadSquirrel">
	<nominal>0</nominal>
	<lifetime>14400</lifetime>
	<restock>0</restock>
	<min>0</min>
	<quantmin>-1</quantmin>
	<quantmax>-1</quantmax>
	<cost>100</cost>
	<flags count_in_cargo="0" count_in_hoarder="0" count_in_map="1" count_in_player="0" crafted="1" deloot="0"/>
	<category name="food"/>
</type>

move the (otter_territories.xml) to your dayz mission folder (Missing.mapname\env)

move the (rabbit_territories.xml) to your dayz mission folder (Missing.mapname\env)

move the (rat_territories.xml) to your dayz mission folder (Missing.mapname\env)

move the (raven_territories.xml) to your dayz mission folder (Missing.mapname\env)

move the (seagull_territories.xml) to your dayz mission folder (Missing.mapname\env)

move the (snake_territories.xml) to your dayz mission folder (Missing.mapname\env)

move the (squirrel_territories.xml) to your dayz mission folder (Missing.mapname\env)

Save and restart your server.