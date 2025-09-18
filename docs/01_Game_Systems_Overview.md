# Glitter Cloud Adventure: Game Systems Overview

## Introduction

Glitter Cloud Adventure is a dual-storyline RPG where players alternate between an arcade dungeon with JRPG combat and a surface world with strategy/4X elements. These worlds interact economically and narratively as Earth battles against the Galaxander corporation.

This document outlines the core game systems, their responsibilities, and how they interact.

## Core Game Systems

### Party System
- Maximum of 4 characters in active party
- 12 total playable characters
- Character swapping at designated rest points
- Front/back row formation system
- Cosmic power synergy between characters
- Relationship-based combo system

### Combat System
- Turn-based combat with initiative
- Cosmic power mechanics
- Relationship-based combos
- Formation bonuses
- Cosmic balance effects
- Character-specific abilities

### Character Progression
- Level-based stat growth
- Cosmic power unlocking
- Relationship development
- Skill acquisition
- Equipment customization
- Cosmic affinity growth

### Resource Management
- HP/MP management
- Cosmic power points
- Relationship points
- Inventory management
- Currency systems
- Consumable items

## Game Modes

### Arcade Dungeon (JRPG)
- Party-based exploration
- Turn-based combat
- Cosmic power usage
- Character relationships
- Story progression
- Side quests

### Surface World (Strategy)
- Resource management
- Base building
- Character recruitment
- Research and development
- Combat operations
- Story progression

## Core Game Loop

### Arcade Dungeon Loop
1. Exploration
   - Navigate dungeons
   - Find treasures
   - Discover secrets
   - Meet characters

2. Combat
   - Engage enemies
   - Use cosmic powers
   - Execute combos
   - Manage resources

3. Character Development
   - Level up
   - Learn skills
   - Develop relationships
   - Unlock cosmic powers

4. Story Progression
   - Complete objectives
   - Advance plot
   - Unlock new areas
   - Meet new characters

### Surface World Loop
1. Base Management
   - Build facilities
   - Train units
   - Research tech
   - Manage resources

2. Operations
   - Plan missions
   - Deploy units
   - Complete objectives
   - Gather intel

3. Character Development
   - Recruit characters
   - Train skills
   - Build relationships
   - Unlock abilities

4. Story Progression
   - Complete missions
   - Advance plot
   - Unlock new areas
   - Meet new characters

## System Integration

### Character System
- Stats and attributes
- Skills and abilities
- Equipment and items
- Cosmic powers
- Relationships
- Progression

### Combat System
- Turn management
- Action processing
- Effect application
- Cosmic balance
- Combo system
- Formation bonuses

### Resource System
- Currency management
- Item inventory
- Equipment management
- Cosmic power points
- Relationship points
- Consumable items

### Story System
- Quest management
- Character events
- Plot progression
- World state
- Relationship events
- Cosmic revelations

## Technical Implementation

### State Management
- Game state
- Character state
- Combat state
- Resource state
- Story state
- Relationship state

### Event System
- Combat events
- Story events
- Character events
- System events
- UI events
- Cosmic events

### Save System
- Game progress
- Character data
- Inventory state
- Story progress
- Relationship data
- Cosmic power data

## Performance Considerations

### Optimization
- Asset management
- State caching
- Event batching
- Memory management
- Load balancing
- Update efficiency

### Scalability
- System modularity
- Content expansion
- Feature addition
- Performance scaling
- Memory scaling
- Load handling

## System Architecture

### 1. Tower Defense System

```
┌───────────────────────────────────────────────────────────────────────────────┐
│  TOWER DEFENSE SYSTEM                                                       │
├───────────────────────────────────┬─────────────────────────────────────────┤
│  PURPOSE                          │  Manages tower defense gameplay         │
│                                   │  against waves of enemies               │
├───────────────────────────────────┼─────────────────────────────────────────┤
│  KEY FEATURES                    │  TOWER TYPES                           │
├───────────────────────────────────┼─────────────────────────────────────────┤
│  • Wave-based enemy spawning      │  • Basic: Balanced, low cost           │
│  • Tower placement/upgrading      │  • Splash: Area damage, anti-group      │
│  • Resource management            │  • Sniper: Long range, single-target    │
│  • Special abilities/power-ups    │  • Support: Buffs/debuffs, utility      │
│  • Conscript deployment           │  • Conscript: Deploys captured units    │
│                                   │                                         │
│  ────────────────────────────────  │  ───────────────────────────────────  │
│                                   │                                         │
│  INTERACTIONS                     │  UPGRADE PATHS                         │
│  • Conscription System: Units     │  • Damage: Increase attack power        │
│  • Resource System: Building costs│  • Range: Extend attack distance        │
│  • Achievement System: Milestones │  • Speed: Faster attack rate           │
│                                   │  • Special: Unique abilities           │
└───────────────────────────────────┴─────────────────────────────────────────┘
```

### 2. Mini-Game System

```
┌───────────────────────────────────────────────────────────────────────────────┐
│  MINI-GAME SYSTEM                                                          │
├───────────────────────────────────┬─────────────────────────────────────────┤
│  PURPOSE                          │  Provides engaging side activities     │
│                                   │  with valuable rewards                 │
├───────────────────────────────────┼─────────────────────────────────────────┤
│  MINI-GAME TYPES                 │  KEY FEATURES                         │
├───────────────────────────────────┼─────────────────────────────────────────┤
│  • Memory Match: Card matching    │  • Score-based progression            │
│  • Endless Faller: Dodge & collect│  • Daily challenges & events          │
│  • Rhythm Game: Beat-based action │  • Leaderboard integration             │
│  • Tower Defense: Wave survival   │  • Unlockable content                 │
│  • Puzzle Challenges: Brain teasers│  • Special event mini-games           │
│                                   │                                         │
│  ────────────────────────────────  │  ───────────────────────────────────  │
│                                   │                                         │
│  REWARDS                         │  PROGRESSION                         │
│  • In-game currency              │  • Unlock new mini-games              │
│  • Exclusive items               │  • Earn experience points             │
│  • Character upgrades            │  • Increase difficulty levels         │
│  • Cosmetic unlocks              │  • Unlock special abilities           │
└───────────────────────────────────┴─────────────────────────────────────────┘
```
- Tracks progress for achievements

### 3. Conscription System

```
┌───────────────────────────────────────────────────────────────────────────────┐
│  CONSCRIPTION SYSTEM                                                       │
├───────────────────────────────────┬─────────────────────────────────────────┤
│  PURPOSE                          │  Captures and deploys enemy units      │
│                                   │  as powerful allies                     │
├───────────────────────────────────┼─────────────────────────────────────────┤
│  CAPTURE MECHANICS               │  CONSCRIPT TYPES                       │
├───────────────────────────────────┼─────────────────────────────────────────┤
│  • Chance-based success           │  • Melee: Frontline fighters           │
│  • Affected by enemy HP/type      │  • Ranged: Support from distance       │
│  • Special capture items          │  • Specialists: Unique abilities       │
│  • Some enemies immune            │  • Elites: Rare, powerful variants     │
│  • Failed attempts may anger      │  • Bosses: Special capture conditions  │
│                                   │                                         │
│  ────────────────────────────────  │  ───────────────────────────────────  │
│                                   │                                         │
│  DEPLOYMENT                      │  PROGRESSION & UPGRADES              │
│  • Tower Defense waves           │  • Level up through battles            │
│  • Dungeon exploration           │  • Train to improve stats              │
│  • Special missions              │  • Evolve into advanced forms          │
│  • Base defense                 │  • Unlock special abilities            │
└───────────────────────────────────┴─────────────────────────────────────────┘
```
- Tracks relationships with Character System

### 4. Character System

```
┌───────────────────────────────────────────────────────────────────────────────┐
│  CHARACTER SYSTEM                                                           │
├───────────────────────────────────┬─────────────────────────────────────────┤
│  PURPOSE                          │  Manages player characters, their       │
│                                   │  progression, and party dynamics        │
├───────────────────────────────────┼─────────────────────────────────────────┤
│  CHARACTER ATTRIBUTES             │  PROGRESSION                           │
├───────────────────────────────────┼─────────────────────────────────────────┤
│  • Strength: Physical damage      │  • Level up through experience         │
│  • Dexterity: Hit/evasion        │  • Stat points distribution            │
│  • Vitality: HP/defense          │  • Skill point allocation              │
│  • Intelligence: Magic power     │  • Unlock new abilities                │
│  • Luck: Critical hits/drops     │  • Class advancements                  │
│                                   │                                         │
│  ────────────────────────────────  │  ───────────────────────────────────  │
│                                   │                                         │
│  PARTY MANAGEMENT                │  INTERACTIONS                         │
│  • Up to 6 characters in party   │  • Combat System: Provides stats       │
│  • Formation bonuses             │  • Mini-Game System: Affects outcomes  │
│  • Character relationships       │  • Quest System: Story progression     │
│  • Equipment & loadouts          │  • Conscription: Special abilities     │
└───────────────────────────────────┴─────────────────────────────────────────┘
```

### 2. Combat System

**Purpose:** Handles all aspects of turn-based battles using dice mechanics.

**Key Features:**
- Initiative determination based on character speed
- Action selection (attack, skill, item, etc.)
- Dice-based hit resolution and damage calculation
- Status effect application and management
- Turn sequencing and battle flow
- Enemy AI behavior patterns
- **Party Combo System** for special multi-character attacks

**Mechanics:**
- Base hit chance determined by attacker's dexterity vs defender's evasion
- Damage calculation using dice rolls modified by character stats
- Critical hits based on fortune stat
- Status effects with duration tracking
- Combo meters that build up during battle, enabling special joint attacks

**Combo System:**
- Characters build affinity through fighting together
- Specific character pairs unlock unique combo attacks
- Combo attacks trigger based on special action sequences or timing-based minigames
- Combo effectiveness scales with character relationship levels
- Discovery system for finding new combinations and effects

**Interactions:**
- Receives character and enemy data from Character System
- Reports combat results to Reward System
- Integrates with UI System for combat visualization

### 3. Relic System

**Purpose:** Manages special items that unlock new abilities, areas, and game features.

**Key Features:**
- Relic acquisition through gameplay
- Fury accumulation for relic leveling
- Ability unlocking based on relic level
- Relic mastery for permanent ability retention
- Equipment slots for active relics (2 slots)

**Progression:**
- Level 1-6 for each relic
- Each level provides stats and new abilities
- Mastery at max level allows retention of abilities when unequipped

**Interactions:**
- Integrates with Character System for stat bonuses
- Provides ability unlocks to Combat System
- Triggers storyline advancement through Story System

### 4. Inventory System

**Purpose:** Manages items, equipment, and resources.

**Key Features:**
- Item acquisition, storage, and usage
- Equipment management and stat application
- Material organization
- Currency tracking
- Item trading between storylines

**Interactions:**
- Provides equipment data to Character System
- Supplies consumables to Combat System
- Exchanges resources with Resource Exchange System
- Integrates with UI for inventory management

### 5. World System

**Purpose:** Handles map navigation, area management, and world state.

**Key Features:**
- Area definition and transition management
- NPC placement and interaction
- Object placement and interaction
- Collision detection and movement
- Environmental effects and time tracking

**Interactions:**
- Provides location data to Story System
- Triggers Combat System for enemy encounters
- Initiates dialogue through Dialogue System
- Activates Mini-Games through Mini-Game System

### 6. Mini-Game System

**Purpose:** Manages arcade-style mini-games within the main game.

**Key Features:**
- Mini-game initialization with character stat integration
- Score tracking and high score management
- Reward calculation based on performance
- Game-specific mechanics and rules

**Types:**
- Endless fallers
- Minesweeper-style puzzles
- Side-scrolling beat-em-ups
- Shooter games (asteroids style)
- Strategy/simulation games

**Interactions:**
- Receives character data from Character System for difficulty scaling
- Reports scores and completion to Reward System
- Provides rewards to Inventory System

### 7. Resource Exchange System

**Purpose:** Facilitates the transfer of resources between dungeon and surface storylines.

**Key Features:**
- Resource transport from dungeon to surface
- Item procurement from surface to dungeon
- Enemy conscription from dungeon to surface
- Citizen assignment to dungeon resource gathering

**Mechanics:**
- Transfer queues for pending exchanges
- Delayed delivery based on game time
- Resource transformation during transfer
- Exchange rates and balance mechanisms

**Interactions:**
- Connects Inventory Systems between storylines
- Integrates with Economy System for pricing
- Reports transfers to UI System for notifications

### 8. Surface Management System

**Purpose:** Handles the strategy/4X gameplay on the surface world.

**Key Features:**
- Resource production and management
- Building construction and upgrading
- Research and technology progression
- Defense management against enemy waves
- Citizen assignment and specialization

**Interactions:**
- Provides resources to Resource Exchange System
- Receives conscripted enemies from Combat System
- Reports surface status to Story System
- Integrates with UI System for management interface

### 9. Story System

**Purpose:** Manages narrative progression, quests, and story branching.

**Key Features:**
- Main storyline tracking and advancement
- Quest management and completion tracking
- Dialogue sequencing and choice tracking
- Event triggering based on player actions
- Achievement tracking

**Quest System:**
- All quests are given by Glitch, who acts as the player's guide
- Glitch's memory fragments unlock new quests
- Quest progression tied to Glitch's memory recovery
- Quest rewards often help Glitch recover more memories
- Quest dialogue reflects Glitch's snarky personality
- Quest objectives often involve exploring areas Glitch remembers

**Interactions:**
- Receives location data from World System
- Triggers cutscenes through UI System
- Provides quest objectives to various systems
- Reports story progress to unlock new content
- Integrates with Glitch's memory system

### 10. Save System

**Purpose:** Handles game state persistence between sessions.

**Key Features:**
- Comprehensive state saving
- Multiple save slots
- Auto-save functionality
- Version migration for updates
- Save data validation and error recovery

**Interactions:**
- Collects state data from all other systems
- Restores state data to all systems during load

## Data Flow Diagram

```
┌─────────────────┐        ┌─────────────────┐
│  Arcade Dungeon  │◄─────►│  Surface World   │
└────────┬────────┘        └────────┬────────┘
         │                          │
         ▼                          ▼
┌─────────────────┐        ┌─────────────────┐
│  Character      │        │  Surface        │
│  System         │        │  Management     │
└────────┬────────┘        └────────┬────────┘
         │                          │
         ▼                          ▼
┌─────────────────┐        ┌─────────────────┐
│  Combat         │        │  Defense        │
│  System         │        │  System         │
└────────┬────────┘        └────────┬────────┘
         │                          │
         ▼                          ▼
┌─────────────────┐        ┌─────────────────┐
│  Inventory      │◄─────►│  Resource        │◄─────►│  Inventory      │
│  (Dungeon)      │        │  Exchange       │        │  (Surface)      │
└────────┬────────┘        └────────┬────────┘        └────────┬────────┘
         │                          │                          │
         ▼                          ▼                          ▼
┌─────────────────┐        ┌─────────────────┐        ┌─────────────────┐
│  Mini-Game      │        │  Story          │        │  Building       │
│  System         │        │  System         │        │  System         │
└─────────────────┘        └─────────────────┘        └─────────────────┘
```

## Key Interactions

1. **Character ↔ Combat**: Character system provides stats and abilities; Combat system returns experience and rewards.

2. **Dungeon ↔ Surface**: Resource Exchange system facilitates transfer of items, resources, and entities between storylines.

3. **Character ↔ Mini-Games**: Character stats influence mini-game difficulty and parameters; mini-games provide rewards and progression.

4. **World ↔ Story**: World state and locations trigger story events; story progression unlocks new areas and content.

5. **Combat ↔ Reward**: Combat results determine rewards; reward system distributes experience, items, and currency.

## Implementation Priorities

1. **Foundation Layer**
   - Core framework and namespaces
   - Event system
   - State management

2. **Gameplay Core**
   - Character system
   - Combat system
   - World navigation

3. **Progression Systems**
   - Relic system
   - Inventory management
   - Experience and leveling

4. **Storyline Connection**
   - Resource exchange
   - Surface management basics
   - Story progression framework

5. **Content Expansion**
   - Mini-games
   - Additional areas and enemies
   - Complex surface management

## Conclusion

This systems overview provides a high-level understanding of how Glitter Cloud Adventure's components work together to create a cohesive gameplay experience spanning two distinct but interconnected game modes. The modular architecture allows for incremental development and expansion while maintaining clear separation of concerns between systems.

The next design documents will dive deeper into specific systems, starting with the Data Models & Schemas document that will define the structure of all major game objects.

### **System Definition: Initial Game Flow**

**1. Purpose:**
To seamlessly onboard the player into the world of *Glittercloud Adventure* by integrating the introductory narrative with core gameplay mechanics. This flow covers the sequence from starting a new game to the point where the player gains control of their character in the main game world.

**2. Sequence of Events:**

*   **Phase 1: Start Screen**
    *   The player is presented with the main title screen.
    *   A "Start Game" button is prominently displayed.
    *   Clicking "Start Game" initiates the Intro Cutscene.

*   **Phase 2: Intro Cutscene**
    *   A non-interactive, skippable cutscene plays, establishing the core narrative: Earth's purchase by the Galaxander Corporation and the forced entry of its inhabitants into an intergalactic game show.
    *   **Player Interaction:**
        *   A single click (or keypress) during a scene's text animation will instantly complete the animation.
        *   A second click will advance to the next scene.
        *   A dedicated "Skip" button (or holding a key like `Esc`) will end the entire cutscene and proceed directly to the First Encounter.
    *   The cutscene must use full-screen background images to be immersive.

*   **Phase 3: First Encounter**
    *   Immediately following the cutscene, a scripted, non-repeatable encounter begins.
    *   **Narrative:** Hazel, the player character, faces their first enemy (e.g., an Arcade Goblin) and meets their first party member (e.g., Zara).
    *   **Gameplay:** This sequence will serve as a tutorial for the combat system. It will be a simplified turn-based battle.
    *   **Rewards:** Upon successful completion, the player is granted:
        *   Starting **Experience Points** and **Gold**.
        *   A basic set of **Items** (e.g., Health Potion).
        *   Initial **Equipment** (e.g., a weapon and armor).
        *   Their first **Party Member** joins them.
    *   The encounter transitions directly to the main game loop upon completion.

*   **Phase 4: Transition to Main Game**
    *   The encounter overlay fades out.
    *   The main game UI (HUD, etc.) becomes visible.
    *   The player now has full control of their character (Hazel) and can move around the game world.
    - The `game.html` canvas becomes visible.
