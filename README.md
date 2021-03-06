:page_facing_up: Project use cases 
---------

Some of the useful work-related project use cases I have been working on.

---------

<details><summary>How to prototype faster new UI screens?</summary>

:pencil: How we prototype faster new UI screens?
---------
:warning: Issue
  ---------
- A lot of popups need to be updated depending on the game state
- We didn't have an official pipeline on how don't do screens manually and reduce the duplicity of similar prefabs
- Our pipeline forced us to build similar prefabs and reference them to screens

:bulb: Solution
  ---------
- Create a modular UI prefab-based system able to build UI screens defined by code even in run time
- Prefab holder keep references on unified prefabs based on category such as atomic, groups, popups
- Ability to define screen template and change runtime depends on our needs and game states

:white_check_mark: Features
  ---------
- Modularity and flexibility of UI screens
- Popups generated based on the scripts or editor
- Runtime initialization
- Prefab caching 

### Architecture

![UI Screen tool architecture](https://user-images.githubusercontent.com/14979589/136431076-5ad1784a-ea47-494f-b4a6-ee8b9d2d91e5.png)

---------
  
</details>


<details><summary>How to optimize the UI testing workflow for QA? </summary>

:pencil: How to optimize the UI testing workflow for QA? 
---------
:warning: Issue
  ---------
- Not stable codebase required to be re-tested almost after each code iteration
- QA time is burned by typical UI test cases

:bulb: Solution
  ---------
- Develop a simple UI testing tool that is able to run simple test cases and avoid basic human mistakes
- Run automatically on specific screens while QA is doing regular testing session  

:white_check_mark: Features
  ---------
- Reusable test scenarios
- Run automatically on specific screens
- Various error handling 
  - Button reference
  - Text or image overlaps
  - Navigation validation after button click
  - HUD bitwise validation, etc...

### Architecture
  
![UI Screen Validation Tool](https://user-images.githubusercontent.com/14979589/136432418-e25cf547-5494-4f27-8548-b749edeacd0f.png)

---------
  
</details>


<details><summary>How to avoid setting active/inactive single elements of HUD in code?</summary>

:pencil: How to avoid setting active/inactive single elements of HUD in code? 
---------
:warning: Issue
  ---------
- UI architecture does not support any layer of UI elements management
- Each HUD element is referenced as a single or grouped game object,  not flexible enough
- Features like a tutorial or specific screens required an out of box HUD layout
- HUD implementation requires a lot of redundant set active/inactive code

:bulb: Solution
  ---------
- Use a bitwise operation approach, each HUD element has a single bit value
- Flexibility power to define custom groups depends on our needs

:white_check_mark: Features
  ---------
- Flexibility & easy to extend
- Simple usage from code or editor
- Performance focused

### Architecture
  
  ![Screenshot 2021-10-08 at 12 36 14](https://user-images.githubusercontent.com/14979589/136533893-f72ed7fe-166a-40ef-84f5-3df4f7a275db.png)

---------
  
</details>


<details><summary>How to make UI/UX designers independent?</summary>
  
:pencil: How to make UI/UX designers independent?
---------
:warning: Issue
  ---------
- UI effects powered by the tween library what is not easy to use for non technical people for example like UI/UX people
- UI/UX designer wants to change or tweak something, the programmer is required to do changes in the code 
- We haven't been able to support the UI/UX wishlist with the current implementation as well


:bulb: Solution
  ---------
- Developed custom UI particle tools to make UI/UX designers independent 
- Support our custom UI/UX wishlist features like draw hand path or reusing scenarios 

:white_check_mark: Features
  ---------
- Easy to use for non-tech people
- Ability to support our custom needs

### Architecture

![image](https://user-images.githubusercontent.com/14979589/73868104-8f7ae180-4850-11ea-83e3-bb6a8cde332d.png)

### Result

Implementation

![image](https://user-images.githubusercontent.com/14979589/73867506-8ccbbc80-484f-11ea-8df4-aa3fcee711c2.png)

Linear effect

![SimpleAttractorEffect](https://user-images.githubusercontent.com/14979589/73284387-29adaa80-41fd-11ea-8229-16e46664aa7a.gif)

Custom draw effect 

![DrawAttractorEffect](https://user-images.githubusercontent.com/14979589/73284391-2aded780-41fd-11ea-8573-99ed373e4bda.gif)

[Redirect to project](https://github.com/AdrianOrcik/Unity_ParticleAttractor_Plugin_Source)
  
---------

</details>


<details><summary>How to optimize the workflow of vehicle prefabs for artists?</summary>

:pencil: How to optimize the workflow of vehicle prefabs for artists?
---------
:warning: Issue
  ---------
- Game has a lot of customizable vehicles by skins or cargos
- For artists, it was time-consuming and not easy to use these visual tweaks in the scene

:bulb: Solution
  ---------
- Cargo rendering tool with the ability to preview cargos and skins
- Tool has the ability not only to preview objects but set up cargo transform as well

:white_check_mark: Features
  ---------
- Quick preview of vehicle skins and cargos 
- Cargo & vehicle transform prefab override
- One change could be applied for all groups of vehicles

### Architecture

![CargoArchitecture](https://user-images.githubusercontent.com/14979589/69476392-01ab6080-0de2-11ea-83c8-97a96a7c5eb1.PNG)

### Result

![renderResult](https://user-images.githubusercontent.com/14979589/69479649-40eca800-0e08-11ea-8cce-7618ae851f45.jpg)

[Redirect to the project](https://github.com/AdrianOrcik/Unity_UseCase_RenderingTool)

---------
  
</details>


<details><summary>How to increase D1 retention and decrease bug rate with the new tutorials?</summary>
  
:pencil: How to increase D1 retention and decrease bug rate with the new tutorials?
---------
:warning: Issue
  ---------
- Default tutorial implementation mixed with feature code, caused mess and problems in the code 
- Not stable implementation produced new bugs while tried to be extended or changed
- Old implementation not flexible enough to solve D1 retention problem with changes of existing tutorial

:bulb: Solution
  ---------
- Modular-based system with own logic layer and kept own implementation above features code
- Support multiple tutorials and easy way how to A/B test them in the production
- Easy to implement new scenarios or modify old ones even for non-technical people
- Tutorial logic is segmented into specific components (camera, dialog, inventory) to be easily extended and maintainable

:white_check_mark: Features
  ---------
- Own logic layer, separated tutorial code from gameplay code
- Tutorial editor suitable for designers 
- Ability to A/B test and improve the user onboarding 
- Easy maintainable component approach

### Architecture
  
![TutorialArchitecture](https://user-images.githubusercontent.com/14979589/83567193-e4daad00-a529-11ea-805c-38362a59382d.png)

### Example

Old editor

![ToolResult](https://user-images.githubusercontent.com/14979589/83565759-99bf9a80-a527-11ea-8f5f-645b74f92514.png)

Improved editor

![NewTutorial](https://user-images.githubusercontent.com/14979589/136411497-828b4879-0d1e-4d9e-982a-66618f346eda.png)

Demo implementation in game

![TutorialDemo](https://user-images.githubusercontent.com/14979589/83566166-3da94600-a528-11ea-9c97-f1c664bef19f.gif)

[Redirect to the project](https://github.com/AdrianOrcik/Unity_UseCase_Tutorial)
 
---------
  
</details>


<details><summary>How to develop a universal cross-project time manager?</summary>
  
:pencil: How to develop a universal cross-project time manager?
---------
:warning: Issue
  ---------
- Not exist reusable unified time-based cross-project implementation 
- Missed manageable access to all timers in the game 
- Every new time implementation is required to create a custom logic like events, time formats, etc

:bulb: Solution
  ---------
- Develop a unified timing system with the ability to use cross-projects  
- Easy to use with predefined rules  

:white_check_mark: Features
  ---------
- Access to all times in the game
- Support multiple time formats (count down, count up, etc)
- Events and actions ready to use  

:receipt: Architecture
  
![TimestObj](https://user-images.githubusercontent.com/14979589/136458935-ff8d722b-e488-4e08-aae7-33fb4e2b52dd.PNG)

---------

</details>


<details><summary>How to develop a pipeline with the ability to download game definitions with one click?</summary>
  
:pencil: How to develop a pipeline with the ability to download game definitions with one click?
---------
:warning: Issue
  ---------
- Hardcoded client game definitions are now enough flexible 
- During development we needed to have multiple versions of definitions

:bulb: Solution
  ---------
- Used google sheet as main data holder with the ability to export JSON by with version by custom add-on
- Python script with the usage of google API gives as the flexibility to see what's happening on the central google drive 
- Unity implementation provides easy to use interface to manipulate with this definition data

:white_check_mark: Features
  ---------
- By one click to download a game definitions
- Game definition versions  

### Architecture

![Architecture](https://user-images.githubusercontent.com/14979589/89738801-36e90300-da84-11ea-8ccb-c5c4273725ac.png)

### Result

Google Sheet Add-on<br>
![ExportAdd-on](https://user-images.githubusercontent.com/14979589/89738913-0190e500-da85-11ea-8a63-62151db6a106.png)

Unity Definition Downloader Editor<br>
![UnityEditor](https://user-images.githubusercontent.com/14979589/89739003-b3301600-da85-11ea-88d6-fe6ab3536d7d.png)

[Redirect to project](https://github.com/AdrianOrcik/Unity_GameJam_GalaxyDefender)
    
---------
  
</details>
