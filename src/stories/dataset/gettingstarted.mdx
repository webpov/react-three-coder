import { Meta } from "@storybook/blocks";


<Meta title="GPT/Dataset/Getting Started" />
##### Section: Getting Started
# Introduction
---
title: Introduction
description: React-three-fiber is a React renderer for three.js.
nav: 0
---

<a href="https://docs.pmnd.rs/react-three-fiber/getting-started/examples">
  <img src="https://github.com/pmndrs/react-three-fiber/raw/master/docs/banner-r3f.jpg" />
</a>
<br />

Build your scene declaratively with re-usable, self-contained components that react to state, are readily interactive and can participate in React's ecosystem.

```bash
npm install three @types/three @react-three/fiber
```

#### Does it have limitations?

None. Everything that works in Threejs will work here without exception.

#### Is it slower than plain Threejs?

No. There is no overhead. Components render outside of React. It outperforms Threejs in scale due to Reacts scheduling abilities.

#### Can it keep up with frequent feature updates to Threejs?

Yes. It merely expresses Threejs in JSX, `<mesh />` dynamically turns into `new THREE.Mesh()`. If a new Threejs version adds, removes or changes features, it will be available to you instantly without depending on updates to this library.

## What does it look like?

<table>
  <tbody>
    <tr>
      <td>
        Let's make a re-usable component that has its own state, reacts to user-input and participates in the
        render-loop. (<a href="https://codesandbox.io/s/rrppl0y8l4?file=/src/App.js">live demo</a>).
      </td>
      <td>
        <a href="https://codesandbox.io/s/rrppl0y8l4">
          <img
            src="https://github.com/pmndrs/react-three-fiber/raw/master/docs/basic-app.gif"
            alt="Two spinning orange cubes that turn purple on mouse over"
            width="252px"
            height="60px"
          />
        </a>
      </td>
    </tr>
  </tbody>
</table>

```jsx
import { createRoot } from 'react-dom/client'
import React, { useRef, useState } from 'react'
import { Canvas, useFrame } from '@react-three/fiber'

function Box(props) {
  // This reference will give us direct access to the mesh
  const meshRef = useRef()
  // Set up state for the hovered and active state
  const [hovered, setHover] = useState(false)
  const [active, setActive] = useState(false)
  // Subscribe this component to the render-loop, rotate the mesh every frame
  useFrame((state, delta) => (meshRef.current.rotation.x += delta))
  // Return view, these are regular three.js elements expressed in JSX
  return (
    <mesh
      {...props}
      ref={meshRef}
      scale={active ? 1.5 : 1}
      onClick={(event) => setActive(!active)}
      onPointerOver={(event) => setHover(true)}
      onPointerOut={(event) => setHover(false)}>
      <boxGeometry args={[1, 1, 1]} />
      <meshStandardMaterial color={hovered ? 'hotpink' : 'orange'} />
    </mesh>
  )
}

createRoot(document.getElementById('root')).render(
  <Canvas>
    <ambientLight intensity={Math.PI / 2} />
    <spotLight position={[10, 10, 10]} angle={0.15} penumbra={1} decay={0} intensity={Math.PI} />
    <pointLight position={[-10, -10, -10]} decay={0} intensity={Math.PI} />
    <Box position={[-1.2, 0, 0]} />
    <Box position={[1.2, 0, 0]} />
  </Canvas>,
)
```

<details>
  <summary>Show TypeScript example</summary>

```bash
npm install @types/three
```

```tsx
import * as THREE from 'three'
import { createRoot } from 'react-dom/client'
import React, { useRef, useState } from 'react'
import { Canvas, useFrame, ThreeElements } from '@react-three/fiber'

function Box(props: ThreeElements['mesh']) {
  const meshRef = useRef<THREE.Mesh>(null!)
  const [hovered, setHover] = useState(false)
  const [active, setActive] = useState(false)
  useFrame((state, delta) => (meshRef.current.rotation.x += delta))
  return (
    <mesh
      {...props}
      ref={meshRef}
      scale={active ? 1.5 : 1}
      onClick={(event) => setActive(!active)}
      onPointerOver={(event) => setHover(true)}
      onPointerOut={(event) => setHover(false)}>
      <boxGeometry args={[1, 1, 1]} />
      <meshStandardMaterial color={hovered ? 'hotpink' : 'orange'} />
    </mesh>
  )
}

createRoot(document.getElementById('root')).render(
  <Canvas>
    <ambientLight intensity={Math.PI / 2} />
    <spotLight position={[10, 10, 10]} angle={0.15} penumbra={1} decay={0} intensity={Math.PI} />
    <pointLight position={[-10, -10, -10]} decay={0} intensity={Math.PI} />
    <Box position={[-1.2, 0, 0]} />
    <Box position={[1.2, 0, 0]} />
  </Canvas>,
)
```

Live demo: https://codesandbox.io/s/icy-tree-brnsm?file=/src/App.tsx

</details>

<details>
  <summary>Show React Native example</summary>

For installation instructions see [react native installation instructions](https://docs.pmnd.rs/react-three-fiber/getting-started/installation#react-native).

```jsx
import React, { useRef, useState } from 'react'
import { Canvas, useFrame } from '@react-three/fiber/native'

function Box(props) {
  const meshRef = useRef(null)
  const [hovered, setHover] = useState(false)
  const [active, setActive] = useState(false)
  useFrame((state, delta) => (meshRef.current.rotation.x += delta))
  return (
    <mesh
      {...props}
      ref={meshRef}
      scale={active ? 1.5 : 1}
      onClick={(event) => setActive(!active)}
      onPointerOver={(event) => setHover(true)}
      onPointerOut={(event) => setHover(false)}>
      <boxGeometry args={[1, 1, 1]} />
      <meshStandardMaterial color={hovered ? 'hotpink' : 'orange'} />
    </mesh>
  )
}

export default function App() {
  return (
    <Canvas>
      <ambientLight intensity={Math.PI / 2} />
      <spotLight position={[10, 10, 10]} angle={0.15} penumbra={1} decay={0} intensity={Math.PI} />
      <pointLight position={[-10, -10, -10]} decay={0} intensity={Math.PI} />
      <Box position={[-1.2, 0, 0]} />
      <Box position={[1.2, 0, 0]} />
    </Canvas>
  )
}
```

</details>

## First steps

You need to be versed in both React and Threejs before rushing into this. If you are unsure about React consult the official [React docs](https://react.dev/learn), especially [the section about hooks](https://react.dev/reference/react). As for Threejs, make sure you at least glance over the following links:

1. Make sure you have a [basic grasp of Threejs](https://threejs.org/docs/index.html#manual/en/introduction/Creating-a-scene). Keep that site open.
2. When you know what a scene is, a camera, mesh, geometry, material, fork the [demo above](https://github.com/pmndrs/react-three-fiber#what-does-it-look-like).
3. [Look up](https://threejs.org/docs/index.html#api/en/objects/Mesh) the JSX elements that you see (mesh, ambientLight, etc), _all_ threejs exports are native to three-fiber.
4. Try changing some values, scroll through our [API](https://docs.pmnd.rs/react-three-fiber) to see what the various settings and hooks do.

Some helpful material:

- [Threejs-docs](https://threejs.org/docs) and [examples](https://threejs.org/examples)
- [Discover Threejs](https://discoverthreejs.com), especially the [Tips and Tricks](https://discoverthreejs.com/tips-and-tricks) chapter for best practices
- [Bruno Simons Threejs Jouney](https://threejs-journey.com), arguably the best learning resource, now includes a full [R3F chapter](https://threejs-journey.com/lessons/what-are-react-and-react-three-fiber)

<a href="https://threejs-journey.com">
  <img src="https://github.com/pmndrs/react-three-fiber/raw/master/docs/banner-journey.jpg" />
</a>

## Eco system

There is a vibrant and extensive eco system around three-fiber, full of libraries, helpers and abstractions.

- [`@react-three/drei`](https://github.com/pmndrs/drei) &ndash; useful helpers, this is an eco system in itself
- [`@react-three/gltfjsx`](https://github.com/pmndrs/gltfjsx) &ndash; turns GLTFs into JSX components
- [`@react-three/postprocessing`](https://github.com/pmndrs/react-postprocessing) &ndash; post-processing effects
- [`@react-three/test-renderer`](https://github.com/pmndrs/react-three-fiber/tree/master/packages/test-renderer) &ndash; for unit tests in node
- [`@react-three/flex`](https://github.com/pmndrs/react-three-flex) &ndash; flexbox for react-three-fiber
- [`@react-three/xr`](https://github.com/pmndrs/react-xr) &ndash; VR/AR controllers and events
- [`@react-three/csg`](https://github.com/pmndrs/react-three-csg) &ndash; constructive solid geometry
- [`@react-three/rapier`](https://github.com/pmndrs/react-three-rapier) &ndash; 3D physics using Rapier
- [`@react-three/cannon`](https://github.com/pmndrs/use-cannon) &ndash; 3D physics using Cannon
- [`@react-three/p2`](https://github.com/pmndrs/use-p2) &ndash; 2D physics using P2
- [`@react-three/a11y`](https://github.com/pmndrs/react-three-a11y) &ndash; real a11y for your scene
- [`@react-three/gpu-pathtracer`](https://github.com/pmndrs/react-three-gpu-pathtracer) &ndash; realistic path tracing
- [`create-r3f-app next`](https://github.com/pmndrs/react-three-next) &ndash; nextjs starter
- [`lamina`](https://github.com/pmndrs/lamina) &ndash; layer based shader materials
- [`zustand`](https://github.com/pmndrs/zustand) &ndash; flux based state management
- [`jotai`](https://github.com/pmndrs/jotai) &ndash; atoms based state management
- [`valtio`](https://github.com/pmndrs/valtio) &ndash; proxy based state management
- [`react-spring`](https://github.com/pmndrs/react-spring) &ndash; a spring-physics-based animation library
- [`framer-motion-3d`](https://www.framer.com/docs/three-introduction/) &ndash; framer motion, a popular animation library
- [`use-gesture`](https://github.com/pmndrs/react-use-gesture) &ndash; mouse/touch gestures
- [`leva`](https://github.com/pmndrs/leva) &ndash; create GUI controls in seconds
- [`maath`](https://github.com/pmndrs/maath) &ndash; a kitchen sink for math helpers
- [`miniplex`](https://github.com/hmans/miniplex) &ndash; ECS (entity management system)
- [`composer-suite`](https://github.com/hmans/composer-suite) &ndash; composing shaders, particles, effects and game mechanics

## How to contribute

If you like this project, please consider helping out. All contributions are welcome as well as donations to [Opencollective](https://opencollective.com/react-three-fiber), or in crypto `BTC: 36fuguTPxGCNnYZSRdgdh6Ea94brCAjMbH`, `ETH: 0x6E3f79Ea1d0dcedeb33D3fC6c34d2B1f156F2682`.

## Backers

Thank you to all our backers! 🙏

<a href="https://opencollective.com/react-three-fiber#backers" target="_blank">
  <img src="https://opencollective.com/react-three-fiber/backers.svg?width=890" />
</a>

## Contributors

This project exists thanks to all the people who contribute.

<a href="https://github.com/pmndrs/react-three-fiber/graphs/contributors">
  <img src="https://opencollective.com/react-three-fiber/contributors.svg?width=890" />
</a>







##### Section: Getting Started
# Installation
---
title: Installation
description: Learn how to install react-three-fiber
nav: 1
---

```bash
npm install three @react-three/fiber
```

> Fiber is compatible with React v18.0.0+ and works with ReactDOM and React Native.

Getting started with React Three Fiber is not nearly as hard as you might have thought, but various frameworks may require particular attention.

We've put together guides for getting started with each popular framework:

- Create React App
- Vite.js
- Next.js
- CDN w/o build tools
- React Native

If you just want to give it a try, fork this [example on codesandbox](https://codesandbox.io/s/rrppl0y8l4?file=/src/App.js)!

## Create React App

`create-react-app` will work out of the box, nothing special here!

```bash
# Create app
npx create-react-app my-app

# Install dependencies
cd my-app
npm install three @react-three/fiber

# Start development server
npm run start
```

## Vite.js

`vite` will also work out of the box.

```bash
# Create app
npm create vite my-app

# Select react as framework

# Install dependencies
cd my-app
npm install three @react-three/fiber

# Start development server
npm run dev
```

## Next.js

It should work out of the box but you will encounter untranspiled add-ons in the three.js ecosystem, in that case,

### Next.js 13.1 or latest version

You need to add three to `transpilePackages` property in `next.config.js`:

```js
transpilePackages: ['three'],
```

### Next.js 13.0 or oldest version

You can install the `next-transpile-modules` module:

```bash
npm install next-transpile-modules --save-dev
```

then, add this to your `next.config.js`

```js
const withTM = require('next-transpile-modules')(['three'])
module.exports = withTM()
```

Make sure to check out our [official next.js starter](https://github.com/pmndrs/react-three-next), too!

## Without build tools

You can use React Three Fiber with browser-ready ES Modules from [esm.sh](https://esm.sh) and a JSX-like syntax powered by [htm](https://github.com/developit/htm).

```jsx
import ReactDOM from 'https://esm.sh/react-dom'
import React, { useRef, useState } from 'https://esm.sh/react'
import { Canvas, useFrame } from 'https://esm.sh/@react-three/fiber'
import htm from 'https://esm.sh/htm'

const html = htm.bind(React.createElement)
ReactDOM.render(html`<${Canvas}>...<//>`, document.getElementById('root'))
```

<details>
<summary>Full example</summary>

```jsx
import ReactDOM from 'https://esm.sh/react-dom'
import React, { useRef, useState } from 'https://esm.sh/react'
import { Canvas, useFrame } from 'https://esm.sh/@react-three/fiber'
import htm from 'https://esm.sh/htm'

const html = htm.bind(React.createElement)

function Box(props) {
  const meshRef = useRef()
  const [hovered, setHover] = useState(false)
  const [active, setActive] = useState(false)
  useFrame(() => (meshRef.current.rotation.x = meshRef.current.rotation.y += 0.01))
  return html` <mesh
    ...${props}
    ref=${meshRef}
    scale=${active ? 1.5 : 1}
    onClick=${() => setActive(!active)}
    onPointerOver=${() => setHover(true)}
    onPointerOut=${() => setHover(false)}
  >
    <boxGeometry args=${[1, 1, 1]} />
    <meshStandardMaterial color=${hovered ? 'hotpink' : 'orange'} />
  </mesh>`
}

ReactDOM.render(
  html` <${Canvas}>
    <ambientLight />
    <pointLight position=${[10, 10, 10]} />
    <${Box} position=${[-1.2, 0, 0]} />
    <${Box} position=${[1.2, 0, 0]} />
  <//>`,
  document.getElementById('root'),
)
```

</details>

## React Native

R3F v8 adds support for react-native and can be imported from `@react-three/fiber/native`. We use `expo-gl` and `expo-asset` under the hood for WebGL2 bindings and ensuring interplay between Metro and three.js loaders.

To get started, create an app via `expo` or `react-native`:

```bash
# Create a managed/bare app
npx create-expo-app
cd my-app

# or

# Create and link bare app
npx react-native init my-app
npx install-expo-modules@latest
cd my-app
```

Then install dependencies (for manual installation or migration, see [expo modules installation](https://docs.expo.dev/bare/installing-expo-modules)):

```bash
# Automatically install
expo install expo-gl

# Install NPM dependencies
npm install three @react-three/fiber
```

Some configuration may be required to tell the Metro bundler about your assets if you use `useLoader` or Drei abstractions like `useGLTF` and `useTexture`:

```js
// metro.config.js
module.exports = {
  resolver: {
    sourceExts: ['js', 'jsx', 'json', 'ts', 'tsx', 'cjs', 'mjs'],
    assetExts: ['glb', 'gltf', 'png', 'jpg'],
  },
}
```

R3F's API is completely x-platform, so you can use [events](https://docs.pmnd.rs/react-three-fiber/api/events) and [hooks](https://docs.pmnd.rs/react-three-fiber/api/hooks) just as you would on the web.

Hint
  Make sure to import from `@react-three/fiber/native` or `@react-three/drei/native` for correct IntelliSense and
  platform-specific abstractions.
Hint

```jsx
import { Suspense } from 'react'
import { Canvas } from '@react-three/fiber/native'
import { useGLTF } from '@react-three/drei/native'
import modelPath from './path/to/model.glb'

function Model(props) {
  const gltf = useGLTF(modelPath)
  return <primitive {...props} object={gltf.scene} />
}

export default function App() {
  return (
    <Canvas>
      <ambientLight />
      <Suspense>
        <Model />
      </Suspense>
    </Canvas>
  )
}
```







---##### Section: Getting Started
# Your First Scene
title: Your first scene
description: This guide will help you setup your first React Three Fiber scene and introduce you to its core concepts.
nav: 2
---

This tutorial will assume some React knowledge.

## Setting up the Canvas

We'll start by importing the `<Canvas />` component from `@react-three/fiber` and putting it in our React tree.

```jsx
import { createRoot } from 'react-dom/client'
import { Canvas } from '@react-three/fiber'

function App() {
  return (
    <div id="canvas-container">
      <Canvas />
    </div>
  )
}

createRoot(document.getElementById('root')).render(<App />)
```

The Canvas component does some important setup work behind the scenes:

- It sets up a **Scene** and a **Camera**, the basic building blocks necessary for rendering
- It renders our scene every frame, you do not need a traditional render-loop

Hint
  Canvas is responsive to fit the parent node, so you can control how big it is by changing the parents width and
  height, in this case #canvas-container.
Hint

## Adding a Mesh Component

To actually see something in our scene, we'll add a lowercase `<mesh />` native element, which is the direct equivalent to new THREE.Mesh().

```js
<Canvas>
  <mesh />
```

Hint
  Note that we don't need to import anything, All three.js objects will be treated as native JSX elements, just like you
  can just write &lt;div /&gt; or &lt;span /&gt; in regular ReactDOM. The general rule is that Fiber components are
  available under the camel-case version of their name in three.js.
Hint

A [`Mesh`](https://threejs.org/docs/#api/en/objects/Mesh) is a basic scene object in three.js, and it's used to hold the geometry and the material needed to represent a shape in 3D space.
We'll create a new mesh using a **BoxGeometry** and a **MeshStandardMaterial** which [automatically attach](https://docs.pmnd.rs/react-three-fiber/api/objects#attach) to their parent.

```jsx
<Canvas>
  <mesh>
    <boxGeometry />
    <meshStandardMaterial />
  </mesh>
```

Let's pause for a moment to understand exactly what is happening here. The code we just wrote is the equivalent to this three.js code:

```jsx
const scene = new THREE.Scene()
const camera = new THREE.PerspectiveCamera(75, width / height, 0.1, 1000)

const renderer = new THREE.WebGLRenderer()
renderer.setSize(width, height)
document.querySelector('#canvas-container').appendChild(renderer.domElement)

const mesh = new THREE.Mesh()
mesh.geometry = new THREE.BoxGeometry()
mesh.material = new THREE.MeshStandardMaterial()

scene.add(mesh)

function animate() {
  requestAnimationFrame(animate)
  renderer.render(scene, camera)
}

animate()
```
# bad from here
### Constructor arguments

According to the [docs for `BoxGeometry`](https://threejs.org/docs/#api/en/geometries/BoxGeometry) we can optionally pass three arguments for: width, length and depth:

```js
new THREE.BoxGeometry(2, 2, 2)
```

In order to do this in Fiber we use the `args` prop, which _always_ takes an array whose items represent the constructor arguments.

```jsx
<boxGeometry args={[2, 2, 2]} />
```

HintNote that every time you change args, the object must be re-constructed!Hint

## Adding lights

Next, we will add some lights to our scene, by putting these components into our canvas.

```jsx
<Canvas>
  <ambientLight intensity={0.1} />
  <directionalLight color="red" position={[0, 0, 5]} />
```

### Props

This introduces us to the last fundamental concept of Fiber, how React `props` work on three.js objects. When you set any prop on a Fiber component, it will set the property of the same name on the three.js instance.

Let's focus on our `ambientLight`, whose [documentation](https://threejs.org/docs/#api/en/lights/AmbientLight) tells us that we can optionally construct it with a color, but it can also receive props.

```jsx
<ambientLight intensity={0.1} />
```

Which is the equivalent to:

```jsx
const light = new THREE.AmbientLight()
light.intensity = 0.1
```

### Shortcuts

There are a few shortcuts for props that have a `.set()` method (colors, vectors, etc).

```jsx
const light = new THREE.DirectionalLight()
light.position.set(0, 0, 5)
light.color.set('red')
```

Which is the same as the following in JSX:

```jsx
<directionalLight position={[0, 0, 5]} color="red" />
```

Please refer to the API for [a deeper explanation](/react-three-fiber/api/objects).

## The result

```jsx
<Canvas>
  <ambientLight intensity={0.1} />
  <directionalLight color="red" position={[0, 0, 5]} />
  <mesh>
    <boxGeometry />
    <meshStandardMaterial />
  </mesh>
</Canvas>
```

Codesandbox id="12q81" 

## Exercise

- try different materials, like [`MeshNormalMaterial`](https://threejs.org/docs/#api/en/materials/MeshNormalMaterial) or [`MeshBasicMaterial`](https://threejs.org/docs/#api/en/materials/MeshBasicMaterial), give them a color
- try different geometries, like [`SphereGeometry`](https://threejs.org/docs/#api/en/geometries/SphereGeometry) or [`OctahedronGeometry`](https://threejs.org/docs/#api/en/geometries/OctahedronGeometry)
- try changing the `position` on our `mesh` component, by setting the prop with the same name
- try extracting our mesh to a new component







##### Section: Getting Started
# Examples
---
title: Examples
description: A few examples that demonstrate what you can do with React Three Fiber
nav: 3
---

## Showcase
```
<Grid cols={1}>
  <li>
    Codesandbox id="9s2wd9" tags={['border-radius']} 
  </li>
</Grid>
<Grid cols={2}>
  <li>
    Codesandbox id="7qytdw" tags={['bruno', 'simon', 'threejs-journey', 'fisheye']} 
  </li>
  <li>
    Codesandbox id="xy8c8z" tags={['lusion', 'n8ao']} 
  </li>
  <li>
    Codesandbox id="nvk9pf" tags={['ecctrl', 'character-controller']} 
  </li>
  <li>
    Codesandbox id="bst0cy" tags={['effects', 'bloom', 'dof', 'reflections']} 
  </li>
  <li>
    Codesandbox id="2ycs3" tags={['effects', 'dof', 'bananas']} 
  </li>
  <li>
    Codesandbox id="ioxywi" tags={['configurator', 't-shirt', 'soft-shadows']} 
  </li>
  <li>
    Codesandbox id="szj6p7" tags={['caustics', 'effects', 'soft-shadows']} 
  </li>
  <li>
    Codesandbox id="5w35n6" tags={['ssgi', 'rapier']} 
  </li>
</Grid>
<Grid cols={4}>
  <li>
    Codesandbox id="gwthnh" tags={['clouds']} 
  </li>
  <li>
    Codesandbox id="2y73c6" tags={['motion-path', 'clouds']} 
  </li>
  <li>
    Codesandbox id="ykfpwf" tags={['caustics', 'effects', 'soft-shadows']} 
  </li>
  <li>
    Codesandbox id="yggpw5" tags={['godrays', 'reflections']} 
  </li>
  <li>
    Codesandbox id="9m4tpc" tags={['portals']} 
  </li>
  <li>
    Codesandbox id="qvk72r" tags={['portals']} 
  </li>
  <li>
    Codesandbox id="drc6qg" tags={['portals']} 
  </li>
  <li>
    Codesandbox id="dq6wwe" tags={['glass', 'transmission', 'bloom']} 
  </li>
  <li>
    Codesandbox id="dc5fjy" tags={['cards', 'image']} 
  </li>
  <li>
    Codesandbox id="3ywzzx" tags={['refraction']} 
  </li>
  <li>
    Codesandbox id="lx2h8" tags={['reflections', 'annotations']} 
  </li>
  <li>
    Codesandbox id="l4klb" tags={['scroll', 'controls']} 
  </li>
  <li>
    Codesandbox id="zxpv7" tags={['physics']} 
  </li>
  <li>
    Codesandbox id="0n9it" tags={['html', 'annotations']} 
  </li>
  <li>
    Codesandbox id="imn42" tags={['frosted', 'glass', 'transmission']} 
  </li>
  <li>
    Codesandbox id="pbwi6i" tags={['gltfjsx', 'effects', 'bloom', 'soft-shadows']} 
  </li>
  <li>
    Codesandbox id="fslt99" tags={['effects', 'reflections', 'ssr', 'bloom']} 
  </li>
  <li>
    Codesandbox id="2qfxj4" tags={['rapier', 'physics', 'soft-shadows']} 
  </li>
  <li>
    Codesandbox id="2n98yj" tags={['scroll', 'refraction', 'lens']} 
  </li>
  <li>
    Codesandbox id="e662p3" tags={['effects', 'bloom', 'reflections']} 
  </li>
  <li>
    Codesandbox id="j3ycvl" tags={['effects', 'bloom']} 
  </li>
  <li>
    Codesandbox id="lwo219" tags={['custom', 'environments']} 
  </li>
  <li>
    Codesandbox id="qxjoj" tags={['gltfjsx', 'configurator']} 
  </li>
  <li>
    Codesandbox id="dvokj" tags={['audio', 'analyser']} 
  </li>
  <li>
    Codesandbox id="bfplr" tags={['ground', 'reflections', 'video-texture']} 
  </li>
  <li>
    Codesandbox id="ni6v4" tags={['bruno-simon', 'threejs-journey']} 
  </li>
  <li>
    Codesandbox id="9keg6" tags={['html', 'iframe']} 
  </li>
  <li>
    Codesandbox id="f79ucc" tags={['splinetool', 'iframe']} 
  </li>
  <li>
    Codesandbox id="zqrreo" tags={['refraction']} 
  </li>
  <li>
    Codesandbox id="4gy946" tags={['refraction', 'instanced']} 
  </li>
  <li>
    Codesandbox id="q48jgy" tags={['ground-projected-env']} 
  </li>
  <li>
    Codesandbox id="ju368j" tags={['splinetool', 'transmission']} 
  </li>
  <li>
    Codesandbox id="mlgzsc" tags={['transmission', 'csg']} 
  </li>
  <li>
    Codesandbox id="y52tmt" tags={['csg']} 
  </li>
  <li>
    Codesandbox id="hg3ejl" tags={['scroll', 'animation', 'effects', 'tiltshift']} 
  </li>
  <li>
    Codesandbox id="ssbdsw" tags={['physics', 'effects', 'n8ao']} 
  </li>
  <li>
    Codesandbox id="024uom" tags={['html', 'input']} 
  </li>
  <li>
    Codesandbox id="gsm1y" tags={['scroll']} 
  </li>
  <li>
    Codesandbox id="x8gvs" tags={['scroll']} 
  </li>
  <li>
    Codesandbox id="yjhzv" tags={['scroll']} 
  </li>
  <li>
    Codesandbox id="qpfgyp" tags={['effects', 'particles']} 
  </li>
  <li>
    Codesandbox id="62o18n" tags={['cross-fade', 'transitions']} 
  </li>
  <li>
    Codesandbox id="8j36ok" tags={['transmission', 'portals', 'physics']} 
  </li>
  <li>
    Codesandbox id="n7jf0f" tags={['transmission', 'portals']} 
  </li>
  <li>
    Codesandbox id="ik11ln" tags={['portals', 'blend']} 
  </li>
  <li>
    Codesandbox id="lxvqek" 
  </li>
  <li>
    Codesandbox id="if9crg" 
  </li>
  <li>
    Codesandbox id="xzi6ps" 
  </li>
  <li>
    Codesandbox id="qvb1vk" 
  </li>
  <li>
    Codesandbox id="hxcc1x" 
  </li>
  <li>
    Codesandbox id="8pbw1f" 
  </li>
  <li>
    Codesandbox id="mw0dtc" 
  </li>
  <li>
    Codesandbox id="8flefh" 
  </li>
  <li>
    Codesandbox id="7e9y1b" 
  </li>
  <li>
    Codesandbox id="whnhyr" 
  </li>
  <li>
    Codesandbox id="0c5hv9" 
  </li>
  <li>
    Codesandbox id="0fqow2" 
  </li>
  <li>
    Codesandbox id="2ij9u" 
  </li>
  <li>
    Codesandbox id="42glz0" 
  </li>
  <li>
    Codesandbox id="ledhe1" 
  </li>
  <li>
    Codesandbox id="nurp5t" 
  </li>
  <li>
    Codesandbox id="2csbr1" 
  </li>
  <li>
    Codesandbox id="go0b4w" 
  </li>
  <li>
    Codesandbox id="s006f" 
  </li>
  <li>
    Codesandbox id="l900i" 
  </li>
  <li>
    Codesandbox id="qyz5r" 
  </li>
  <li>
    Codesandbox id="kv7tv" 
  </li>
  <li>
    Codesandbox id="ls503" 
  </li>
  <li>
    Codesandbox id="n60qg" 
  </li>
  <li>
    Codesandbox id="4jr4p" 
  </li>
  <li>
    Codesandbox id="kud9p" 
  </li>
  <li>
    Codesandbox id="zgsyn" 
  </li>
  <li>
    Codesandbox id="i6t0j" 
  </li>
  <li>
    Codesandbox id="h8o2d" 
  </li>
  <li>
    Codesandbox id="wu51m" 
  </li>
  <li>
    Codesandbox id="tu24h" 
  </li>
  <li>
    Codesandbox id="jz9l97qn89" 
  </li>
  <li>
    Codesandbox id="prb9t" 
  </li>
  <li>
    Codesandbox id="pecl6" 
  </li>
  <li>
    Codesandbox id="sbf2i" 
  </li>
  <li>
    Codesandbox id="t4l0f" 
  </li>
  <li>
    Codesandbox id="wdzv4" 
  </li>
  <li>
    Codesandbox id="6hi1y" 
  </li>
  <li>
    Codesandbox id="1sccp" 
  </li>
  <li>
    Codesandbox id="q23sw" 
  </li>
  <li>
    Codesandbox id="gpioq" 
  </li>
  <li>
    Codesandbox id="3rjsl" 
  </li>
  <li>
    Codesandbox id="4j2q2" 
  </li>
  <li>
    Codesandbox id="dh2jc" 
  </li>
  <li>
    Codesandbox id="gkfhr" 
  </li>
  <li>
    Codesandbox id="0buje" 
  </li>
  <li>
    Codesandbox id="5oufp" 
  </li>
  <li>
    Codesandbox id="f1ixt" 
  </li>
  <li>
    Codesandbox id="7psew" 
  </li>
  <li>
    Codesandbox id="vl221" 
  </li>
  <li>
    Codesandbox id="oep9o" 
  </li>
  <li>
    Codesandbox id="tx1pq" 
  </li>
</Grid>
```
## Game prototypes
```
<Grid>
  <li>
    Codesandbox id="lo6kp" 
  </li>
  <li>
    Codesandbox id="rmfcq" 
  </li>
  <li>
    Codesandbox id="i2160" 
  </li>
  <li>
    Codesandbox id="vkgi6" 
  </li>
  <li>
    Codesandbox id="2yqpv" 
  </li>
  <li>
    Codesandbox id="ptdgrn" 
  </li>
  <li>
    Codesandbox id="66cd7" 
  </li>
</Grid>
```
## Basic examples
```
<Grid>
  <li>
    Codesandbox id="rrppl0y8l4" 
  </li>
  <li>
    Codesandbox id="0z8i2c" 
  </li>
  <li>
    Codesandbox id="txzeq8" 
  </li>
  <li>
    Codesandbox id="pj7zjq" 
  </li>
  <li>
    Codesandbox id="wlz1o0" 
  </li>
  <li>
    Codesandbox id="7n2yru" 
  </li>
  <li>
    Codesandbox id="z3f2mw" 
  </li>
  <li>
    Codesandbox id="btsbj" 
  </li>
  <li>
    Codesandbox id="rz2g0" 
  </li>
  <li>
    Codesandbox id="8fo01" 
  </li>
  <li>
    Codesandbox id="7duy8" 
  </li>
  <li>
    Codesandbox id="bp6tmc" tags={['views', 'portals']} 
  </li>
  <li>
    Codesandbox id="r9w2ob" tags={['views', 'portals']} 
  </li>
  <li>
    Codesandbox id="p9umgf" tags={['html', 'scroll']} 
  </li>
  <li>
    Codesandbox id="k8phr" 
  </li>
  <li>
    Codesandbox id="dix1y" 
  </li>
  <li>
    Codesandbox id="zcuqh" 
  </li>
  <li>
    Codesandbox id="7ucso" 
  </li>
  <li>
    Codesandbox id="py4db" 
  </li>
  <li>
    Codesandbox id="hf1cs" 
  </li>
  <li>
    Codesandbox id="39hg8" 
  </li>
  <li>
    Codesandbox id="wbrfs" 
  </li>
  <li>
    Codesandbox id="itfgk" 
  </li>
  <li>
    Codesandbox id="iup24" 
  </li>
  <li>
    Codesandbox id="zu2wo" 
  </li>
  <li>
    Codesandbox id="1g4qq" 
  </li>
  <li>
    Codesandbox id="z8e6m" 
  </li>
  <li>
    Codesandbox id="h545c" 
  </li>
  <li>
    Codesandbox id="0k27n" 
  </li>
  <li>
    Codesandbox id="d36mw" 
  </li>
  <li>
    Codesandbox id="h873k" 
  </li>
  <li>
    Codesandbox id="08s1u" 
  </li>
  <li>
    Codesandbox id="wvgxp" 
  </li>
  <li>
    Codesandbox id="5xho4" 
  </li>
  <li>
    Codesandbox id="mbfzf" 
  </li>
  <li>
    Codesandbox id="mkq8e" 
  </li>
  <li>
    Codesandbox id="12nmp" 
  </li>
  <li>
    Codesandbox id="6oei7" 
  </li>
  <li>
    Codesandbox id="3k4g6" 
  </li>
  <li>
    Codesandbox id="3878x" 
  </li>
  <li>
    Codesandbox id="1b40u" 
  </li>
  <li>
    Codesandbox id="0ycwe" 
  </li>
  <li>
    Codesandbox id="ib0jc" 
  </li>
</Grid>
```