:page_facing_up: Project Expo
---------
All work-related usecase projects here

---------

:pencil: How to prototyped new UI screens faster?
---------
:warning: Issue
- A lot of popups need to be updated depending on the game state. 
- We didn't have an official pipeline on how don't do screens manually and reduce the duplicity of similar prefabs.
- Our pipeline forced us to build similar prefabs and reference to screens.

:bulb: Solution
- Create a modular UI prefab-based system that is able to build UI screens defined by code run time.
- Prefab holder keep references on unified prefabs based on category such as atomic, groups, popups.
- Ability to define screen template and change runtime depends on our needs and game states.

:white_check_mark: Features
- Modular UI prefabs
- Popups generated based on code script
- Runtime initialization
- Prefab caching 

:receipt: Basic architecture

---------

:pencil: How to optimized UI testing workflow for QA?  
---------
:warning: Issue
- Not stable codebase required to be re-tested almost after each code change.
- QA time is burned on typical UI test cases, it cost their time and energy.

:bulb: Solution
- Developed a simple UI testing tool that is able to run simple test cases to avoid basic human mistakes.
- Automatic run on specific screens during QA is doing regular testing session.  

:white_check_mark: Features
- Reusable test scenarios
- Automatic run on specific screens
- Different error handling 
  - Button reference
  - Text or image overlaps
  - Navigation validation after button click
  - HUD bitwise validation

:receipt: Basic architecture

---------

:pencil: How to avoid set active/inactive single elements of HUD during development? 
---------
:warning: Issue
- UI architecture does not support any layer of UI elements management.
- Each HUD element is referenced as a single or grouped game object that is not flexible enough.
- Our features like a tutorial or specific screens require of box layout what is currently now support.
- HUD implementation requires a lot of redundant game object active/deactive code.

:bulb: Solution
- Use a bitwise operation approach where each HUD element will have a single bit value.
- Give us the flexibility power to define custom groups depends on our needs.

:white_check_mark: Features
- Flexibility & easy to extend
- Simple usage from code or editor
- Performance focused

todo architecture

---------

:pencil: How to made UI/UX designers independent?
---------
:warning: Issue
- Screen effects are running by tweening library what is not easy to use for UI/UX designers as non-tech people
- When UI/UX designer want to change or tweak somehthing programmer is require do code changes 
- Currently we are also missing custom particle attractions which are not easy support by our implementation 


:bulb: Solution
- Developed custom UI particle tools to make UI/UX designers independent 
- Support our custom UI/UX wishlist features like draw hand path or reusing scenarios 

:white_check_mark: Features
- Easy to use for non-tech people
- Ability to support our custom needs

### Architecture

![image](https://user-images.githubusercontent.com/14979589/73868104-8f7ae180-4850-11ea-83e3-bb6a8cde332d.png)

### Examples

Implementation

![image](https://user-images.githubusercontent.com/14979589/73867506-8ccbbc80-484f-11ea-8df4-aa3fcee711c2.png)

Linear effect

![SimpleAttractorEffect](https://user-images.githubusercontent.com/14979589/73284387-29adaa80-41fd-11ea-8229-16e46664aa7a.gif)

Custom draw effect 

![DrawAttractorEffect](https://user-images.githubusercontent.com/14979589/73284391-2aded780-41fd-11ea-8573-99ed373e4bda.gif)

[Redirect to Project](https://github.com/AdrianOrcik/Unity_ParticleAttractor_Plugin_Source)


---------

:pencil: How to optimized level art prefabs workflow?
---------


:pencil: How to increased D1 retention with tutorial?
---------


:pencil: How to develop universal time manager?
---------


:pencil: How to download game definitions in one click?
---------


