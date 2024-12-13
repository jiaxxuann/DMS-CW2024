# **DMS-CW2024 - Sky Battle**

## 1. About This Repository
- Repository Owner : Siow Jia Xuan (20618655)
- Github link : https://github.com/jiaxxuann/DMS-CW2024

## 2. Compilation Instruction
### 2.1 Prerequisites
### 2.2 Cloning the Project
### 2.3 Importing Project in IntelliJ IDEA

  **First-Time Users: **
  **Existing Users: **

### 2.4 Resolving Maven Dependencies
### 2.5 Setting up JDK

## 3. Implemented and Working Properly
### 3.1 Separate Screens
### 3.2 
- list features successfully implemented, functioning as expected, brief explanation

## 4. Implemented but Not Working Properly
### 4.1 Load Game Mechanism
- identify features implemented but not working correctly. explain issue encountered, if possible steps took to address them

## 5. Features Not Implemented
- list features unable implement, explanation they were left out(no time)

## 6. New Java Classes
### 6.1 Refactoring Classes
#### 6.1.1 Observer, Observable, Observable Helper
- to replace deprecated Observable and Observer APIs

#### 6.1.2 LevelBehaviour Interface
- to move all abstract methods from the `LevelParent` class to the new `LevelBehaviour` interface
- updated `LevelParent` to implement the `LevelBehaviour` interface
- improved code organization by separating responsibilities between interface and class

#### 6.1.3 CollisionHandler
- to manage game conditions such as collisions, projectile interactions, and enemy behavior
- to move condition-related logic from `LevelParent` to `ConditionHandler` to improve code readability and maintainability
- enhanced separation of concerns by isolating condition checks and interactions into a dedicated handler class

#### 6.1.4 ActorManager
- to handle actor management tasks, such as adding, removing, and updating actors
- moved actor-related logic from `LevelParent` to `ActorManager` to improve code modularity and maintainability
- enhanced code readability by isolating actor management functionality into a dedicated class

#### 6.1.5 HeartDisplay
- renamed `removeHearts` method in `LevelParentView` to `updateHeartCount` to better reflect its purpose
- moved the heart removal logic to `HeartDisplay`, delegating the responsibility to the `HeartDisplay` class
- `HeartDisplay` now handles heart removal with a new `removeHearts` method, improving code organization and separation of concerns
- simplified `LevelParentView` by offloading heart display management to `HeartDisplay`

#### 6.1.6 LevelParentController, LevelParentView
- split the `LevelParent` class into three components: `LevelParent` (Model), `LevelParentController` (Controller), and `LevelParentView` (View)
- moved game logic and state management to `LevelParent` (Model)
- handled user input and game flow in `LevelParentController` (Controller)
- updated UI-related functionality in `LevelParentView` (View)
- improved code organization by adhering to the MVC pattern for better separation of concerns

#### 6.1.7 Hitbox
- created a `Hitbox` class to encapsulate all hitbox-related logic, improving code modularity and adhering to the single responsibility principle
- updated `ActiveActorDestructible` to use the `Hitbox` class for managing hitbox creation, position updates, and retrieval
- simplified hitbox initialization and management in `ActiveActorDestructible` for better readability and maintainability
- encapsulated hitbox visualization logic within the `Hitbox` class, preparing for potential reuse in other classes

#### 6.1.8 ImageLoader
- introduced a new `ImageLoader` class to handle image loading functionality
- replaced individual image loading code in relevant classes with calls to the `ImageLoader.loadImage()` method

#### 6.1.9 ActorBehaviour
- extracted updatePosition() and updateActor() from ActiveActor and ActiveActorDestructible into new interface
- refactored ActiveActor and ActiveActorDestructible to implement the interface

#### 6.1.10 ProjectileFiring interface
- moved fireProjectile() from FighterPlane into ProjectileFiring interface
- refactored FighterPlane so that it implements the interface
  
#### 6.1.11 ShieldManager
- created `ShieldManager` class to handle shield's state, activation, deactivation, and visibility
- `ShieldManager` improves separation of concerns and simplify the Boss and ShieldImage class
  
#### 6.1.12 ProjectileFactory
- added a ProjectileFactory class to centralize the creation of User, Enemy, and Boss projectiles
- removed redundant constructor logic from individual projectile classes
- refactored Projectile class to handle shared functionality across all projectiles
- removed all individual projectile classes
- simplified client code by introducing a factory-based approach for creating projectiles

#### 6.1.13 PlaneFactory
#### 6.1.14


### 6.2 New Levels
#### 6.2.1 LevelThree, LevelFour
- added two new levels with new assets and backgrounds as additions to make the game more enjoyable

#### 6.2.1 LevelFourView
- consist of the same logic as LevelTwoView as LevelFour contains the Boss

### 6.3 Screens
#### 6.3.1 MainMenu
- set MainMenu as the initial screen when the game starts
- the MainMenu screen contains 'Start Game', 'Settings' and 'Quit' buttons
  
#### 6.3.1 LoseScreen
- integrated LoseScreen with game logic to display after losing a level
- the LoseScreen contains 'Play Again' and 'Main Menu' buttons

#### 6.3.1 WinScreen
- integrated LoseScreen with game logic to display after losing a level
- the LoseScreen contains 'Restart' and 'Main Menu' buttons

- enumerate new java classes introduced, brief description of new class's purpose and location in code
- new levels, gameplay enhancement, unique features







## 7. Modified Java Classes
### 6.1 Refactoring Classes
#### 6.1.1 LevelView, LevelViewTwo
- renamed `LevelView` to `LevelParentView`
- renamed `LevelViewLevelTwo` to `LevelTwoView`

#### 6.1.2
#### 6.1.3

- plane classes
- level classes
- controller classes
- list modified classes from provided code, describe changes(fix bug, packages, code, name, single responsibilities, design pattern) and why isit necessary

## 8. Unexpected Problems
### 8.1 
fix: delete two lines of code to resolve InvalidModuleDescriptorException
- deleted problematic `opens` directives in module descriptor to fix module validation error
- unexpected challenges during asgm, how attempted to resolve
