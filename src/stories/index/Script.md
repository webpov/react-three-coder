Follow these steps to make, a 3d web game.


##### Chapter 1:
Getting Started.

-- Section 1
### Install Libraries, and create a website.
Download and install, Node.js; at node "J S" dot org.
Then run these commands to continue:
- Step 1: Copy a website template, from a Next.js 13 web app:
  - ``` npx create next app...```.
- Step 2: Organize your project structure following the recommended schema:
  - ``` make dir...```.
- *Optionally;
  - Step 3: install all libraries needed for the project
    - ``` npm install...```.
- Finally: Run ```npm run dev``` to start a development server, at localhost

-- Section 2
### Make a State Machine
Implement react hooks, and local storage, to add interaction and data persistence:
- First: Install libraries
  - ``` npm i -s usehooks-ts```
- Second: Create react hooks for game logic
    ```txt
    # generate:
    * `a local storage hook with implementation`
    * `a basic counter react hook with several states and with local storage reusing the previous hook`    
    ```
- Third: Update UI display output

    -- Section 3
### 3D Web Game Upgrade
Integrate the state machine in 3D on the browser (React Three Fiber) into the project and start creating objects, scenes, and stages for the game interface.
- Part 1: Install 3d web libraries
  - ``` npm i -s @react-three/drei @react-three/fiber @types/three threeleva postprocessing three-obj-loader @react-three/postprocessing ```
- Part 2: Create basic 3d components
    ```txt
    # generate:
    * `a basic 3d component with onclick and counter of useState`    
    * Optional* `make the component forwardRef with useImperativeHandle`    
    ```
- Part 3: *Optionaly: Copy css from CSSCSS CDN
  - ``` https://unpkg.com/csscss@1.1.2/index.css  ```
