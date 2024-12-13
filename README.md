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
- to move all abstract methods from the LevelParent class to the new LevelBehaviour interface
- updated LevelParent to implement the LevelBehaviour interface
- improved code organization by separating responsibilities between interface and class

#### 6.1.3 CollisionHandler
- to manage game conditions such as collisions, projectile interactions, and enemy behavior
- to move condition-related logic from LevelParent to ConditionHandler to improve code readability and maintainability
- enhanced separation of concerns by isolating condition checks and interactions into a dedicated handler class

#### 6.1.4 ActorManager
- to handle actor management tasks, such as adding, removing, and updating actors
- moved actor-related logic from LevelParent to ActorManager to improve code modularity and maintainability
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

### 6.2 New Levels
- 

### 6.3 Screens
- 


- enumerate new java classes introduced, brief description of new class's purpose and location in code
- new levels, gameplay enhancement, unique features







## 7. Modified Java Classes
### 6.1 Refactoring Classes
#### 6.1.1 

- plane classes
- level classes
- controller classes
- list modified classes from provided code, describe changes(fix bug, packages, code, name, single responsibilities, design pattern) and why isit necessary

## 8. Unexpected Problems
### 8.1 
- unexpected challenges during asgm, how attempted to resolve
