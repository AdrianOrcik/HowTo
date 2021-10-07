:page_facing_up: Project use cases 
---------

Some of useful work-related project use cases I have been working on.

---------

<details><summary>How we prototyped new UI screens faster?</summary>

:pencil: How we prototyped new UI screens faster?
---------
:warning: Issue
- A lot of popups need to be updated depending on the game state
- We didn't have an official pipeline on how don't do screens manually and reduce the duplicity of similar prefabs
- Our pipeline forced us to build similar prefabs and reference to screens

:bulb: Solution
- Create a modular UI prefab-based system that is able to build UI screens defined by code run time
- Prefab holder keep references on unified prefabs based on category such as atomic, groups, popups
- Ability to define screen template and change runtime depends on our needs and game states

:white_check_mark: Features
- Modular UI prefabs
- Popups generated based on code script
- Runtime initialization
- Prefab caching 

:receipt: TODO architecture

</details>


<details><summary>How we optimized the UI testing workflow for QA? </summary>

:pencil: How we optimized the UI testing workflow for QA? 
---------
:warning: Issue
- Not stable codebase required to be re-tested almost after each code change
- QA time is burned on typical UI test cases, it cost their time and energy

:bulb: Solution
- Developed a simple UI testing tool that is able to run simple test cases to avoid basic human mistakes
- Automatic run on specific screens during QA is doing regular testing session  

:white_check_mark: Features
- Reusable test scenarios
- Automatic run on specific screens
- Different error handling 
  - Button reference
  - Text or image overlaps
  - Navigation validation after button click
  - HUD bitwise validation

:receipt: TODO architecture

</details>


<details><summary>How we avoided setting active/inactive single elements of HUD in code?</summary>

:pencil: How we avoided setting active/inactive single elements of HUD in code? 
---------
:warning: Issue
- UI architecture does not support any layer of UI elements management
- Each HUD element is referenced as a single or grouped game object that is not flexible enough
- Our features like a tutorial or specific screens require of box layout what is currently now support
- HUD implementation requires a lot of redundant game object active/deactive code

:bulb: Solution
- Use a bitwise operation approach where each HUD element will have a single bit value
- Give us the flexibility power to define custom groups depends on our needs

:white_check_mark: Features
- Flexibility & easy to extend
- Simple usage from code or editor
- Performance focused

:receipt: TODO architecture

</details>


<details><summary>How we made UI/UX designers independent?</summary>
  
:pencil: How we made UI/UX designers independent?
---------
:warning: Issue
- Screen effects are running by tweening the library what is not easy to use for UI/UX designers as non-tech people
- When UI/UX designer wants to change or tweak something programmer is required to do code changes 
- We also haven't been able to support the UI/UX wishlist with the current implementation 


:bulb: Solution
- Developed custom UI particle tools to make UI/UX designers independent 
- Support our custom UI/UX wishlist features like draw hand path or reusing scenarios 

:white_check_mark: Features
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


</details>


<details><summary>How we optimized level vehicle prefabs workflow for artist?</summary>

:pencil: How we optimized level vehicle prefabs workflow for artist?
---------
:warning: Issue
- Game contained a lot of customizable vehicles by skins or cargo
- For art was time-consuming and not easy to do these visual tweaks just in the scene

:bulb: Solution
- Cargo rendering tool with the ability to preview cargos and skins
- Tool has the ability not only to preview objects but set up cargo transform as well

:white_check_mark: Features
- Quick preview of vehicle skins and cargos 
- Cargo & vehicle transform prefab override
- One change could be applied for all groups of vehicles

### Architecture

![CargoArchitecture](https://user-images.githubusercontent.com/14979589/69476392-01ab6080-0de2-11ea-83c8-97a96a7c5eb1.PNG)

### Result

![renderResult](https://user-images.githubusercontent.com/14979589/69479649-40eca800-0e08-11ea-8cce-7618ae851f45.jpg)

[Redirect to the project](https://github.com/AdrianOrcik/Unity_UseCase_RenderingTool)

</details>


<details><summary>How we increased D1 retention and decrease bug rate with the new tutorial?</summary>
  
:pencil: How we increased D1 retention and decrease bug rate with the new tutorial?
---------
:warning: Issue
- Default tutorial implementation was mixed with feature code, caused mess and problems in the code 
- Not stable implementation produced new bugs while tried to be extended or changed
- Old implementation was not flexible enough to cover our D1 problem

:bulb: Solution
- Modular-based tutorial system which has its own logic layers and kept own implementation above features code
- Supported to run multiple tutorials and provided an easy way hot to A/B them in production
- Easy to implement new scenarios or modify old ones even for non-technical people
- Tutorial logic is segmented into specific components (camera, dialog, inventory) to be easily extended and maintainable

:white_check_mark: Features
- Own logic layer, not mixed feature code with tutorial specific code
- Tutorial editor suitable for designers 
- Ability to provide A/B tests and improve user onboarding 
- Easy maintainable component approach

### Architecture

![TutorialArchitecture](https://user-images.githubusercontent.com/14979589/83567193-e4daad00-a529-11ea-805c-38362a59382d.png)

### Examples

Old editor

![ToolResult](https://user-images.githubusercontent.com/14979589/83565759-99bf9a80-a527-11ea-8f5f-645b74f92514.png)

Improved editor

![NewTutorial](https://user-images.githubusercontent.com/14979589/136411497-828b4879-0d1e-4d9e-982a-66618f346eda.png)

Demo implementation in game

![TutorialDemo](https://user-images.githubusercontent.com/14979589/83566166-3da94600-a528-11ea-9c97-f1c664bef19f.gif)

[Redirect to the project](https://github.com/AdrianOrcik/Unity_UseCase_Tutorial)

</details>


<details><summary>How we developed a universal cross-project time manager?</summary>
  
:pencil: How we developed a universal cross-project time manager?
---------
:warning: Issue
- Not exist reusable unified time-based cross-project implementation 
- Missed manageable access to all timers in the game 
- Each implementation required to create a custom logic like events, time formats, etc

:bulb: Solution
- Not exist simple unified time-based cross-project implementation
- Easy to use with predefined rules, how things works  

:white_check_mark: Features
- Access to all times in the game
- Support multiple time formats (count down, count up, etc)
- Events and actions ready to use   

:receipt: TODO architecture

</details>


<details><summary>How we developed a pipeline with the ability to download game definitions by one click?</summary>
  
:pencil: How we developed a pipeline with the ability to download game definitions by one click?
---------
:warning: Issue
- Hard coded client game definitions is now enough flexible 
- During development we needed to has multiple versions of definitions

:bulb: Solution
- Used google sheet as main data holder with ability export json by with version by custom add-on
- Python script with usage of google API give as flexibility to see whats happening on central google drive 
- Unity implemnetation provide easy to use interface to manipulate with this definition data

:white_check_mark: Features
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

</details>
