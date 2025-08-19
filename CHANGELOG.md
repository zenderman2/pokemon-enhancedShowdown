# Changelog

## [1.0.0] - 2025-08-19

### Added
- Individual PP Ups per move (0-3 PP Ups per move independently)
- Complete item usage system with 40+ healing/status/revival items
- PP restoration items (Ether, Elixir, etc.)
- Extended team string format with PP Up data
- JSON format support for PP Ups
- Human-readable export format with PP Ups

### Modified
- `PokemonSet` interface to include `ppUps` array
- Team parser functions (`pack`, `unpack`, `import`, `export`)
- Pokémon constructor for PP calculation
- Move slot initialization with individual PP Up support
- `battle.ts` and `battle-queue.ts` to update changes regarding item usage action 

### Technical Changes
- Added `medicineEffects` object with comprehensive item database
- Enhanced battle action handling for item usage
- Proper TypeScript types for all new features