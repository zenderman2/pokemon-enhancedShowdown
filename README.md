# Pokémon Enhanced Showdown

A modified version of [Pokémon Showdown](https://github.com/smogon/pokemon-showdown) with additional features for enhanced battle simulation.

## 🚀 Installation 
```
git clone https://github.com/zenderman2/pokemon-enhancedShowdown.git
cd pokemon-enhancedShowdown
npm install
```

## ✨ New Features

- **Individual PP Ups per move**: Each move can have 0-3 PP Ups independently.
- **Full item usage system**: Use healing items, status cures, PP restoration, and revival items during battle on any Pokemon in the team.
- **Enhanced team building**: Support for PP Up data in team strings and JSON format.

## 📝 New Team Format

### Packed Format with PP Ups
``Name|Species|Item|Ability|Moves|Nature|EVs|Gender|IVs|Shiny|Level|Misc|PPUps``

#### **Example:**
```js
const team = "Rapidash|||FlashFire|disable,wildcharge,highhorsepower,flareblitz|Jolly|||2,31,31,30,31,31||88|255,,ultraball,,10,Fire|1,3,3,3";
```

### JSON Format
```json
[{
"name": "Rapidash",
"species": "Rapidash",
"ability": "Flash Fire",
"moves": ["disable", "wildcharge", "highhorsepower", "flareblitz"],
"nature": "Jolly",
"level": 88,
"ivs": { "hp": 2, "atk": 31, "def": 31, "spa": 30, "spd": 31, "spe": 31 },
"happiness": 255,
"pokeball": "ultraball",
"dynamaxLevel": 10,
"teraType": "Fire",
"ppUps": [1,3,3,3]
}]
```

#### **PP Ups Section:** `1,3,3,3` means:
- Disable: 1 PP Up → 24 PP (20 base + 20×0.2×1 = 20 + 4)
- Wild Charge: 3 PP Ups → 24 PP (15 base + 15×0.2×3 = 15 + 9)
- High Horsepower: 3 PP Ups → 16 PP (10 base + 10×0.2×3 = 10 + 6)
- Flare Blitz: 3 PP Ups → 24 PP (15 base + 15×0.2×3 = 15 + 9)

## 🎮 Item Usage Commands

### Basic Syntax:
``PLAYER USE ITEMNAME POKEMONSLOT``

### Examples:
```js
// Heal active Pokémon with Hyper Potion
stream.write(`p1 use Hyper Potion`)

// Cure paralysis on second Pokémon
stream.write(`p1 use Paralyze Heal 2`)

// Restore PP with Max Elixir on 6th Pokémon
stream.write(`p1 use Max Elixir 6`)

// Revive fainted Pokémon in slot 2
stream.write(`p1 use Revive 2`)

// Use Sacred Ash (revives all fainted)
stream.write(`p1 use Sacred Ash`)
```

## 🔄 Everything Else Same as Original

- **Battle mechanics:** Unchanged
- **Move effects:** Same as official Pokémon Showdown
- **Type chart:** Official type effectiveness
- **Abilities:** All abilities work normally
- **Formats:** All existing formats supported

## 🔧 Key Modifications

- Extended `PokemonSet` interface with `ppUps` array
- Modified team parser (`teams.ts`) for PP Up import/export
- Updated Pokémon constructor for individual move PP calculation
- Added comprehensive medicine/item usage system with 40+ items

## 🤝 Contributing

This project builds upon the excellent foundation of Pokémon Showdown. If you find bugs or want to suggest improvements:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is based on [Pokémon Showdown](https://github.com/smogon/pokemon-showdown) by Smogon University.
Licensed under the MIT License - see original project for details.

## 🙏 Credits

### Original Pokémon Showdown Team:
- **Owner:** Guangcong Luo [Zarel] - Development, Design, Sysadmin
- **Staff:** Andrew Werner [HoeenHero], Annika L. [Annika], Chris Monsanto [chaos], Kris Johnson [dhelmise], Leonard Craft III [DaWoblefet], Mathieu Dias-Martins [Marty-D], Mia A [Mia]
- **Contributors:** See [pokemonshowdown.com/credits](http://pokemonshowdown.com/credits)

### Enhanced Features:
- **PP Ups System & Item Usage:** [zenderman2]

---

**Start battling with enhanced control over your team's movepool and strategic item usage!**

