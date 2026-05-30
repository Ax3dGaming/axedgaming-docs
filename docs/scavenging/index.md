# Scavenging

Scavenging is a data-driven system that allows players to search blocks for loot.

Recipes define:

* Which block can be scavenged
* Which tool is required (optional)
* Whether the tool takes durability damage
* Which items can be obtained
* The chance of obtaining each item

Scavenging is designed for:

* Modpack creators
* Datapack creators
* KubeJS users

## Features

* Fully datapack driven
* Fully KubeJS compatible
* JEI support
* Multiple outputs per recipe
* Individual drop chances
* Optional bare-hand recipes
* Optional durability consumption

## Example

A player right-clicks sand using a stone shovel.

The recipe may return:

* Cobblestone (75%)
* Flint (25%)
* Diamond (1%)

Each output is rolled independently.
