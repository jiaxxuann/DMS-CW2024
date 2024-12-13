# **DMS-CW2024 - Sky Battle**

## 1. About This Repository
- Repository Owner : Siow Jia Xuan (20618655)
- Github link : https://github.com/jiaxxuann/DMS-CW2024

## 2. Compilation Instruction
### 2.1 Prerequisites
To successfully compile and run this project, ensure you have the following prerequisites installed on your system:
- Java Development Kit (JDK): Version 11 or later.
- Maven: For managing dependencies and building the project.
- IntelliJ IDEA: Recommended IDE for Java development.
- Git: For cloning the project repository.

### 2.2 Cloning the Project
**From Git: ** Use git clone [repository URL] to clone the repository
**From ZIP file: **
1. Download: Save zip file to your computer
2. Extract: Unzip to a suitable location

To get the project files onto your local machine, follow these steps:
1. Open a terminal or command prompt.

2. Execute the following command to clone the repository:
git clone <repository-url>

3. Navigate to the project directory:
cd <project-directory>

### 2.3 Importing Project in IntelliJ IDEA

  **First-Time Users: **
1. Open IntelliJ IDEA.

2. Select File > New > Project from Existing Sources.

3. Browse to the cloned project directory and click OK.

4. Select the option Import project from external model and choose Maven.

5. Click Next and configure the project SDK (refer to Section 2.5 for setting up JDK).

6. Click Finish to complete the import process.

  **Existing Users: **
1. Open IntelliJ IDEA.

2. Select File > Open.

3. Browse to the project directory and select it.

4. IntelliJ will automatically detect the Maven project structure and import it.

### 2.4 Resolving Maven Dependencies
1. After importing the project, IntelliJ IDEA will automatically attempt to resolve Maven dependencies.

2. If dependencies are not resolved automatically:

 - Open the Maven Tool Window (on the right sidebar).

 - Click on the Reload All Maven Projects button (circular arrows icon).

3. Ensure your internet connection is active to download the required dependencies.

### 2.5 Setting up JDK
1. In IntelliJ IDEA, navigate to File > Project Structure.

2. Under the Project Settings section, select Project.

3. In the Project SDK dropdown, click Add SDK > JDK.

4. Browse to the installation directory of your JDK and select it.

5. Ensure the language level is set to match the JDK version (e.g., SDK 11 for Java 11).

6. Click Apply and OK to save the settings.

Your environment is now set up to compile and run the project!

## 3. Implemented and Working Properly
### 3.1 Separate Screens
#### 3.1.1 Main Menu
- Main Menu screen is added before the start of game
- most of the buttons are working as expected (except for mute buttons in Settings screen which will be addressed in 4.2)
- 'Start Game' button will bring user to the first level of the game
- 'Settings' button will display a pop-up screen which contains mute buttons to mute and unmute the background music
- 'Quit' button will exit the game completely

#### 3.1.2 Win Screen
- Win screen is displayed at the end of game when user wins all the levels
- all buttons are working as expected
- 'Play Again' button will bring user to the first level of the game
- 'Main Menu' button will bring user to the Main Menu screen
  
#### 3.1.3 Lose Screen
- Lose screen is displayed when user wins loses a level
- all buttons are working as expected
- 'Restart' button will bring user to the first level of the game
- 'Main Menu' button will bring user to the Main Menu screen

### 3.2 New Levels
- Two new levels are added in addition to the original levels
- New assets are introduced in the new levels to enhance gameplay experience for user
- game logic is similar to first two levels


## 4. Implemented but Not Working Properly
### 4.1 Background Music
- due to this error 'Module not found: javafx.media', the backgrounf music was not able to be implemented
- this error was not resolve as other tasks was prioritised due to lack of time 

### 4.2 'Mute' and 'Unmute' buttons in Settings menu
- Due to 4.1, the buttons are redundant in the game
- There is no background music for the user to mute/unmute
  
### 4.3 'Main Menu' button in Win and Lose screens
- When user clicks the 'Main Menu' button in Win and Lose screens, the Main Menu screen displayed is not centered
- My guess on the occurence of this problem is that new MainMenu object is being created in Win and Lose screen instead of calling the previous MainMenu screen
- Due to lack of time, the logic of the buttons were being prioritised so this issue was not resolved 


## 5. Features Not Implemented
### 5.1 Pause Screen
- Due to the lack of time, pause screen was not implemented eventhough it was in the original plan as the other screens
  
### 5.2 Tutorial
- In my original plan, another button 'Tutorial' was supposed to be included in the Main Menu
- Tutorial is where user can play the 2 original levels as a practice game before starting the actual levels which are 'How To Train Your Dragon' themed
- Due to lack of time again, the idea was ditched and time was spent on ading the other additional features and making code more refactored

### 5.3 'Choose Your Dragon'
- There should also be a button called 'Choose Your Dragon' for user to choose their 'userplane' before proceeding to the game
- This idea was also ditched because of complexity and lack of time


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
- added a ProjectileFactory class to centralize the creation of all projectiles
- removed redundant constructor logic from individual projectile classes
- refactored Projectile class to handle shared functionality across all projectiles
- removed all individual projectile classes
- simplified client code by introducing a factory-based approach for creating projectiles

#### 6.1.13 PlaneFactory
- added a PlaneFactory class to centralize the creation of all planes
- removed redundant constructor logic from individual plane classes
- refactored Plane class to handle shared functionality across all planes
- simplified client code by introducing a factory-based approach for creating planes


### 6.2 New Levels
#### 6.2.1 LevelThree, LevelFour
- added two new levels with new assets and backgrounds as additions to make the game more enjoyable
- new levels are inspired by 'How To Train Your Dragon' animation movie

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


## 7. Modified Java Classes
### 7.1 Renaming Classes
#### 7.1.1 LevelView, LevelViewTwo
- renamed `LevelView` to `LevelParentView`
- renamed `LevelViewLevelTwo` to `LevelTwoView`
- for better clarity 

### 7.2 Fix Bugs
#### 7.2.1 ShieldImage
- fixed InvocationTargetException error by changing fixed "/com/example/demo/images/shield.jpg" to "/com/example/demo/images/shield.png"
- necessary to run the game

### 7.3 Introduce Packages
#### 7.3.1 actors, collision, controller, levels, ui and util under com.example.demo
- Separated classes into actors, collision, controller, levels, ui and util
- for better organisation of java files

### 7.4 Design Pattern : MVC
#### 7.4.1 LevelParent
- Split LevelParent class into LevelParen(model), LevelParentController(controller) and LevelParentView(view)
- to separate concerns in applications, enhancing maintainability, scalability, and testability

### 7.5 Single Responsibilities
#### 7.5.1 LevelParentView, HeartDisplay
- renamed `removeHearts` method in `LevelParent` to `updateHeartCount` to better reflect its purpose
- moved the heart removal logic to `HeartDisplay`, delegating the responsibility to the `HeartDisplay` class
- `HeartDisplay` now handles heart removal with a new `removeHearts` method, improving code organization and separation of concerns
- simplified `LevelParent` by offloading heart display management to `HeartDisplay`


## 8. Unexpected Problems
### 8.1 InvalidModuleDescriptorException Error
Challenge: This error occured after packages are introduced to organise my Java classes which causes a lot of time spent on searching and fixing the error
Resolution: Online resources and help from friends have helped me to solve the error. Error is resolved by deleting problematic `opens` directives in module descriptor

### 8.2 Time Management
Challenge: Due to too much time spent on fixing bugs and refactoring work, I had lesser time to implement more additional features. Lesser additional features are implemented than I have originally intended and current implemented features could be better
Resolution: Set certain timings to finish the tasks at hand to avoid overspending time on a certain task

