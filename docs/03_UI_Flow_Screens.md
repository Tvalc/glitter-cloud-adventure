# Glitter Cloud Adventure: UI Flow & Screens

## Introduction

This document defines the user interface architecture, screen flows, and UI components for Glitter Cloud Adventure. The UI is designed to support both dungeon (JRPG) and surface (strategy) gameplay modes while maintaining a cohesive visual style and intuitive navigation.

## Core UI Screens

### Main Menu
```
┌─────────────────────────────────────────────────────────┐
│  Glitter Cloud Adventure                                │
├─────────────────────────────────────────────────────────┤
│  [New Game]                                            │
│  [Continue]                                            │
│  [Options]                                             │
│  [Credits]                                             │
└─────────────────────────────────────────────────────────┘
```

### Party Management Screen
```
┌─────────────────────────────────────────────────────────┐
│  Party Management                                      │
├─────────────────────────────────────────────────────────┤
│  Active Party (4/4)                                    │
│  ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐                      │
│  │Char1│ │Char2│ │Char3│ │Char4│                      │
│  └─────┘ └─────┘ └─────┘ └─────┘                      │
├─────────────────────────────────────────────────────────┤
│  Available Characters                                  │
│  [Character List with Stats]                           │
├─────────────────────────────────────────────────────────┤
│  Cosmic Balance                                        │
│  [Harmony] [Chaos] [Stability]                         │
├─────────────────────────────────────────────────────────┤
│  [Save Formation] [Return]                             │
└─────────────────────────────────────────────────────────┘
```

### Battle Screen
```
┌─────────────────────────────────────────────────────────┐
│  Cosmic Balance Meter                                  │
│  [Harmony] [Chaos] [Stability]                         │
├─────────────────────────────────────────────────────────┤
│  Turn Order                                            │
│  [Character Icons with Turn Indicators]                │
├─────────────────────────────────────────────────────────┤
│  Enemy Area                                            │
│  [Enemy Sprites with HP Bars]                          │
├─────────────────────────────────────────────────────────┤
│  Party Area (4 characters)                             │
│  ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐                      │
│  │Char1│ │Char2│ │Char3│ │Char4│                      │
│  └─────┘ └─────┘ └─────┘ └─────┘                      │
├─────────────────────────────────────────────────────────┤
│  Action Menu                                           │
│  [Attack] [Skills] [Cosmic] [Combo] [Items] [Defend]   │
└─────────────────────────────────────────────────────────┘
```

### Character Status Screen
```
┌─────────────────────────────────────────────────────────┐
│  Character Status                                      │
├─────────────────────────────────────────────────────────┤
│  Basic Info                                            │
│  Name: [Character Name]                                │
│  Level: [Level]                                        │
│  HP: [Current/Total]                                   │
│  MP: [Current/Total]                                   │
├─────────────────────────────────────────────────────────┤
│  Stats                                                 │
│  Strength: [Value]                                     │
│  Defense: [Value]                                      │
│  Speed: [Value]                                        │
│  Cosmic Affinity: [Value]                              │
├─────────────────────────────────────────────────────────┤
│  Cosmic Powers                                         │
│  [List of Available Powers]                            │
├─────────────────────────────────────────────────────────┤
│  Relationships                                         │
│  [Relationship Status with Other Characters]           │
└─────────────────────────────────────────────────────────┘
```

## UI Flow States

### Game Start Flow
1. Main Menu
   - New Game → Character Creation
   - Continue → Load Game
   - Options → Settings Menu
   - Credits → Credits Screen

2. Character Creation
   - Select Character Class
   - Customize Appearance
   - Set Initial Stats
   - Choose Starting Cosmic Power

3. Initial Tutorial
   - Basic Movement
   - Combat Basics
   - Party Management
   - Cosmic Power Usage

### Combat Flow
1. Battle Initiation
   - Enemy Encounter Animation
   - Party Formation Check
   - Cosmic Balance Initialization
   - Turn Order Calculation

2. Turn Execution
   - Action Selection
   - Target Selection
   - Effect Animation
   - Status Update

3. Combat Resolution
   - Victory/Defeat Screen
   - Reward Distribution
   - Experience Gain
   - Relationship Updates

### Party Management Flow
1. Character Selection
   - View Available Characters
   - Check Party Requirements
   - Verify Cosmic Balance
   - Confirm Changes

2. Formation Management
   - Front/Back Row Assignment
   - Cosmic Power Synergy
   - Relationship Bonuses
   - Save Formation

## UI Components

### Cosmic Balance Meter
- Visual representation of cosmic balance
- Color-coded sections for Harmony, Chaos, Stability
- Dynamic updates during combat
- Affects available actions and combos

### Relationship Indicators
- Shows relationship levels between characters
- Indicates available combos
- Displays relationship bonuses
- Updates after story events

### Action Menu
- Context-sensitive options
- Cosmic power availability
- Combo attack indicators
- Item usage restrictions

## Implementation Guidelines

### Screen Transitions
- Smooth fade effects
- Context preservation
- State management
- Error handling

### Input Handling
- Keyboard shortcuts
- Controller support
- Touch controls
- Context-sensitive help

### Performance Optimization
- Asset preloading
- State caching
- Efficient updates
- Memory management

### Accessibility Features
- Color blind mode
- Text scaling
- Audio cues
- Control customization

## Guide System (Glitch Stick Lv.1)

### Guide Summoning
- Accessible from the main menu or overworld (not during combat)
- Activated via 'Call Guide' button or hotkey
- Guide appears in a semi-transparent overlay

### Guide Interface - Main Screen
```
┌─────────────────────────────────────────────────────────────┐
│  GUIDE SYSTEM                                              │
├─────────────────────────────────────────────────────────────┤
│  [Close]  [Previous]                             [Next]    │
│                                                             │
│  "Welcome back, Glitch Hunter! What do you need help with?"  │
│                                                             │
│  • Active Quest: The Lost Codex                             │
│  • Quest Tasks:                                            │
│    1. [✓] Speak to the Archivist in Glitchport            │
│    2. [ ] Locate the Ancient Terminal in Sector 7           │
│    3. [ ] Decrypt the data fragments (0/3)                 │
│    4. [ ] Return to the Archivist                          │
│                                                             │
│  [Quests]  [Bestiary]  [Lore]  [Hints]                      │
└─────────────────────────────────────────────────────────────┘
```

### Bestiary Screen
```
┌─────────────────────────────────────────────────────────────┐
│  BESTIARY - AREA: GLITCHPORT DOCKS                         │
├─────────────────────────────────────────────────────────────┤
│  [Back]  [Filter: All]  [Search...]                        │
│                                                             │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐        │
│  │ Glitch Rat  │  │ Data Mite   │  │ Byte Bat    │        │
│  │ Lv. 2-4     │  │ Lv. 3-5     │  │ Lv. 4-6     │        │
│  │ ⚡Weak: Fire │  │ ⚡Weak: Water│  │ ⚡Weak: Light│        │
│  └─────────────┘  └─────────────┘  └─────────────┘        │
│                                                             │
│  ┌───────────────────────────────────────────────────────┐  │
│  │  GLITCH RAT                                         │  │
│  │  HP: 25       MP: 5        Weak: Fire               │  │
│  │  XP: 15        Gold: 5-8                             │  │
│  │  Drops: Glitch Fragment (80%), Rat Tail (30%)       │  │
│  │  "Small corrupted creatures that swarm in numbers."  │  │
│  └───────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────┘
```

### Guide Features
- **Quest Management**: Track and change active quests
- **Task Tracking**: Detailed breakdown of current objectives
- **Bestiary**: Enemy information organized by area/level
- **Lore Archive**: World-building and story elements
- **Contextual Hints**: Dynamic tips based on current progress

## UI Architecture (Single HTML File)

The UI is implemented using a single HTML file with dynamic content switching:

```html
<!-- Main container -->
<div id="game-container">
  <!-- Screens are shown/hidden via CSS classes -->
  <div id="title-screen" class="screen active">
    <!-- Title screen content -->
  </div>
  
  <div id="game-screen" class="screen">
    <!-- Game HUD -->
    <div id="hud">
      <div id="health-bar" class="status-bar"></div>
      <div id="mp-bar" class="status-bar"></div>
      <div id="skill-bar" class="skill-bar">
        <!-- Dynamically populated skills -->
      </div>
    </div>
    
    <!-- Dialog/Notification System -->
    <div id="notification-container"></div>
    
    <!-- Modal Windows -->
    <div id="modal-container"></div>
  </div>
  
  <!-- Other screens... -->
</div>
```

### UI Management

```javascript
// In GCA.UI
GCA.UI = (function() {
  const screens = {};
  let currentScreen = null;
  
  // Initialize UI components
  function init() {
    // Cache screen elements
    document.querySelectorAll('.screen').forEach(screen => {
      screens[screen.id] = screen;
    });
    
    // Set up event listeners
    setupEventListeners();
  }
  
  // Show a screen
  function showScreen(screenId, data = {}) {
    if (currentScreen) {
      currentScreen.classList.remove('active');
    }
    
    const screen = screens[screenId];
    if (screen) {
      screen.classList.add('active');
      currentScreen = screen;
      
      // Trigger screen-specific initialization
      const initFn = `init${screenId.charAt(0).toUpperCase() + screenId.slice(1)}`;
      if (typeof GCA.UI[initFn] === 'function') {
        GCA.UI[initFn](data);
      }
    }
  }
  
  // Show notification
  function showNotification(message, type = 'info', duration = 3000) {
    const notification = document.createElement('div');
    notification.className = `notification ${type}`;
    notification.textContent = message;
    
    const container = document.getElementById('notification-container');
    container.appendChild(notification);
    
    setTimeout(() => {
      notification.classList.add('fade-out');
      setTimeout(() => notification.remove(), 500);
    }, duration);
  }
  
  // Public API
  return {
    init,
    showScreen,
    showNotification,
    // Other public methods...
  };
})();

// Initialize UI when DOM is loaded
document.addEventListener('DOMContentLoaded', GCA.UI.init);

## Global UI Elements

These elements appear across multiple screens and maintain consistency:

### Navigation Bar
- Always visible at the top of the screen (except during cutscenes)
- Shows current location, time/day indicator, and main menu button
- Quick-access buttons for inventory, character, and storyline switching

### Notification System
- Appears in the top-right corner
- Shows quest updates, item acquisitions, and system messages
- Special notifications for level ups and new skill unlocks
- Notifications fade after a few seconds but can be reviewed in the log

### Level Up Notification
```
┌─────────────────────────────────────────────┐
│  ⭐ LEVEL UP!                              │
│  Alex reached Level 5!                     │
│                                             │
│  Stats Increased:                          │
│  • HP +10                                  │
│  • MP +5                                   │
│  • Attack +3                               │
│                                             │
│  [View Skills]    [Continue]               │
└─────────────────────────────────────────────┘
```
- Appears immediately upon leveling up
- Shows stat increases from level up
- 'View Skills' shows detailed skill unlocks
- 'Continue' returns to game
- Auto-dismisses after 5 seconds if no input

### Skill Unlock Screen
```
┌─────────────────────────────────────────────┐
│  NEW SKILL UNLOCKED!                       │
│  ┌─────────────────────────────────────┐  │
│  │  Power Strike                      │  │
│  │  [ICON]                            │  │
│  │  Deals 150% damage to one target   │  │
│  │  Cost: 5 MP                        │  │
│  └─────────────────────────────────────┘  │
│  [OK]                                      │
└─────────────────────────────────────────────┘
```
- Detailed view of newly unlocked skills
- Shows skill description, effects, and cost
- Includes visual representation of the skill

### Context Menu
- Right-click (or long press) on game elements to show context actions
- Contextual options based on the type of element (NPC, item, environment)

## Screen Flow Diagram

```
┌─────────────────┐
│  Title Screen   │
└────────┬────────┘
         │
         ▼
┌─────────────────┐     ┌─────────────────┐
│  New Game       │────►│  Character      │
│                 │     │  Creation       │
└────────┬────────┘     └────────┬────────┘
         │                       │
         │                       ▼
         │              ┌─────────────────┐
         │              │  Introduction   │
         │              │  Cutscene       │
         │              └────────┬────────┘
         │                       │
         ▼                       │
┌─────────────────┐              │
│  Load Game      │              │
└────────┬────────┘              │
         │                       │
         ▼                       ▼
┌─────────────────┐     ┌─────────────────┐
│  Options        │◄────┤  Main Game UI   │◄────┐
└─────────────────┘     └────────┬────────┘     │
                                 │               │
                 ┌───────────────┼───────────────┼───────────┐
                 │               │               │           │
                 ▼               ▼               ▼           ▼
         ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐
         │  Dungeon    │ │  Surface    │ │  Mini-Game  │ │  Storyline  │
         │  Mode       │ │  Mode       │ │  Screen     │ │  Switch     │
         └──────┬──────┘ └──────┬──────┘ └──────┬──────┘ └──────┬──────┘
                │               │               │               │
                └───────────────┴───────────────┴───────────────┘
```

## Screen Descriptions

### Tower Defense Mode
```
┌─────────────────────────────────────────────────────────────┐
│  Wave: 3/10  Lives: 15  Gold: 450  Energy: 75/100         │
├─────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────┐  │
│  │  [Tower Menu]  [Upgrades]  [Abilities]  [Conscripts] │  │
│  │  ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐    │  │
│  │  │     │ │     │ │     │ │     │ │     │ │     │    │  │
│  │  │     │ │     │ │     │ │     │ │     │ │     │    │  │
│  │  └─────┘ └─────┘ └─────┘ └─────┘ └─────┘ └─────┘    │  │
│  │  [Basic] [Splash] [Sniper] [Support] [Conscript]     │  │
│  │  Cost: 100   150     200      150        200        │  │
│  └───────────────────────────────────────────────────────┘  │
│  Next Wave in: 15s  [Start Wave Early]                     │
└─────────────────────────────────────────────────────────────┘
```


### Mini-Game Selection
```
┌─────────────────────────────────────────────────────────────┐
│  [X] Mini-Games                                 [Close]    │
├─────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────┐  │
│  │  [Memory Match]  [Endless Faller]  [Rhythm]         │  │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  │  │
│  │  │   Memory    │  │   Endless   │  │   Rhythm    │  │  │
│  │  │   Match     │  │   Faller    │  │   Game      │  │  │
│  │  │   Score: 2500  │  │   Score: 1800  │  │   Score: 3200  │  │  │
│  │  └─────────────┘  └─────────────┘  └─────────────┘  │  │
│  │                                                     │  │
│  │  [Tactical Puzzle]  [Resource Rush]  [Coming Soon]  │  │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  │  │
│  │  │   Tactical  │  │   Resource  │  │    Locked   │  │  │
│  │  │   Puzzle    │  │   Rush      │  │             │  │  │
│  │  │   Score: 1800  │  │   Score: 2100  │  │             │  │  │
│  │  └─────────────┘  └─────────────┘  └─────────────┘  │  │
│  └───────────────────────────────────────────────────────┘  │
│  Daily Challenge: Match 15 pairs in Memory Match - 3/15     │
└─────────────────────────────────────────────────────────────┘
```

### Endless Faller Game
```
┌─────────────────────────────────────────────────────────────┐
│  Score: 1250  Distance: 350m  Speed: 2.5x  [Pause]        │
├─────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────┐  │
│  │  [Player]                                          │  │
│  │                                                     │  │
│  │         [Obstacle] [Obstacle]                       │  │
│  │                                                     │  │
│  │                 [Coin] [Coin] [Coin]                │  │
│  │                                                     │  │
│  │  [Powerup]                                         │  │
│  │                                                     │  │
│  │        [Obstacle]                                   │  │
│  │                                                     │  │
│  └───────────────────────────────────────────────────────┘  │
│  [Left]  [Right]  [Jump]  [Slide]  [Special]               │
└─────────────────────────────────────────────────────────────┘
```

### Memory Match Game
```
┌─────────────────────────────────────────────────────────────┐
│  Pairs: 2/10  Moves: 7  Time: 0:45  [Pause]  [Hint (3)]   │
├─────────────────────────────────────────────────────────────┤
│  ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐  │
│  │  ?  │ │  ?  │ │  ?  │ │  ?  │ │  ?  │ │  ?  │ │  ?  │  │
│  │     │ │     │ │     │ │     │ │     │ │     │ │     │  │
│  └─────┘ └─────┘ └─────┘ └─────┘ └─────┘ └─────┘ └─────┘  │
│  ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐  │
│  │  ?  │ │  ?  │ │  ?  │ │  ?  │ │  ?  │ │  ?  │ │  ?  │  │
│  │     │ │     │ │     │ │     │ │     │ │     │ │     │  │
│  └─────┘ └─────┘ └─────┘ └─────┘ └─────┘ └─────┘ └─────┘  │
│  ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐  │
│  │  ?  │ │  ?  │ │  ?  │ │  ?  │ │  ?  │ │  ?  │ │  ?  │  │
│  │     │ │     │ │     │ │     │ │     │ │     │ │     │  │
│  └─────┘ └─────┘ └─────┘ └─────┘ └─────┘ └─────┘ └─────┘  │
│  ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐  │
│  │  ?  │ │  ?  │ │  ?  │ │  ?  │ │  ?  │ │  ?  │ │  ?  │  │
│  │     │ │     │ │     │ │     │ │     │ │     │ │     │  │
│  └─────┘ └─────┘ └─────┘ └─────┘ └─────┘ └─────┘ └─────┘  │
│  ┌───────────────────────────────────────────────────────┐  │
│  │  [Shuffle (2)]  [Reveal Pair (1)]  [Extra Time (3)]  │  │
│  └───────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────┘
```

### Tower Defense - Conscript Deployment
```
┌─────────────────────────────────────────────────────────────┐
│  [X] Deploy Conscripts                          [Close]    │
├─────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────┐  │
│  │  Available Conscripts: 3/5                           │  │
│  │  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐    │  │
│  │  │ Byte Bug    │ │ Glitch Slime│ │ Data Hound  │    │  │
│  │  │ Lv.3        │ │ Lv.2        │ │ Lv.4        │    │  │
│  │  │ HP: 45/50   │ │ HP: 30/30   │ │ HP: 65/65   │    │  │
│  │  └─────────────┘ └─────────────┘ └─────────────┘    │  │
│  │  [Select Tower]  [Deploy]  [Recall]  [Info]          │  │
│  │                                                     │  │
│  │  Selected Tower: Basic Tower (0/2)                   │  │
│  │  [Assign Conscript]  [Upgrade Tower]  [Sell Tower]   │  │
│  └───────────────────────────────────────────────────────┘  │
│  Tip: Drag conscripts to towers or right-click to recall   │
└─────────────────────────────────────────────────────────────┘
```

### Mini-Game Results
```
┌─────────────────────────────────────────────────────────────┐
│  [X] Memory Match Results                      [Continue]  │
├─────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────┐  │
│  │  🏆  Memory Match Complete!  🏆                     │  │
│  │                                                     │  │
│  │  Pairs Matched: 10/10                               │  │
│  │  Moves: 12 (Perfect!)                               │  │
│  │  Time: 1:23                                        │  │
│  │  Score: 2,450  (New High Score!)                    │  │
│  │  Streak Bonus: x1.5                                 │  │
│  │                                                     │  │
│  │  Rewards:                                          │  │
│  │  - 150 Gold                                        │  │
│  │  - 1 Conscript Orb                                 │  │
│  │  - 2 Memory Shards                                 │  │
│  │                                                     │  │
│  │  [Play Again]  [Next Challenge]  [Exit]            │  │
│  └───────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────┘
```

## Screen Descriptions

### Title Screen
- Game logo and animated background
- Menu options: New Game, Load Game, Options, Credits
- Version number and Farcade integration status
- Background music and ambient animations

### Character Creation
- Character name input
- Class selection with descriptions and stat comparisons
- Appearance customization (color schemes)
- Starting stats preview
- Backstory hints

### Main Game UI (Dungeon Mode)
The primary interface maximizes the viewable game area with minimal UI elements, showing only essential information:

```
┌─────────────────────────────────────────────────────────────┐
│  [Crystal Caverns - Lv.3]  💰 1,245G           [Menu]     │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│                                                             │
│                                                             │
│                                                             │
│                                                             │
│                     GAME WORLD VIEW                         │
│                                                             │
│                                                             │
│                                                             │
│                                                             │
│                                                             │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Dungeon Debug Tools (Press F3)
*Accessible via F3 key during development*

#### Debug Overlay
```
┌─────────────────────────────────────────────────────────────────────────┐
│  [X] Dungeon Debug Tools                            [Close]            │
├─────────────────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────────────────┐  │
│  │  [Layers]  [Collision]  [Spawning]  [Triggers]  [AI Paths]      │  │
│  ├───────────────────────────────────────────────────────────────────┤  │
│  │  ┌─────────────┐  ┌─────────────────────────────────────────┐  │  │
│  │  │ [Collision] │  │  Selected Tile: (7,12)                    │  │  │
│  │  │ [x] Blocked  │  │  [Set Blocked]  [Set Walkable]          │  │  │
│  │  │ [x] Ledge    │  │  [Set Ledge]    [Set Spawn]             │  │  │
│  │  │ [x] Water    │  │  [Set Water]    [Set Special]           │  │  │
│  │  │ [x] Hazard   │  │  [Set Hazard]   [Clear Tile]            │  │  │
│  │  │             │  │                                       │  │  │
│  │  │ [Spawns]    │  │  Spawn Zones:                           │  │  │
│  │  │ [x] Player  │  │  [Add Spawn Zone]  [Remove Zone]        │  │  │
│  │  │ [x] Enemy   │  │  [Test Spawn]     [Clear All]           │  │  │
│  │  │ [x] NPC     │  │                                       │  │  │
│  │  │ [x] Item    │  │  Current Zone: Enemy Spawn (Radius: 3)  │  │  │
│  │  │             │  │  [Move]  [Resize]  [Properties]          │  │  │
│  │  └─────────────┘  └─────────────────────────────────────────┘  │  │
│  │                                                                   │  │
│  │  [Save Layout]  [Load Layout]  [Test]  [Reset]  [Close]           │  │
│  └───────────────────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────────────┘
```

#### Collision Layer Visualization
```
┌─────────────────────────────────────────────────────────────────────────┐
│  [X] Collision Map - Dungeon Level 1                      [Close]      │
├─────────────────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────────────────┐  │
│  │  [X] Blocked  [X] Ledges  [ ] Water  [ ] Hazards  [ ] Spawns    │  │
│  │  ┌───┬───┬───┬───┬───┬───┬───┬───┬───┬───┬───┬───┬───┬───┬───┐    │  │
│  │  │###│   │###│   │###│   │###│   │###│   │###│   │###│   │    │  │
│  │  ├───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┤    │  │
│  │  │   │###│   │###│   │###│   │###│   │###│   │###│   │###│    │  │
│  │  ├───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┤    │  │
│  │  │###│   │###│   │###│   │###│   │###│   │###│   │###│   │    │  │
│  │  ├───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┤    │  │
│  │  │   │###│   │###│   │###│   │###│   │###│   │###│   │###│    │  │
│  │  ├───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┤    │  │
│  │  │###│   │###│   │###│   │###│   │###│   │###│   │###│   │    │  │
│  │  ├───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┼───┤    │  │
│  │  │   │###│   │###│   │###│   │###│   │###│   │###│   │###│    │  │
│  │  └───┴───┴───┴───┴───┴───┴───┴───┴───┴───┴───┴───┴───┴───┴───┘    │  │
│  │  [1][2][3][4][5][6][7][8][9][10][11][12][13][14][15]              │  │
│  └───────────────────────────────────────────────────────────────────┘  │
│  [Save]  [Load]  [Test]  [Reset]  [Close]                               │
└─────────────────────────────────────────────────────────────────────────┘
```

#### Spawn Zone Editor
```
┌─────────────────────────────────────────────────────────────────────────┐
│  [X] Spawn Zone Editor - Dungeon Level 1                   [Close]      │
├─────────────────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────────────────┐  │
│  │  Zone Type: [Enemy Spawn ▼]  |  Radius: [▁▃▅▆▇ 3]              │  │
│  │  Spawn Rate: [▁▃▅▆▇ 60%]  |  Max Active: [2]                   │  │
│  │  Spawn List:                                                   │  │
│  │  ┌─────────────────────────────────────────────────────────┐    │  │
│  │  │ [✓] Goblin (40%)                                      │    │  │
│  │  │ [✓] Skeleton (30%)                                    │    │  │
│  │  │ [ ] Bat (20%)                                        │    │  │
│  │  │ [ ] Slime (10%)                                      │    │  │
│  │  │ [Add Enemy Type...]                                  │    │  │
│  │  └─────────────────────────────────────────────────────────┘    │  │
│  │  [Test Spawn]  [Clear Zone]  [Save]  [Cancel]                  │  │
│  └───────────────────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────────────┘
```

### Menu Overlay (Card-Based Layout)

#### 1. Status Tab (Default)
```
┌─────────────────────────────────────────────────────────────┐
│  [X] Menu > Status                             [Minimize ▼]  │
│  ◄ [Alex] ►  💰 1,245G                        1/3 Members  │
├─────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────┐  │
│  │  ┌─────────────┐  ┌─────────────────────────────┐  │  │
│  │  │  Character  │  │  Alex Lv.5 - Flexecutioner  │  │  │
│  │  │    Sprite   │  ├─────────────────────────────┤  │  │
│  │  │             │  │  HP: ████████████████████ 85/85  │  │  │
│  │  └─────────────┘  │  MP: ███████████ 35/35       │  │  │
│  │                   │  XP: █████████████ 1200/1500  │  │  │
│  │  ┌─────────────┐  ├─────────────────────────────┤  │  │
│  │  │  Equipment  │  │  STR: 10 (+2)  INT: 6       │  │  │
│  │  │  Head:      │  │  VIT: 8         DEX: 9       │  │  │
│  │  │  Body:      │  │  FOR: 7         CHA: 5       │  │  │
│  │  │  Weapon:    │  └─────────────────────────────┘  │  │
│  │  └─────────────┘                                   │  │
│  │  Active Effects: [XP Boost] [Well Rested]          │  │
│  └───────────────────────────────────────────────────┘  │
│  ◄─┐  Current Party: [Alex] [Maya] [Kai]  │►─►│
├─────────────────────────────────────────────────────────────┤
│  [Status]  [Skills]  [Equipment]  [Relics]  [Inventory]     │
└─────────────────────────────────────────────────────────────┘
```

#### 2. Skills Tab (List + Tooltip)
```
┌─────────────────────────────────────────────────────────────┐
│  [X] Menu > Skills                              [Minimize ▼]  │
│  💰 1,245G                                                     │
├─────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────┐  │
│  │  [All]  [Combat]  [Magic]  [Passive]  [Class]      │  │
│  ├───────────────────┬─────────────────────────────────┤  │
│  │  Power Strike Lv.3│  ┌─────────────────────────┐  │  │
│  │  Flex Taunt Lv.2  │  │ Name: Power Strike     │  │  │
│  │  Bulk Up Lv.1     │  │ Type: Physical - Attack │  │  │
│  │  Mighty Swing     │  │ MP: 8                  │  │  │
│  │  Intimidate       │  │ Effect: Deal 120% ATK  │  │  │
│  │  Adrenaline Rush  │  │ Cooldown: 2 turns      │  │  │
│  │  Ultimate Flex    │  │                        │  │  │
│  │                   │  │ "A powerful strike..." │  │  │
│  │  [Scrollable]     │  └─────────────────────────┘  │  │
│  └───────────────────┴─────────────────────────────────┘  │
├─────────────────────────────────────────────────────────────┤
│  [Status]  [Skills]  [Equipment]  [Relics]  [Inventory]     │
└─────────────────────────────────────────────────────────────┘
```

#### 3. Equipment Tab (List + Tooltip)
```
┌─────────────────────────────────────────────────────────────┐
│  [X] Menu > Equipment                         [Minimize ▼]  │
│  💰 1,245G                                                     │
├─────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────┐  │
│  │  [All]  [Weapons]  [Armor]  [Accessories]           │  │
│  ├───────────────────┬─────────────────────────────────┤  │
│  │  Head: [EMPTY]    │  ┌─────────────────────────┐  │  │
│  │  Body: Gym Tank   │  │  Workout Bandana       │  │  │
│  │  Weapon: Dumbells │  │  DEF: +3, STR +1       │  │  │
│  │  Off-hand: [NONE] │  │  "A stylish headband..."│  │  │
│  │  Relic 1: Glitch  │  │  [Equip] [Info]        │  │  │
│  │  Relic 2: [EMPTY] │  └─────────────────────────┘  │  │
│  │  Accessory: [NONE]│                                │  │
│  │                   │  [Change] [Optimize] [Auto]  │  │
│  │  [Scrollable]     │                                │  │
│  └───────────────────┴─────────────────────────────────┘  │
├─────────────────────────────────────────────────────────────┤
│  [Status]  [Skills]  [Equipment]  [Relics]  [Inventory]     │
└─────────────────────────────────────────────────────────────┘
```

#### 4. Relics Tab (List + Tooltip)
```
┌─────────────────────────────────────────────────────────────┐
│  [X] Menu > Relics                             [Minimize ▼]  │
│  💰 1,245G                                                     │
├─────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────┐  │
│  │  [Equipped]  [Available]  [Locked]                  │  │
│  ├───────────────────┬─────────────────────────────────┤  │
│  │  Glitch Stick    │  ┌─────────────────────────┐  │  │
│  │  [Slot 1]         │  │  Glitch Stick Lv.2      │  │  │
│  │  ---------------- │  │  Fury: 150/300          │  │  │
│  │  [EMPTY SLOT]    │  │  Abilities:             │  │  │
│  │  [Slot 2]         │  │  • Summon Guide         │  │  │
│  │                   │  │  • Summon Shop          │  │  │
│  │  Available:       │  │  • ??? (Lv.4)           │  │  │
│  │  • Pixel Compass  │  │                        │  │  │
│  │  • Codex Fragment │  │  [Equip] [Dismantle]   │  │  │
│  │                   │  └─────────────────────────┘  │  │
│  └───────────────────┴─────────────────────────────────┘  │
├─────────────────────────────────────────────────────────────┤
│  [Status]  [Skills]  [Equipment]  [Relics]  [Inventory]     │
└─────────────────────────────────────────────────────────────┘
```

#### 5. Inventory Tab (Universal)
```
┌─────────────────────────────────────────────────────────────┐
│  [X] Menu > Inventory                          [Minimize ▼]  │
│  💰 1,245G                                                     │
├─────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────┐  │
│  │  [All]  [Consumables]  [Materials]  [Key Items]     │  │
│  ├───────────────────┬─────────────────────────────────┤  │
│  │  Health Potion x5 │  ┌─────────────────────────┐  │  │
│  │  Mana Potion x3   │  │  Health Potion         │  │  │
│  │  Glow Shard x12   │  │  Restores 50 HP        │  │  │
│  │  Iron Ore x7      │  │  "A red potion that..."│  │  │
│  │  Mysterious Key   │  │  [Use] [Info] [Discard]│  │  │
│  │  Rope x3          │  └─────────────────────────┘  │  │
│  │  [Scrollable]     │                                │  │
│  └───────────────────┴─────────────────────────────────┘  │
│  [Sort: A-Z]  [Use]  [Discard]  [Storage]                  │
├─────────────────────────────────────────────────────────────┤
│  [Status]  [Skills]  [Equipment]  [Relics]  [Inventory]     │
└─────────────────────────────────────────────────────────────┘
```

### Card-Based Navigation System

1. **Character Status Cards**
   - Swipe or use arrow buttons to cycle through party members
   - Current character highlighted in party list
   - Smooth transitions between character cards

2. **List + Tooltip Pattern** (Skills/Equipment/Relics):
   - Left panel: Scrollable list of items/abilities
   - Right panel: Detailed tooltip view
   - Only one tooltip shown at a time
   - Click to select/deselect items

3. **Universal Controls**
   - `[X]` - Close menu
   - `[Minimize]` - Collapse to compact view
   - `[Tab]` - Cycle through tabs
   - `[1-5]` - Quick jump to tab
   - `[ESC]` - Close menu/tooltip
   - `[Mouse Wheel]` - Scroll lists
   - `[Click]` - Select item/action
   - `[Right-Click]` - Context menu

4. **Responsive Behavior**
   - On smaller screens, tooltip appears below list
   - Touch-friendly controls for mobile
   - Tooltips adapt to available space

### Dungeon Mode UI

#### Exploration View
- Character sprite centered in play area
- NPCs and interactive objects
- Minimap in corner showing explored areas
- Contextual action button for interactions
- Party members follow the leader

#### Combat View (Updated Layout)
- Side view for battle sequences
- Player characters on the right, enemies on the left
- Command menu at the bottom
- Turn order indicator
- Battle status indicators (HP/MP bars, status effects)
- Animation effects for actions

```
┌─────────────────────────────────────────────────────────────┐
│ Battle: [Enemy Group Name]                  Round: 3        │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│    [Enemy Group]                     [Player Party]         │
│                                                             │
│    Byte Bug                          Alex                   │
│    HP: ███████                        HP: ██████████         │
│    MP: █████                          MP: ████████           │
│                                                             │
│    Pixel Pirate                      Maya                   │
│    HP: █████████                      HP: ████████           │
│    MP: █████                          MP: ██████             │
│                                                             │
│    [Summon Companion]                                      │
│                                                             │
├─────────────────────────────┬───────────────────────────────┤
│ Turn Order:                 │ [Attack] [Skill] [Item] [Run] │
│ 1. Alex   2. Byte Bug       │ [Guard] [Summon] [Flee]       │
│ 3. Maya   4. Pixel Pirate   │                               │
└─────────────────────────────┴───────────────────────────────┘
```

### Companion Interaction Screens

#### 1. Companion Summoning Screen
```
┌─────────────────────────────────────────────────────────────┐
│ [X] Summon Companion                           [Dismiss]   │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│    ┌─────────────────────────────────────────────────┐     │
│    │                                                 │     │
│    │              [Companion Sprite]                 │     │
│    │                                                 │     │
│    └─────────────────────────────────────────────────┘     │
│    "How may I assist you today, traveler?"                  │
│                                                             │
│    ┌─────────────┐  ┌─────────────┐  ┌─────────────┐      │
│    │    Shop     │  │   Quests    │  │    Lore     │      │
│    └─────────────┘  └─────────────┘  └─────────────┘      │
│                                                             │
│    ┌─────────────┐  ┌─────────────────────────────┐      │
│    │   Advice    │  │        [Dismiss]            │      │
│    └─────────────┘  └─────────────────────────────┘      │
└─────────────────────────────────────────────────────────────┘
```

#### 2. Companion Shop
```
┌─────────────────────────────────────────────────────────────┐
│ [X] Merchant's Wares                          [Back]       │
├─────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────┐  │
│  │  [Weapons]  [Armor]  [Items]  [Special]             │  │
│  ├───────────────────────────────────────────────────────┤  │
│  │  ┌─────────────┐  ┌─────────────────────────────┐    │  │
│  │  │  Iron Sword │  │  Iron Sword                │    │  │
│  │  │     250g    │  │  ATK: +8                   │    │  │
│  │  └─────────────┘  │  "A standard iron sword..." │    │  │
│  │                   │  [Buy]  [Info]             │    │  │
│  │  ┌─────────────┐  └─────────────────────────────┘    │  │
│  │  │ Health Pot  │  Gold: 1,250g                     │  │
│  │  │     50g     │  [Sell]  [Sort]  [Filter]         │  │
│  │  └─────────────┘                                   │  │
│  └───────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────┘
```

#### 3. Quest Journal
```
┌─────────────────────────────────────────────────────────────┐
│ [X] Quest Journal                             [Back]       │
├─────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────┐  │
│  │  [Active]  [Completed]  [Failed]  [Tracked]         │  │
│  ├───────────────────────────────────────────────────────┤  │
│  │  ► Main Quest: The Glittering Key                   │  │
│  │    • Find the entrance to the Crystal Caverns       │  │
│  │    • Defeat the Guardian of the Shrine             │  │
│  │                                                     │  │
│  │  ► Side Quest: Lost Heirloom                        │  │
│  │    • Find the missing family locket                 │  │
│  │    • Return to Elder Miriam in Glimmerbrook         │  │
│  │                                                     │  │
│  │  [Track Quest]  [Show on Map]  [Abandon]            │  │
│  └───────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────┘
```
#### 4. Lore Archive
```
┌─────────────────────────────────────────────────────────────┐
│ [X] Lore Archive                              [Back]       │
├─────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────┐  │
│  │  [History]  [Factions]  [Bestiary]  [Locations]     │  │
│  ├───────────────────────────────────────────────────────┤  │
│  │  The Age of Twilight                                 │  │
│  │  After the Great Sundering, the world was plunged    │  │
│  │  into chaos. The ancient Glittering Empire fell,     │  │
│  │  leaving behind only fragments of their advanced     │  │
│  │  technology and magic...                            │  │
│  │                                                     │  │
│  │  [Previous]  [Next]  [Related Entries]               │  │
│  └───────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────┘
```
#### 5. Advice & Hints
```
┌─────────────────────────────────────────────────────────────┐
│ [X] Advice & Hints                             [Back]       │
├─────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────┐  │
│  │  [Current]  [General]  [Combat]  [Exploration]      │  │
│  ├───────────────────────────────────────────────────────┤  │
│  │  Current Objective:                                  │  │
│  │  "The cave entrance is hidden behind the waterfall    │  │
│  │  in the Whispering Woods. Look for the glowing       │  │
│  │  mushrooms to find the path."                        │  │
│  │                                                     │  │
│  │  Combat Tip:                                        │  │
│  │  "Goblins are weak to fire magic. Try using Firebolt  │  │
│  │  for extra damage!"                                  │  │
│  │                                                     │  │
│  │  [Show on Map]  [More Hints]                         │  │
│  └───────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────┘
```

### Surface Mode UI

#### Strategy Overview
- Top-down view of settlement
- Resource indicators at top
- Building placement grid
- Citizen management panel
- Research and production queues
- Enemy approach indicators

```
┌─────────────────────────────────────────────────────────────┐
│ Settlement: [Name]  📦 Metal: 250  🌲 Wood: 180  ⚡ Energy: 45/50 │
├─────────────────────────────────────────────────────────────┤
│ ┌─────┐                                                     │
│ │Mini-│                                                     │
│ │map  │                                                     │
│ └─────┘                                                     │
│                                                             │
│                  SETTLEMENT VIEW                            │
│                                                             │
│                                                             │
│                                                             │
│                                                             │
├─────────────────┬───────────────────────┬─────────────────┤
│ Citizens: 8/10  │ [Build] [Research]    │ Day 5 - 12:30   │
│ Workers: 6      │ [Manage] [Defend]     │ Next Attack: 4h │
└─────────────────┴───────────────────────┴─────────────────┘
```

### Tower Defense Mode

#### TD Game Screen (Debug Mode)
```
┌─────────────────────────────────────────────────────────────────────────┐
│ Wave: 5/20  💰 500  ❤️ 20/20  ⏱️ 2:45  [Pause] [Speed x2] [Debug: ON]  │
├─────────────────────────────────────────────────────────────────────────┤
│ ┌───────────────────────────────────────────────────────────────────┐   │
│ │  0,0  0,1  0,2  0,3  0,4  0,5  0,6  0,7  0,8  0,9  0,10 0,11  │   │
│ │  1,0 [░░░] [░░░] [░░░] [   ] [   ] [   ] [   ] [   ] [   ] [   ]  │   │
│ │  2,0 [░░░] [   ] [   ] [   ] [   ] [   ] [   ] [   ] [   ] [   ]  │   │
│ │  3,0 [░░░] [   ] [   ] [   ] [   ] [   ] [   ] [   ] [   ] [   ]  │   │
│ │  4,0 [░░░] [   ] [   ] [   ] [   ] [   ] [   ] [   ] [   ] [   ]  │   │
│ │  5,0 [░░░] [   ] [   ] [   ] [   ] [   ] [   ] [   ] [   ] [   ]  │   │
│ │  6,0 [░░░] [   ] [   ] [   ] [   ] [   ] [   ] [   ] [   ] [   ]  │   │
│ │  7,0 [░░░] [   ] [   ] [   ] [   ] [   ] [   ] [   ] [   ] [   ]  │   │
│ │  8,0 [░░░] [   ] [   ] [   ] [   ] [   ] [   ] [   ] [   ] [   ]  │   │
│ │  9,0 [░░░] [   ] [   ] [   ] [   ] [   ] [   ] [   ] [   ] [   ]  │   │
│ │ 10,0 [░░░] [   ] [   ] [   ] [   ] [   ] [   ] [   ] [   ] [   ]  │   │
│ │ 11,0 [░░░] [   ] [   ] [   ] [   ] [   ] [   ] [   ] [   ] [   ]  │   │
│ └───────────────────────────────────────────────────────────┘   │
│  [Start Wave]  [Upgrade Path]  [Sell Tower]  [Abilities]  [Debug Tools]  │
└─────────────────────────────────────────────────────────────────────────┘
```

#### Debug Tools Overlay
```
┌─────────────────────────────────────────────────────────────┐
│  [X] Debug Tools                               [Close]      │
├─────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────┐  │
│  │  [Toggle Grid]  [Show Paths]  [Show Build Areas]    │  │
│  │  [Add Waypoint] [Clear Waypoints]                   │  │
│  │  [Save Layout]  [Load Layout]  [Test Path]          │  │
│  │                                                     │  │
│  │  Selected Tile: (3,4)                               │  │
│  │  [Set as Path]  [Set as Build]  [Set as Blocked]    │  │
│  │  [Add Spawn]    [Add Goal]      [Clear Tile]         │  │
│  │                                                     │  │
│  │  Current Path: 0,0 → 0,1 → 0,2 → 1,2 → 2,2 → 3,2    │  │
│  └───────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────┘
```

#### Conscript Tower Menu
```
┌─────────────────────────────────────────────────────────────┐
│  [X] Conscript Tower                             [Close]    │
├─────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────┐  │
│  │  Available Conscripts: 3/5                           │  │
│  │  ├─ [Recruit] (Cost: 50G, 1 Food)                    │  │
│  │  ├─ [Train] (Cost: 100G, 1 Turn)                     │  │
│  │  └─ [Upgrade] (Cost: 200G)                           │  │
│  │                                                     │  │
│  │  Active Units:                                      │  │
│  │  ├─ ⚔️ Conscript Lv.1 (HP: 50/50)                   │  │
│  │  ├─ 🏹 Archer Lv.1 (HP: 30/30)                      │  │
│  │  └─ 🛡️ Guard Lv.2 (HP: 80/80)                      │  │
│  │                                                     │  │
│  │  [Deploy]  [Recall]  [Special Ability]  [Dismiss]   │  │
│  └───────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────┘
```

#### TD Build Menu
```
┌─────────────────────────────────────────────────────────────┐
│  [X] Build Menu                                [Close]      │
├─────────────────────────────────────────────────────────────┤
│  ┌─────────────┐  ┌─────────────────────────────────────┐  │
│  │  ⚔️ Melee   │  │  Cannon Tower                      │  │
│  │  🏹 Ranged  │  │  Cost: 150G                       │  │
│  │  🧙 Magic   │  │  Damage: Medium                    │  │
│  │  🛡️ Support  │  │  Range: 3 Tiles                   │  │
│  │  🎯 Special  │  │  Effect: Splash Damage            │  │
│  │             │  │                                   │  │
│  │  [Upgrades] │  │  [Build] [Upgrade] [Sell]         │  │
│  └─────────────┘  └─────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────┘
```

### Endless Faller Mode

#### Faller Game Screen
```
┌─────────────────────────────────────────────────────────────┐
│  Score: 12,450  Multiplier: x3  [Pause]  [Powerups: 2]      │
├─────────────────────────────────────────────────────────────┤
│  │                                                         │  │
│  │                                                         │  │
│  │                    🚀                                  │  │
│  │                                                         │  │
│  │         💎          💣                                │  │
│  │                                                         │  │
│  │    ⚡                                                   │  │
│  │             👕                                        │  │
│  │                                                         │  │
│  │                   🛡️                                   │  │
│  │                                                         │  │
│  │        [←][→]                                         │  │
│  └─────────────────────────────────────────────────────────┘  │
│  ❤️❤️❤️  [Shield Active: 5s]  [Magnet: 3s]  [2x: 8s]          │
└─────────────────────────────────────────────────────────────┘
```

#### Faller Powerup Menu
```
┌─────────────────────────────────────────────────────────────┐
│  [X] Powerup Selection                         [Close]      │
├─────────────────────────────────────────────────────────────┤
│  ┌─────────────┐  ┌─────────────────────────────────────┐  │
│  │  ⚡ Speed    │  │  Shield                          │  │
│  │  🧲 Magnet   │  │  Duration: 10 seconds             │  │
│  │  🛡️ Shield   │  │  Effect: Become invincible and    │  │
│  │  ⭐ 2x Score │  │  destroy obstacles on contact     │  │
│  │  💣 Nuke     │  │  Cooldown: 30s                   │  │
│  │             │  │  [Activate] [Upgrade]            │  │
│  └─────────────┘  └─────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────┘
```

### Tactical Strategy Mode

#### Battlefield View
```
┌─────────────────────────────────────────────────────────────┐
│  Turn: 3/99  [Alex's Turn]  💰2,450  [End Turn] [Options]  │
├─────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────┐  │
│  │  ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  │  │
│  │  ░ A ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░  │  │
│  │  ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░  │  │
│  │  ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░  │  │
│  │  ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░  │  │
│  │  ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░  │  │
│  │  ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░  │  │
│  │  ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░  │  │
│  │  ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░  │  │
│  │  ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░  │  │
│  │  ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░   ░  │  │
│  │  ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  │  │
│  └───────────────────────────────────────────────────────┘  │
│  [Move] [Attack] [Skills] [Items] [Wait] [Status] [Flee]   │
└─────────────────────────────────────────────────────────────┘
```

#### Character Action Menu
```
┌─────────────────────────────────────────────────────────────┐
│  [X] Alex - Lv.10 Knight                       [Close]      │
├─────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────┐  │
│  │  HP: ████████████ 120/120                            │  │
│  │  MP: ███████ 35/50                                   │  │
│  │  Move: 4/4      Jump: 2                               │  │
│  │                                                     │  │
│  │  [Attack]  [Abilities]  [Items]  [Wait]  [Status]    │  │
│  │                                                     │  │
│  │  [Equip]  [Optimize]  [Formation]  [Tactics]        │  │
│  └───────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────┘
```

### Universal Game Menus

#### Pause Menu (All Modes)
```
┌─────────────────────────────────────────────────────────────┐
│  [X] Game Paused                               [Close]      │
├─────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────┐  │
│  │  [Resume]                                          │  │
│  │  [Save Game]                                       │  │
│  │  [Load Game]                                       │  │
│  │  [Options]                                         │  │
│  │  [Help & Controls]                                 │  │
│  │  [Return to Main Menu]                             │  │
│  │  [Quit to Desktop]                                 │  │
│  └───────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────┘
```

#### Options Menu
```
┌─────────────────────────────────────────────────────────────┐
│  [X] Options                                   [Close]      │
├─────────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────────┐  │
│  │  [Graphics]  [Audio]  [Controls]  [Gameplay]        │  │
│  ├───────────────────────────────────────────────────┐  │  │
│  │  Resolution: 1920x1080  [▼]                      │  │  │
│  │  Fullscreen: [✓]  Borderless: [ ]  Windowed: [ ]  │  │  │
│  │  VSync: [✓]  FPS Limit: 60 [▼]                   │  │  │
│  │  Quality: High [▼]  Brightness: [───────●────]    │  │  │
│  │  UI Scale: 100% [─●────────────]                 │  │  │
│  │  [Reset to Defaults]  [Apply]  [Cancel]          │  │  │
│  └───────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────┘
```

### Inventory Screen
- Grid-based item display
- Item details on selection
- Category filters
- Sort options (type, value, name)
- Usage and equip buttons
- Storage capacity indicator

```
┌─────────────────────────────────────────────────────────────┐
│ Inventory                                           15/50   │
├─────────────┬───────────────────────────────────────────────┤
│             │                                               │
│ Categories: │ ┌────┐ ┌────┐ ┌────┐ ┌────┐ ┌────┐ ┌────┐    │
│             │ │Item│ │Item│ │Item│ │Item│ │Item│ │Item│    │
│ □ All       │ └────┘ └────┘ └────┘ └────┘ └────┘ └────┘    │
│ □ Weapons   │                                               │
│ □ Armor     │ ┌────┐ ┌────┐ ┌────┐ ┌────┐ ┌────┐ ┌────┐    │
│ □ Consumable│ │Item│ │Item│ │Item│ │Item│ │Item│ │Item│    │
│ □ Key Items │ └────┘ └────┘ └────┘ └────┘ └────┘ └────┘    │
│ □ Materials │                                               │
│             │                                               │
│ Sort By:    │ Selected Item:                                │
│ ◉ Name      │ Health Potion                                 │
│ ○ Type      │ Restores 30 HP to one character               │
│ ○ Value     │                                               │
│             │ [Use] [Drop] [Give]                           │
└─────────────┴───────────────────────────────────────────────┘
```

### Character Screen
- Character portrait and 3D model view
- Stat display with level and experience
- Equipment slots with visual feedback
- Skill tree or list
- Relic slots and progress
- Comparison tooltips for equipment

```
┌─────────────────────────────────────────────────────────────┐
│ Characters                                 [1] [2] [3] [4]  │
├─────────────┬───────────────────────────────────────────────┤
│             │                                               │
│ Alex        │ Class: Flexecutioner          Level: 5        │
│ Level 5     │ XP: 2500/3000                                 │
│             │                                               │
│ ┌─────┐     │ Stats:                       Equipment:       │
│ │     │     │ Strength:     10 (+2)        Head: Empty      │
│ │     │     │ Intelligence:  6             Body: Workout Tee│
│ │     │     │ Vitality:      8             Weapon: Dumbells │
│ └─────┘     │ Dexterity:     9             Off-hand: Empty  │
│             │ Fortune:       7             Legs: Sweatpants │
│ HP: 85/85   │ Charisma:      5             Feet: Trainers   │
│ MP: 35/35   │                                               │
│             │ Relics:                                       │
│ Skills:     │ [Glitch Stick Lv.2]  [Empty]                  │
│ [List]      │ Fury: 150/300                                 │
└─────────────┴───────────────────────────────────────────────┘
```

### Dialogue Screen
- Character portraits for speaker
- Text box with name indicator
- Choice options when applicable
- Dialogue history scrolling
- Skip and auto-advance options
- Animated expressions

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│                                                             │
│                                                             │
│                                                             │
│                      GAME WORLD VIEW                        │
│             (partially dimmed during dialogue)              │
│                                                             │
│                                                             │
│                                                             │
│                      ┌───────────────┐                      │
│ ┌──────────────┐    │ I've been      │                      │
│ │              │    │ waiting for    │                      │
│ │  CHARACTER   │    │ someone like   │                      │
│ │   PORTRAIT   │    │ you. The       │                      │
│ │              │    │ arcade needs   │                      │
│ └──────────────┘    │ your help.     │                      │
│ Glitch Guide        └───────────────┘                       │
└─────────────────────────────────────────────────────────────┘
```

### Quest Log
- List of active, completed, and failed quests
- Quest details with objectives and rewards
- Progress tracking indicators
- Sort by priority, area, or completion status
- Map markers for quest objectives

### Map Screen
- Zoomable world map showing discovered areas
- Area name and level indicators
- Player position marker
- Quest objective markers
- Fast travel options to unlocked locations
- Undiscovered areas shown as silhouettes

### Storyline Switch Screen
- Split screen showing both storylines
- Status summary of each world
- Transfer options for resources
- Countdown timer for auto-switch reminder
- Story progress indicators

```
┌─────────────────────────────────────────────────────────────┐
│ Storyline Switch                                            │
├─────────────────────────┬─────────────────────────────────┤
│                         │                                 │
│ DUNGEON STORYLINE       │ SURFACE STORYLINE              │
│                         │                                 │
│ Current Location:       │ Settlement Status:             │
│ Arcade Level 2          │ Glitch Haven                   │
│                         │                                 │
│ Party Status:           │ Resources:                     │
│ Alex (Lv.5)             │ Metal: 250  Wood: 180          │
│ Maya (Lv.4)             │ Food: 120   Energy: 45/50      │
│                         │                                 │
│ Current Quest:          │ Current Projects:              │
│ Find the Debug Terminal │ Building Workshop (80%)        │
│                         │ Researching Defense Tech       │
│                         │                                 │
│ [Switch to Dungeon]     │ [Switch to Surface]            │
│                         │                                 │
└─────────────────────────┴─────────────────────────────────┘
```

## UI Components Library

### Buttons
- Standard action button
- Toggle button
- Tab button
- Icon button
- Radio button group

### Text Elements
- Dialog text (with typewriter effect)
- Headers (various levels)
- Status text
- Tooltips
- Error messages

### Containers
- Panels (with collapsible sections)
- Scrollable lists
- Tabs container
- Card layout
- Grid layout

### Progress Indicators
- Health/Mana bars
- Experience bar
- Loading bar
- Cooldown indicator
- Countdown timer

### Navigation
- Minimap
- Breadcrumb trail
- Tab navigation
- Pagination controls
- Search field

## Animation and Transitions

### Screen Transitions
- Fade transition between major screens
- Slide transition for panels
- Pop effect for notifications
- Zoom effect for map navigation

### UI Animations
- Button hover/press effects
- Notification appearance/disappearance
- Item acquisition sparkle effect
- Damage number floating
- Experience gain particles

## UI Theme and Styling

### Color Palette

```
Primary colors:
- Neon Blue: #00ffff - Main UI elements, highlights
- Electric Purple: #9900ff - Secondary elements, magic effects
- Cyber Yellow: #ffd300 - Alerts, important notifications
- Digital Green: #00ff66 - Positive feedback, healing
- Virtual Red: #ff3366 - Negative feedback, damage, warnings

Background colors:
- Deep Digital Blue: #001133 - Main background
- Dark Matrix: #0a0a1e - Secondary background
- Shadow Black: #000011 - Modal backgrounds

Text colors:
- Data White: #ffffff - Primary text
- Info Gray: #cccccc - Secondary text
- Muted Blue: #7799cc - Disabled text
```

### Typography
- Main Font: "Pixel Code" (custom pixel font)
- UI Font: "Circuit Sans" (clean, readable sans-serif)
- Numerical Font: "Data Mono" (monospaced for stats)
- Font sizes: 12px (small), 16px (normal), 20px (large), 32px (header)

### Visual Style
- Cyberpunk aesthetic with neon accents
- Clean, minimalist UI frames
- Glowing effects for interactive elements
- Pixel art style consistent with game world
- Subtle grid patterns in backgrounds

## Responsive Design

The UI adjusts based on the device's resolution and aspect ratio:

### Desktop/Landscape Mode
- Full horizontal layout
- Side panels for detailed information
- Hover effects for all interactive elements
- Keyboard shortcuts shown in tooltips

### Mobile/Portrait Mode
- Stacked vertical layout
- Collapsible panels to save space
- Larger touch targets for buttons
- Swipe gestures for navigation
- Virtual d-pad for movement

## Accessibility Features

- Adjustable text size
- High contrast mode
- Colorblind-friendly palette options
- Screen reader compatibility
- Configurable UI scale
- Button remapping
- Auto-advance text option
- Visual cues paired with audio cues

## Loading and Progress Indicators

### Main Loading Screen
- Animated game logo
- Progress bar showing load percentage
- Cycling gameplay tips
- Background art that changes based on game progress

### Mini-Loaders
- Spinning pixel animation for short loads
- Progress circle for transitions
- Pulsing effect for interactive elements while processing

## Conclusion

This UI design document outlines the complete user interface architecture for Glitter Cloud Adventure. The UI system prioritizes clarity, consistency, and immersion while supporting the game's dual-storyline structure. The component-based approach allows for modular development and easy updates as the game evolves.

The next design document will cover the Combat System Design, detailing the mechanics of the dice-based combat system and how it integrates with character progression.

### Quest UI

#### Quest Log Screen
- Quest list with categories (Main, Side, Completed)
- Quest details panel
- Quest progress tracking
- Quest rewards preview
- Glitch's memory fragment preview
- Quest giver info (Glitch)
- Quest dialogue history
- Quest map markers

#### Quest Details Panel
- Quest title and description
- Quest objectives list
- Progress indicators
- Reward preview
- Glitch's memory fragment info
- Quest giver portrait (Glitch)
- Quest dialogue options
- Quest map integration

#### Quest Dialogue
- Glitch's dialogue options
- Quest acceptance/rejection
- Quest progress updates
- Quest completion dialogue
- Memory fragment reveals
- Quest hints and tips
- Quest rewards collection
- Quest follow-up options

#### Quest Map
- Quest location markers
- Quest area boundaries
- Quest path indicators
- Quest objective locations
- Glitch's memory fragment locations
- Quest giver location (Glitch)
- Quest completion zones
- Quest reward collection points

## Additional UI Screens

### Inventory Screen
```
┌─────────────────────────────────────────────────────────┐
│  Inventory                                              │
├─────────────────────────────────────────────────────────┤
│  [Filter: All] [Sort: Type] [Search...]                 │
├─────────────────────────────────────────────────────────┤
│  Items Grid (6x4)                                       │
│  ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐       │
│  │Item1│ │Item2│ │Item3│ │Item4│ │Item5│ │Item6│       │
│  └─────┘ └─────┘ └─────┘ └─────┘ └─────┘ └─────┘       │
│  ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐       │
│  │Item7│ │Item8│ │Item9│ │Item10││Item11││Item12│      │
│  └─────┘ └─────┘ └─────┘ └─────┘ └─────┘ └─────┘       │
│  ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐       │
│  │Item13││Item14││Item15││Item16││Item17││Item18│      │
│  └─────┘ └─────┘ └─────┘ └─────┘ └─────┘ └─────┘       │
│  ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐       │
│  │Item19││Item20││Item21││Item22││Item23││Item24│      │
│  └─────┘ └─────┘ └─────┘ └─────┘ └─────┘ └─────┘       │
├─────────────────────────────────────────────────────────┤
│  Selected Item Details                                  │
│  Name: [Item Name]                                      │
│  Type: [Item Type]                                      │
│  Description: [Item Description]                        │
│  Effects: [Item Effects]                                │
├─────────────────────────────────────────────────────────┤
│  [Use] [Equip] [Drop] [Return]                          │
└─────────────────────────────────────────────────────────┘
```

### Equipment Screen
```
┌─────────────────────────────────────────────────────────┐
│  Equipment                                              │
├─────────────────────────────────────────────────────────┤
│  Character: [Character Name]                            │
├─────────────────────────────────────────────────────────┤
│  Equipment Slots                                        │
│  Head:    [Helmet]                                      │
│  Body:    [Armor]                                       │
│  Hands:   [Gloves]                                      │
│  Feet:    [Boots]                                       │
│  Weapon:  [Sword]                                       │
│  Accessory: [Ring]                                      │
├─────────────────────────────────────────────────────────┤
│  Stats                                                  │
│  ATK: +15  DEF: +10  SPD: +5                           │
│  MAT: +8   MDF: +12  LUK: +3                           │
├─────────────────────────────────────────────────────────┤
│  [Optimize] [Clear All] [Return]                        │
└─────────────────────────────────────────────────────────┘
```

### Save/Load Screen
```
┌─────────────────────────────────────────────────────────┐
│  Save/Load Game                                         │
├─────────────────────────────────────────────────────────┤
│  Save Slots                                             │
│  ┌───────────────────────────────────────────────────┐  │
│  │ Slot 1: Level 15 - Glitchport Docks              │  │
│  │ Party: [Char1] [Char2] [Char3] [Char4]           │  │
│  │ Time: 5:23:45  Date: 2024-03-15                  │  │
│  └───────────────────────────────────────────────────┘  │
│  ┌───────────────────────────────────────────────────┐  │
│  │ Slot 2: Level 12 - Digital Dawn                   │  │
│  │ Party: [Char1] [Char3] [Char5] [Char6]           │  │
│  │ Time: 3:45:12  Date: 2024-03-14                  │  │
│  └───────────────────────────────────────────────────┘  │
│  ┌───────────────────────────────────────────────────┐  │
│  │ Slot 3: [Empty]                                  │  │
│  └───────────────────────────────────────────────────┘  │
├─────────────────────────────────────────────────────────┤
│  [Save] [Load] [Delete] [Return]                        │
└─────────────────────────────────────────────────────────┘
```

### Settings Screen
```
┌─────────────────────────────────────────────────────────┐
│  Settings                                               │
├─────────────────────────────────────────────────────────┤
│  Display                                                │
│  [ ] Fullscreen                                         │
│  Resolution: [1920x1080 ▼]                             │
│  Brightness: [=====o====]                              │
│  [ ] V-Sync                                            │
├─────────────────────────────────────────────────────────┤
│  Audio                                                  │
│  Master Volume: [=====o====]                           │
│  Music Volume: [=====o====]                            │
│  SFX Volume: [=====o====]                              │
│  [ ] Mute All                                          │
├─────────────────────────────────────────────────────────┤
│  Controls                                               │
│  [Customize Controls...]                               │
│  [Reset to Default]                                    │
├─────────────────────────────────────────────────────────┤
│  Accessibility                                          │
│  [ ] Color Blind Mode                                  │
│  Text Size: [Small] [Medium] [Large]                   │
│  [ ] Screen Shake                                      │
├─────────────────────────────────────────────────────────┤
│  [Save] [Reset] [Return]                                │
└─────────────────────────────────────────────────────────┘
```

### Quest Log Screen
```
┌─────────────────────────────────────────────────────────┐
│  Quest Log                                              │
├─────────────────────────────────────────────────────────┤
│  [Active] [Completed] [Failed]                          │
├─────────────────────────────────────────────────────────┤
│  Active Quests                                          │
│  ┌───────────────────────────────────────────────────┐  │
│  │ The Lost Codex                                   │  │
│  │ Progress: 2/4 Tasks                              │  │
│  │ • [✓] Speak to the Archivist                     │  │
│  │ • [✓] Locate the Ancient Terminal                │  │
│  │ • [ ] Decrypt the data fragments (0/3)           │  │
│  │ • [ ] Return to the Archivist                    │  │
│  └───────────────────────────────────────────────────┘  │
│  ┌───────────────────────────────────────────────────┐  │
│  │ Digital Corruption                               │  │
│  │ Progress: 1/3 Tasks                              │  │
│  │ • [✓] Investigate the anomaly                    │  │
│  │ • [ ] Defeat the corrupted entities (0/5)        │  │
│  │ • [ ] Seal the corruption source                 │  │
│  └───────────────────────────────────────────────────┘  │
├─────────────────────────────────────────────────────────┤
│  [Track Quest] [Show on Map] [Return]                   │
└─────────────────────────────────────────────────────────┘
```

### Map Screen
```
┌─────────────────────────────────────────────────────────┐
│  World Map                                              │
├─────────────────────────────────────────────────────────┤
│  [Zoom In] [Zoom Out] [Reset View]                      │
├─────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────┐  │
│  │                                                   │  │
│  │  [Glitchport]    [Digital Dawn]    [Data Stream]  │  │
│  │                                                   │  │
│  │  [Great Firewall] [Quantum Realm]  [Dreamscape]   │  │
│  │                                                   │  │
│  │  [Corrupted Core] [Cyber Citadel]  [Digital Void] │  │
│  │                                                   │  │
│  └───────────────────────────────────────────────────┘  │
├─────────────────────────────────────────────────────────┤
│  Current Location: [Digital Dawn]                       │
│  [Fast Travel] [Return]                                 │
└─────────────────────────────────────────────────────────┘
```

### Shop Screen
```
┌─────────────────────────────────────────────────────────┐
│  Shop - [Shop Name]                                     │
├─────────────────────────────────────────────────────────┤
│  [Buy] [Sell] [Repair] [Upgrade]                        │
├─────────────────────────────────────────────────────────┤
│  Available Items                                        │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐        │
│  │ Item 1      │ │ Item 2      │ │ Item 3      │        │
│  │ Price: 100g │ │ Price: 150g │ │ Price: 200g │        │
│  └─────────────┘ └─────────────┘ └─────────────┘        │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐        │
│  │ Item 4      │ │ Item 5      │ │ Item 6      │        │
│  │ Price: 250g │ │ Price: 300g │ │ Price: 350g │        │
│  └─────────────┘ └─────────────┘ └─────────────┘        │
├─────────────────────────────────────────────────────────┤
│  Your Gold: 1000g                                       │
│  [Buy Selected] [Sell Selected] [Return]                │
└─────────────────────────────────────────────────────────┘
```

### Crafting Screen
```
┌─────────────────────────────────────────────────────────┐
│  Crafting                                               │
├─────────────────────────────────────────────────────────┤
│  [Weapons] [Armor] [Items] [Consumables]                │
├─────────────────────────────────────────────────────────┤
│  Available Recipes                                      │
│  ┌───────────────────────────────────────────────────┐  │
│  │ Digital Sword                                    │  │
│  │ Materials:                                       │  │
│  │ • Digital Fragment x3                           │  │
│  │ • Mystic Essence x1                             │  │
│  │ [Craft]                                         │  │
│  └───────────────────────────────────────────────────┘  │
│  ┌───────────────────────────────────────────────────┐  │
│  │ Quantum Armor                                    │  │
│  │ Materials:                                       │  │
│  │ • Quantum Shard x2                              │  │
│  │ • Digital Fragment x2                           │  │
│  │ [Craft]                                         │  │
│  └───────────────────────────────────────────────────┘  │
├─────────────────────────────────────────────────────────┤
│  [Craft Selected] [Return]                              │
└─────────────────────────────────────────────────────────┘
```

## Additional Essential Screens

### Character Creation Screen
```
┌─────────────────────────────────────────────────────────┐
│  Create Character                                        │
├─────────────────────────────────────────────────────────┤
│  Name: [_________________]                               │
├─────────────────────────────────────────────────────────┤
│  Class Selection                                         │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐        │
│  │ [Hacker]    │ │ [Mystic]    │ │ [Guardian]  │        │
│  │ Digital     │ │ Quantum     │ │ Cyber       │        │
│  │ Expert      │ │ Manipulator │ │ Defender    │        │
│  └─────────────┘ └─────────────┘ └─────────────┘        │
├─────────────────────────────────────────────────────────┤
│  Starting Stats                                          │
│  HP: 100   MP: 50   ATK: 10   DEF: 8                    │
│  SPD: 12   MAT: 15   MDF: 10   LUK: 10                  │
├─────────────────────────────────────────────────────────┤
│  [Randomize Stats] [Confirm] [Back]                      │
└─────────────────────────────────────────────────────────┘
```

### Party Management Screen
```
┌─────────────────────────────────────────────────────────┐
│  Party Management                                        │
├─────────────────────────────────────────────────────────┤
│  Active Party                                            │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐        │
│  │ [Char1]     │ │ [Char2]     │ │ [Char3]     │        │
│  │ Lv.15       │ │ Lv.14       │ │ Lv.13       │        │
│  │ Hacker      │ │ Mystic      │ │ Guardian    │        │
│  └─────────────┘ └─────────────┘ └─────────────┘        │
├─────────────────────────────────────────────────────────┤
│  Available Characters                                    │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐        │
│  │ [Char4]     │ │ [Char5]     │ │ [Char6]     │        │
│  │ Lv.12       │ │ Lv.11       │ │ Lv.10       │        │
│  │ Hacker      │ │ Mystic      │ │ Guardian    │        │
│  └─────────────┘ └─────────────┘ └─────────────┘        │
├─────────────────────────────────────────────────────────┤
│  [Swap] [Formation] [Return]                             │
└─────────────────────────────────────────────────────────┘
```

### Skill Tree Screen
```
┌─────────────────────────────────────────────────────────┐
│  Skill Tree - [Character Name]                           │
├─────────────────────────────────────────────────────────┤
│  [Hacker Skills] [Mystic Skills] [Guardian Skills]       │
├─────────────────────────────────────────────────────────┤
│  ┌─────┐     ┌─────┐     ┌─────┐                        │
│  │Skill│ --> │Skill│ --> │Skill│                        │
│  │ 1   │     │ 2   │     │ 3   │                        │
│  └─────┘     └─────┘     └─────┘                        │
│      │           │           │                          │
│      ▼           ▼           ▼                          │
│  ┌─────┐     ┌─────┐     ┌─────┐                        │
│  │Skill│ --> │Skill│ --> │Skill│                        │
│  │ 4   │     │ 5   │     │ 6   │                        │
│  └─────┘     └─────┘     └─────┘                        │
├─────────────────────────────────────────────────────────┤
│  Skill Points: 5                                         │
│  [Learn] [Reset] [Return]                                │
└─────────────────────────────────────────────────────────┘
```

### Achievement Screen
```
┌─────────────────────────────────────────────────────────┐
│  Achievements                                            │
├─────────────────────────────────────────────────────────┤
│  [All] [Combat] [Exploration] [Story]                    │
├─────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────┐  │
│  │ Digital Master                                   │  │
│  │ Defeat 100 digital enemies                       │  │
│  │ Progress: 75/100                                │  │
│  │ [Reward: 1000g]                                 │  │
│  └───────────────────────────────────────────────────┘  │
│  ┌───────────────────────────────────────────────────┐  │
│  │ Quantum Explorer                                 │  │
│  │ Visit all areas in the Quantum Realm             │  │
│  │ Progress: 3/5                                   │  │
│  │ [Reward: Quantum Crystal]                       │  │
│  └───────────────────────────────────────────────────┘  │
├─────────────────────────────────────────────────────────┤
│  Total Achievements: 12/50                              │
│  [Return]                                              │
└─────────────────────────────────────────────────────────┘
```

### Tutorial Screen
```
┌─────────────────────────────────────────────────────────┐
│  Tutorial                                               │
├─────────────────────────────────────────────────────────┤
│  [Basic Controls] [Combat] [Skills] [Items]             │
├─────────────────────────────────────────────────────────┤
│  Movement                                               │
│  • Use WASD or Arrow Keys to move                      │
│  • Hold Shift to run                                   │
│  • Press Space to interact                             │
│                                                        │
│  Combat                                                │
│  • Press Enter to initiate combat                      │
│  • Use number keys 1-4 to select skills                │
│  • Press Tab to switch targets                         │
├─────────────────────────────────────────────────────────┤
│  [Previous] [Next] [Skip] [Return]                      │
└─────────────────────────────────────────────────────────┘
```

### Pause Menu
```
┌─────────────────────────────────────────────────────────┐
│  Pause Menu                                             │
├─────────────────────────────────────────────────────────┤
│  [Resume Game]                                          │
│  [Save Game]                                            │
│  [Load Game]                                            │
│  [Settings]                                             │
│  [Tutorial]                                             │
│  [Achievements]                                         │
│  [Return to Main Menu]                                  │
└─────────────────────────────────────────────────────────┘
```

### Game Over Screen
```
┌─────────────────────────────────────────────────────────┐
│  Game Over                                              │
├─────────────────────────────────────────────────────────┤
│  Your party has been defeated...                        │
│                                                        │
│  Time Played: 5:23:45                                  │
│  Level Reached: 15                                     │
│  Enemies Defeated: 234                                 │
│  Items Collected: 156                                  │
├─────────────────────────────────────────────────────────┤
│  [Load Last Save]                                       │
│  [Return to Main Menu]                                  │
└─────────────────────────────────────────────────────────┘
```

### Notification System
```
┌─────────────────────────────────────────────────────────┐
│  Notifications                                          │
├─────────────────────────────────────────────────────────┤
│  • New Quest Available: "Digital Corruption"            │
│  • Level Up! Character is now level 16                  │
│  • Achievement Unlocked: "Digital Master"               │
│  • New Area Discovered: "Quantum Realm"                 │
└─────────────────────────────────────────────────────────┘
```

## HUD Components

### Main HUD Layout
```
┌─────────────────────────────────────────────────────────┐
│  [Menu] [Map] [Quest] [Bestiary] [Inventory]            │
├─────────────────────────────────────────────────────────┤
│  ┌─────┐                                                │
│  │     │  Party Status                                  │
│  │     │  [Char1] HP: ████████░░  MP: █████░░░         │
│  │     │  [Char2] HP: ███████░░░  MP: ████░░░░         │
│  │     │  [Char3] HP: ████████░░  MP: █████░░░         │
│  │     │                                                │
│  └─────┘  [Status Effects]                              │
│           [Poison] [Haste] [Protect]                    │
├─────────────────────────────────────────────────────────┤
│  [Quick Items] [Quick Skills] [Quick Menu]              │
└─────────────────────────────────────────────────────────┘
```

### Mini-map Component
```
┌─────────────────────────────────────────────────────────┐
│  Mini-map                                                │
├─────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────┐  │
│  │                                                   │  │
│  │  [P] [E] [N] [S] [B] [Q] [I] [M]                 │  │
│  │                                                   │  │
│  │  [P] = Player                                    │  │
│  │  [E] = Enemy                                     │  │
│  │  [N] = NPC                                       │  │
│  │  [S] = Shop                                      │  │
│  │  [B] = Boss                                      │  │
│  │  [Q] = Quest Objective                           │  │
│  │  [I] = Item                                      │  │
│  │  [M] = Mission Point                             │  │
│  └───────────────────────────────────────────────────┘  │
├─────────────────────────────────────────────────────────┤
│  [Zoom In] [Zoom Out] [Toggle Full Map]                │
└─────────────────────────────────────────────────────────┘
```

### Quick Access Menu
```
┌─────────────────────────────────────────────────────────┐
│  Quick Access                                           │
├─────────────────────────────────────────────────────────┤
│  [1] Health Potion                                     │
│  [2] Mana Potion                                       │
│  [3] Digital Shield                                    │
│  [4] Quantum Bomb                                      │
│  [5] Cyber Grenade                                     │
│  [6] Mystic Crystal                                    │
│  [7] Repair Kit                                        │
│  [8] Emergency Exit                                    │
├─────────────────────────────────────────────────────────┤
│  [Customize] [Return]                                   │
└─────────────────────────────────────────────────────────┘
```

### Status Effects Display
```
┌─────────────────────────────────────────────────────────┐
│  Status Effects                                         │
├─────────────────────────────────────────────────────────┤
│  Active Effects                                         │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐        │
│  │ [Haste] │ │[Protect]│ │[Regen]  │ │[Poison] │        │
│  │ 2 turns │ │ 3 turns │ │ 4 turns │ │ 3 turns │        │
│  └─────────┘ └─────────┘ └─────────┘ └─────────┘        │
├─────────────────────────────────────────────────────────┤
│  [View Details] [Return]                                 │
└─────────────────────────────────────────────────────────┘
```

### Quest Tracker
```
┌─────────────────────────────────────────────────────────┐
│  Active Quest                                           │
├─────────────────────────────────────────────────────────┤
│  The Lost Codex                                         │
│  • [✓] Speak to the Archivist                          │
│  • [✓] Locate the Ancient Terminal                     │
│  • [ ] Decrypt the data fragments (0/3)                │
│  • [ ] Return to the Archivist                         │
├─────────────────────────────────────────────────────────┤
│  [Show on Map] [View All Quests]                        │
└─────────────────────────────────────────────────────────┘
```

## Combat UI Components

### Battle Screen
```
┌─────────────────────────────────────────────────────────┐
│  Battle                                                 │
├─────────────────────────────────────────────────────────┤
│  Turn Order: [E1] [P1] [P2] [E2] [P3] [E3]              │
├─────────────────────────────────────────────────────────┤
│  Enemies                                                │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐                    │
│  │ [E1]    │ │ [E2]    │ │ [E3]    │                    │
│  │ HP: 80% │ │ HP: 65% │ │ HP: 90% │                    │
│  │ [Poison]│ │ [Slow]  │ │ [None]  │                    │
│  └─────────┘ └─────────┘ └─────────┘                    │
├─────────────────────────────────────────────────────────┤
│  Party                                                  │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐                    │
│  │ [P1]    │ │ [P2]    │ │ [P3]    │                    │
│  │ HP: 75% │ │ HP: 90% │ │ HP: 85% │                    │
│  │ MP: 60% │ │ MP: 80% │ │ MP: 70% │                    │
│  └─────────┘ └─────────┘ └─────────┘                    │
├─────────────────────────────────────────────────────────┤
│  Action Menu                                            │
│  [Attack] [Skills] [Items] [Defend] [Escape]            │
└─────────────────────────────────────────────────────────┘
```

### Action Points Display
```
┌─────────────────────────────────────────────────────────┐
│  Action Points                                          │
├─────────────────────────────────────────────────────────┤
│  Current AP: 3/5                                         │
│  ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐                │
│  │  ●  │ │  ●  │ │  ●  │ │  ○  │ │  ○  │                │
│  └─────┘ └─────┘ └─────┘ └─────┘ └─────┘                │
├─────────────────────────────────────────────────────────┤
│  Next AP in: 2 turns                                     │
└─────────────────────────────────────────────────────────┘
```

### Combat Log
```
┌─────────────────────────────────────────────────────────┐
│  Combat Log                                             │
├─────────────────────────────────────────────────────────┤
│  • E1 used Digital Slash on P1 (-25 HP)                 │
│  • P1 used Quantum Burst on all enemies                 │
│  • E2 is poisoned (-10 HP)                              │
│  • P2 used Cyber Shield on P1                           │
│  • E3 used System Crash on all party members            │
├─────────────────────────────────────────────────────────┤
│  [Clear] [Save Log] [Return]                             │
└─────────────────────────────────────────────────────────┘
```

### Combat Sub-Menus

#### Skills Sub-Menu (Page 1)
```
┌─────────────────────────────────────────────────────────┐
│  Skills - Page 1/3                                       │
├─────────────────────────────────────────────────────────┤
│  [1] Digital Slash    MP: 10  [Target: Single]          │
│  [2] Quantum Burst    MP: 25  [Target: All]             │
│  [3] Cyber Shield     MP: 15  [Target: Self]            │
│  [4] Mystic Wave      MP: 20  [Target: Row]             │
│  [5] Data Drain       MP: 30  [Target: Single]          │
│  [6] System Crash     MP: 40  [Target: All]             │
├─────────────────────────────────────────────────────────┤
│  [Page 1] [Page 2] [Page 3]                             │
│  [Back] [Auto] [Return]                                  │
└─────────────────────────────────────────────────────────┘
```

#### Skills Sub-Menu (Page 2)
```
┌─────────────────────────────────────────────────────────┐
│  Skills - Page 2/3                                       │
├─────────────────────────────────────────────────────────┤
│  [1] Binary Strike    MP: 15  [Target: Single]          │
│  [2] Code Breaker     MP: 35  [Target: All]             │
│  [3] Firewall        MP: 20  [Target: Self]            │
│  [4] Virus Scan      MP: 25  [Target: Row]             │
│  [5] Data Recovery   MP: 30  [Target: Single]          │
│  [6] System Restore  MP: 45  [Target: All]             │
├─────────────────────────────────────────────────────────┤
│  [Page 1] [Page 2] [Page 3]                             │
│  [Back] [Auto] [Return]                                  │
└─────────────────────────────────────────────────────────┘
```

#### Skills Sub-Menu (Page 3)
```
┌─────────────────────────────────────────────────────────┐
│  Skills - Page 3/3                                       │
├─────────────────────────────────────────────────────────┤
│  [1] Quantum Lock    MP: 40  [Target: Single]          │
│  [2] Digital Storm   MP: 50  [Target: All]             │
│  [3] Cyber Armor     MP: 30  [Target: Self]            │
│  [4] Mystic Pulse    MP: 35  [Target: Row]             │
│  [5] Data Overload   MP: 45  [Target: Single]          │
│  [6] System Override MP: 60  [Target: All]             │
├─────────────────────────────────────────────────────────┤
│  [Page 1] [Page 2] [Page 3]                             │
│  [Back] [Auto] [Return]                                  │
└─────────────────────────────────────────────────────────┘
```

#### Items Sub-Menu (Categorized)
```
┌─────────────────────────────────────────────────────────┐
│  Items                                                   │
├─────────────────────────────────────────────────────────┤
│  [Consumables] [Equipment] [Key Items] [Materials]       │
├─────────────────────────────────────────────────────────┤
│  Consumables (Page 1/2)                                  │
│  [1] Health Potion    x5                                 │
│  [2] Mana Potion      x3                                 │
│  [3] Digital Shield   x2                                 │
│  [4] Quantum Bomb     x1                                 │
│  [5] Cyber Grenade    x4                                 │
│  [6] Mystic Crystal   x2                                 │
├─────────────────────────────────────────────────────────┤
│  [Next Page] [Back] [Return]                             │
└─────────────────────────────────────────────────────────┘
```

#### Items Sub-Menu (Equipment)
```
┌─────────────────────────────────────────────────────────┐
│  Equipment                                               │
├─────────────────────────────────────────────────────────┤
│  [Weapons] [Armor] [Accessories] [Return]                │
├─────────────────────────────────────────────────────────┤
│  Weapons (Page 1/2)                                      │
│  [1] Digital Blade    ATK+25                            │
│  [2] Quantum Sword    ATK+30                            │
│  [3] Cyber Dagger     ATK+20                            │
│  [4] Mystic Staff     MAT+35                            │
│  [5] Data Blade       ATK+28                            │
│  [6] System Saber     ATK+32                            │
├─────────────────────────────────────────────────────────┤
│  [Next Page] [Back] [Return]                             │
└─────────────────────────────────────────────────────────┘
```

#### Target Selection Sub-Menu
```
┌─────────────────────────────────────────────────────────┐
│  Select Target                                           │
├─────────────────────────────────────────────────────────┤
│  [Single Target] [All Enemies] [All Allies] [Self]       │
├─────────────────────────────────────────────────────────┤
│  Single Target                                           │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐                    │
│  │ [E1]    │ │ [E2]    │ │ [E3]    │                    │
│  │ HP: 80% │ │ HP: 65% │ │ HP: 90% │                    │
│  │ [Poison]│ │ [Slow]  │ │ [None]  │                    │
│  └─────────┘ └─────────┘ └─────────┘                    │
├─────────────────────────────────────────────────────────┤
│  [Back] [Auto] [Return]                                  │
└─────────────────────────────────────────────────────────┘
```

#### Status Effect Details Sub-Menu
```
┌─────────────────────────────────────────────────────────┐
│  Status Effect Details                                   │
├─────────────────────────────────────────────────────────┤
│  [Poison]                                               │
│  • Duration: 3 turns                                    │
│  • Effect: -10 HP per turn                              │
│  • Resistance: 25%                                      │
│  • Can be cured by: Antidote, Cleanse                   │
│                                                        │
│  [Haste]                                                │
│  • Duration: 2 turns                                    │
│  • Effect: +50% Speed                                   │
│  • Resistance: 15%                                      │
│  • Can be removed by: Slow, Dispel                      │
├─────────────────────────────────────────────────────────┤
│  [Back] [Return]                                         │
└─────────────────────────────────────────────────────────┘
```

### Quest System
```
┌─────────────────────────────────────────────────────────┐
│  Quest System                                            │
├─────────────────────────────────────────────────────────┤
│  [Active] [Completed] [Failed]                           │
├─────────────────────────────────────────────────────────┤
│  Active Quests                                           │
│  ┌───────────────────────────────────────────────────┐  │
│  │ The Lost Codex                                   │  │
│  │ Progress: 2/4 Tasks                              │  │
│  │ • [✓] Speak to the Archivist                     │  │
│  │ • [✓] Locate the Ancient Terminal                │  │
│  │ • [ ] Decrypt the data fragments (0/3)           │  │
│  │ • [ ] Return to the Archivist                    │  │
│  └───────────────────────────────────────────────────┘  │
│  ┌───────────────────────────────────────────────────┐  │
│  │ Digital Corruption                               │  │
│  │ Progress: 1/3 Tasks                              │  │
│  │ • [✓] Investigate the anomaly                    │  │
│  │ • [ ] Defeat the corrupted entities (0/5)        │  │
│  │ • [ ] Seal the corruption source                 │  │
│  └───────────────────────────────────────────────────┘  │
├─────────────────────────────────────────────────────────┤
│  [Track Quest] [Show on Map] [Return]                   │
└─────────────────────────────────────────────────────────┘
```

### Quest Tracker (HUD)
```
┌─────────────────────────────────────────────────────────┐
│  Active Quest                                           │
├─────────────────────────────────────────────────────────┤
│  The Lost Codex                                         │
│  • [✓] Speak to the Archivist                          │
│  • [✓] Locate the Ancient Terminal                     │
│  • [ ] Decrypt the data fragments (0/3)                │
│  • [ ] Return to the Archivist                         │
├─────────────────────────────────────────────────────────┤
│  [Show on Map] [View All Quests]                        │
└─────────────────────────────────────────────────────────┘
```

### Map System
```
┌─────────────────────────────────────────────────────────┐
│  World Map                                              │
├─────────────────────────────────────────────────────────┤
│  [Zoom In] [Zoom Out] [Reset View]                      │
├─────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────┐  │
│  │                                                   │  │
│  │  [Glitchport]    [Digital Dawn]    [Data Stream]  │  │
│  │                                                   │  │
│  │  [Great Firewall] [Quantum Realm]  [Dreamscape]   │  │
│  │                                                   │  │
│  │  [Corrupted Core] [Cyber Citadel]  [Digital Void] │  │
│  │                                                   │  │
│  └───────────────────────────────────────────────────┘  │
├─────────────────────────────────────────────────────────┤
│  Current Location: [Digital Dawn]                       │
│  [Fast Travel] [Return]                                 │
└─────────────────────────────────────────────────────────┘
```

### Mini-map (HUD)
```
┌─────────────────────────────────────────────────────────┐
│  Mini-map                                                │
├─────────────────────────────────────────────────────────┤
│  ┌───────────────────────────────────────────────────┐  │
│  │                                                   │  │
│  │  [P] [E] [N] [S] [B] [Q] [I] [M]                 │  │
│  │                                                   │  │
│  │  [P] = Player                                    │  │
│  │  [E] = Enemy                                     │  │
│  │  [N] = NPC                                       │  │
│  │  [S] = Shop                                      │  │
│  │  [B] = Boss                                      │  │
│  │  [Q] = Quest Objective                           │  │
│  │  [I] = Item                                      │  │
│  │  [M] = Mission Point                             │  │
│  └───────────────────────────────────────────────────┘  │
├─────────────────────────────────────────────────────────┤
│  [Zoom In] [Zoom Out] [Toggle Full Map]                │
└─────────────────────────────────────────────────────────┘
```
