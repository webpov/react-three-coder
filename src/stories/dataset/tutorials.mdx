import { Meta } from "@storybook/blocks";


<Meta title="GPT/Dataset/Tutorials" />
##### Section: Tutorials
# v8 Migration Guide
---
title: 'v8 Migration Guide'
description: Changes and new features with v8 and react 18
nav: 12
---

Work on version 8 has begun 3 Sep 2021 and is perhaps the biggest update to Fiber yet. We've tried our best to keep breaking-changes to a minimum, they mostly affect rarely used api's like `attach`. This release brings a ton of performance related fixes, but also includes some new and ground breaking features.

We would like to express our gratitude to the community for their continued support, as well as to all our contributors. 🎉

## React Native support

With React 18 and Expo 43, you can now ship threejs goodness across web and native. These apps are not confined to a web-view, they are truly native OpenGLES.

Now expo-gl, which does the hard lifting, has existed for a while, but we've addressed some of the common concerns related to interop and making the three eco system readily work in the native space. For instance, you handle assets the same exact way you'd treat them in a web app.

See [installation](/react-three-fiber/getting-started/installation#react-native) to get started with managed Expo or bare React Native apps.

```diff
- import { Canvas, useLoader } from '@react-three/fiber'
+ import { Canvas, useLoader } from '@react-three/fiber/native'

- import { useGLTF } from '@react-three/drei'
+ import { useGLTF } from '@react-three/drei/native'
```

This is complete with support for Pressability events and native threejs loaders. See [events](/react-three-fiber/api/events) for a complete list of events.

```jsx
<mesh
  onClick={(e) => console.log('onPress')}
  onPointerDown={(e) => console.log('onPressIn')}
  onPointerUp={(e) => console.log('onPressOut')}
  onDoubleClick={(e) => console.log('onLongPress')}
  onPointerOver={(e) => console.log('onHoverIn')}
  onPointerOut={(e) => console.log('onHoverOut')}
  onPointerMove={(e) => console.log('onPressMove')}
  // Not implemented
  // onContextMenu={(e) => console.log('context menu')}
  // onWheel={(e) => console.log('wheel spins')}
/>
```

```jsx
import React, { Suspense } from 'react'
import { useGLTF } from '@react-three/drei/native'
import { Canvas } from '@react-three/fiber/native'
import modelPath from './assets/model.glb'

function Model(props) {
  const { scene } = useGLTF(modelPath)
  return <primitive {...props} object={scene} />
}

export default function App() {
  return (
    <Canvas>
      <Suspense fallback={null}>
        <Model />
      </Suspense>
    </Canvas>
  )
}
```

React Native support was submitted by [@Cody_J_Bennett](https://twitter.com/Cody_J_Bennett). 🎉

## Zustand and suspend-react

Fiber uses [zustand](https://zustand.js.org/) to manage state. It's a simple, powerful, and performant state management library for React. And [suspend-react](https://github.com/pmndrs/suspend-react) to manage async ops and suspense (useLoader for instance). You can use these in your projects as well as they are to get closer interop with Fiber.

## New pixel ratio default

The default DPR has changed from `1` to `[1, 2]`, which will clamp between 1 and 2, but prefer 2, depending on the screen's native pixel ratio.

This was the most common setting in the wild, so it was brought in as a better default.

```diff
- <Canvas dpr={[1, 2]} />
+ <Canvas />
```

## Color management

Color management is now being handled by Three R139. Therefore we set `THREE.ColorManagement.enabled` to `true` and cede to touch colors and textures since everything will now be converted from sRGB to linear color space by Three itself.

You can manipulate this yourself with the `legacy` prop:

```jsx
// sets THREE.ColorManagement.enabled = false
<Canvas legacy={true}>
```

While you can of course use Fiber with any Three version you like we recommend updating to R139.

Check out https://threejs.org/docs/#manual/en/introduction/Color-management for information.

## Automatic concurrency

Concurrency is now part of React 18, which automatically switches between blocking (default) and concurrent (async).

```diff
- <Canvas mode="concurrent" />
+ <Canvas />
```

React 18 introduces the `startTransition` and `useTransition` APIs to defer and schedule expensive operations and state updates. Use these to de-prioritize expensive operations.

```jsx
import { startTransition } from 'react'
import { Points } from '@react-three/drei'

const [radius, setRadius] = useState(1)
const positions = calculatePositions(radius)
const colors = calculateColors(radius)
const sizes = calculateSizes(radius)

<Points
  positions={positions}
  colors={colors}
  sizes={sizes}
  onPointerOut={() => startTransition(() => setRadius(prev => prev + 1))}
>
  <meshBasicMaterial vertexColors />
</Points>
```

### Examples

Please be careful, this is an extreme stress test. It creates so much load that without React the browser will freeze or crash.

<p>
  <a href="https://codesandbox.io/s/qjo4t">
    <img width="49%" src="https://codesandbox.io/api/v1/sandboxes/qjo4t/screenshot.png" alt="View splitting" />
  </a>
</p>

## Conditional rendering with frameloop

`frameloop` can now be toggled to render conditionally. This is useful to toggle on user interaction or while in frame.

```jsx
const [frameloop, setFrameloop] = useState('never')

<Canvas
  frameloop={frameloop}
  onClick={() => setFrameloop('always')}
/>
```

Another usecase would be using intersection observers to stop the canvas when it's out of view.

```jsx
const canvasRef = useRef()
const [frameloop, setFrameloop] = useState('never')

useEffect(() => {
  const observer = new IntersectionObserver(([{ isIntersecting }]) => {
    setFrameloop(isIntersecting ? 'always' : 'never')
  }, {})

  observer.observe(canvasRef.current)
  return () => observer.disconnect()
}, [])

<Canvas ref={canvasRef} frameloop={frameloop} />
```

## Expanded gl prop

The `gl` prop can now accept both constructor args and renderer properties like the `camera` prop.

```jsx
<Canvas gl={{ alpha: false, physicallyCorrectLights: true }} />
```

It can also accept a synchronous callback to manually create a renderer. This allows you to use any custom renderer you want.

```jsx
<Canvas gl={(canvas) => new Renderer({ canvas })} />
```

## Improved WebXR handling

### Automatic WebXR switching

The `vr` prop was removed in favor of automatic WebXR switching. Whenever a session is requested, XR features are enabled, and the renderer will render at the native refresh rate. The inverse is true when exiting a session.

> `frameloop` will not be respected while in a session.

```diff
- <Canvas vr />
+ <Canvas />
```

### Extended useFrame

In addition to the automatic rendering, useFrame will expose the current [`XRFrame`](https://developer.mozilla.org/en-US/docs/Web/API/XRFrame) obtained via [XRSession#requestAnimationFrame](https://developer.mozilla.org/en-US/docs/Web/API/XRSession/requestAnimationFrame).

```ts
useFrame((state: RootState, delta: number, frame?: THREE.XRFrame) => { ... })
```

This removes the need for custom rendering loops when using WebXR pose data and abstractions like `useXRFrame` of [@react-three/xr](https://github.com/pmndrs/react-xr).

## Manual camera manipulation

By default Fiber is responsive and will set up cameras properly on resize (aspect ratio etc).

Cameras can be controlled manually by setting `manual` to true in `camera`. This will opt out of projection matrix recalculation when the drawing area resizes.

```jsx
<Canvas camera={{ manual: true }}>
```

This is also supported by all cameras that you create, be it a THREE.PerspectiveCamera or drei/cameras, put `manual` on it and Fiber will not touch it.

```jsx
import { PerspectiveCamera } from '@react-three/drei'
<Canvas>
  <PerspectiveCamera makeDefault manual />
</Canvas>
```

## Unified attach API

Previously, attach had multiple signatures:

- `attach="name"`
- `attachObject={["name", "attribute"]}`
- `attachArray="name"`
- `attachFns={["add", "remove"]}`
- `attachFns={[(self, parent) => parent.add(self), (self, parent) => parent.remove(self)]}`

This is now a single, unified signature with support for piercing and named attach functions or custom handlers.

```jsx
// Attach foo to parent.a
<foo attach="a" />

// Attach foo to parent.a.b and a.b.c (nested object attach)
<foo attach="a-b" />
<foo attach="a-b-c" />

// Attach foo to parent.a[0] and [1] (array attach is just object attach)
<foo attach="a-0" />
<foo attach="a-1" />

// Attach foo to parent via explicit add/remove functions
<foo attach={(parent, self) => {
  parent.add(self)
  return () => parent.remove(self)
} />

// The same as a one liner
<foo attach={(parent, self) => (parent.add(self), () => parent.remove(self))} />
```

### Real-world use-cases:

Attaching to nested objects:

```diff
- <directionalLight
-   castShadow
-   position={[2.5, 8, 5]}
-   shadow-mapSize={[1024, 1024]}
-   shadow-camera-far={50}
-   shadow-camera-left={-10}
-   shadow-camera-right={10}
-   shadow-camera-top={10}
-   shadow-camera-bottom={-10}
- />
+ <directionalLight castShadow position={[2.5, 8, 5]} shadow-mapSize={[1024, 1024]}>
+   <orthographicCamera attach="shadow-camera" args={[-10, 10, 10, -10]} />
+ </directionalLight>
```

```diff
<bufferGeometry>
-   <bufferAttribute attachObject={['attributes', 'position']} count={count} array={vertices} itemSize={3} />
+   <bufferAttribute attach="attributes-position" count={count} array={vertices} itemSize={3} />
</bufferGeometry>
```

Arrays must be explcit now:

```diff
<mesh>
-  {colors.map((color, index) => <meshBasicMaterial key={index} attachArray="material" color={color} />)}
+  {colors.map((color, index) => <meshBasicMaterial key={index} attach={`material-${index}`} color={color} />)}
</mesh>
```

## Spread Canvas props

The `<Canvas />` can now accept non-render props to spread as native props: styles, classes, events, a11y, ...

```diff
- <div aria-describedby={...}>
-  <Canvas />
- </div>
+ <Canvas aria-describedby={...} />
```

## New createRoot API

`render` is depreciated in v8 for the new `createRoot` signature.

```diff
import {
- render,
+ createRoot,
  events
} from '@react-three/fiber'

- render(<mesh />, canvas, { event })
+ createRoot(canvas).configure({ events }).render(<mesh />)
```

Here is a typical setup:

```jsx
import * as THREE from 'three'
import { extend, createRoot, events } from '@react-three/fiber'

extend(THREE)

const root = createRoot(document.querySelector('#root'))

window.addEventListener('resize', () => {
  root.configure({
    events,
    camera: { position: [0, 0, 50], fov: 50 },
    size: { width: window.innerWidth, height: window.innerHeight },
  })
  root.render(<App />)
})
window.dispatchEvent(new Event('resize'))

// This is how you would unmount the root
// root.unmount()
```

### Examples

This is a custom-renderer example using the createRoot api:

<p>
  <a href="https://codesandbox.io/s/zcuqh">
    <img width="49%" src="https://codesandbox.io/api/v1/sandboxes/zcuqh/screenshot.png" alt="View splitting" />
  </a>
</p>

## Tree-shaking via extend

The underlying reconciler no longer pulls in the THREE namespace automatically.

This enables a granular catalogue and tree-shaking via the `extend` API:

```jsx
import { extend, createRoot } from '@react-three/fiber'
import { Mesh, BoxGeometry, MeshStandardMaterial } from 'three'

extend({ Mesh, BoxGeometry, MeshStandardMaterial })

createRoot(canvas).render(
  <mesh>
    <boxGeometry />
    <meshStandardMaterial />
  </mesh>,
)
```

There's an [official babel plugin](https://github.com/pmndrs/react-three-babel) which will do this for you automatically:

```jsx
// In:

import { createRoot } from '@react-three/fiber'

createRoot(canvasNode).render(
  <mesh>
    <boxGeometry />
    <meshStandardMaterial />
  </mesh>,
)

// Out:

import { createRoot, extend } from '@react-three/fiber'
import { Mesh as _Mesh, BoxGeometry as _BoxGeometry, MeshStandardMaterial as _MeshStandardMaterial } from 'three'

extend({
  Mesh: _Mesh,
  BoxGeometry: _BoxGeometry,
  MeshStandardMaterial: _MeshStandardMaterial,
})

createRoot(canvasNode).render(
  <mesh>
    <boxGeometry />
    <meshStandardMaterial />
  </mesh>,
)
```

No changes are necessary for `@react-three/test-renderer` as THREE is extended automatically.

## createPortal creates a state enclave

`createPortal` allows you to write a declarative JSX scene into a pre-existing, foreign object. This has been very useful for portals, heads-up displays, view-cubes, view splitting, etc.

But these things were very limited and lacked event support as well as support for eco-system packages (for instance putting OrbitControls into a split view).

With this release `createPortal` creates a virtual state-model in which everything keeps functioning. Events work, you can use any 3rd party eco-system control and throw it in there.

The event layering part of this was submitted by [@theatre_js](https://twitter.com/theatre_js) and [@AndrewPrifer](https://twitter.com/AndrewPrifer) 🎉.

```jsx
import { createPortal } from '@react-three/fiber'

function HeadsUpDisplay({ children }) {
  const [scene] = useState(() => new THREE.Scene())
  return createPortal(children, scene, {
    /* Override RootState here */
  })
}
```

The event system in particular can now be layered, so that you can have portals inside portals with event priority. You can also inject objects into RootState right away, these will become the defaults inside the portalled state world and anything using `useThree` inside will receive these objects.

Here is an example of a layered portal:

```jsx
createPortal(children, scene, {
  camera: myCustomCamera,
  events: {
    priority: previousPriority - 1,
    compute: (event, state, previous) => {
      // First we call the previous state-onion-layers compute, this is what makes it possible to nest portals
      if (!previous.raycaster.camera) previous.events.compute(event, previous, previous.previousRoot.getState())
      // We run a quick check against the textured plane itself, if it isn't hit there's no need to raycast at all
      const [intersection] = previous.raycaster.intersectObject(ref.current)
      if (!intersection) return false
      // We take that hits uv coords, set up this layers raycaster, et voilà, we have raycasting with perspective shift
      const uv = intersection.uv
      state.raycaster.setFromCamera(state.pointer.set(uv.x * 2 - 1, uv.y * 2 - 1), camera)
    },
  },
})
```

`createPortal` can still be considered low-level and the exact API for `compute` is still experimental at this point. Expect ready-made components for portals, hud's and view-splitting to come to drei soon.

### Examples

<p>
  <a href="https://codesandbox.io/s/1wmlew">
    <img width="49%" src="https://codesandbox.io/api/v1/sandboxes/1wmlew/screenshot.png" alt="View splitting" />
  </a>
  <a href="https://codesandbox.io/s/kp1w5u">
    <img width="49%" src="https://codesandbox.io/api/v1/sandboxes/kp1w5u/screenshot.png" alt="Portals" />
  </a>
  <a href="https://codesandbox.io/s/dioqhj">
    <img width="49%" src="https://codesandbox.io/api/v1/sandboxes/dioqhj/screenshot.png" alt="Heads-up displays" />
  </a>
</p>

## RTTR Regex Matchers

test-renderer's `findByProps` and `findAllByProps` now accept RegExp matchers to search for variable or computed properties.

```ts
testInstance.findByProps(props)

// Also accepts RegExp matchers
testInstance.findByProps({ [prop]: /^match/i })
```

```ts
testInstance.findAllByProps(props)

// Also accepts RegExp matchers
testInstance.findAllByProps({ [prop]: /^matches/i })
```

React-three-test-renderer was submitted by [@_josh_ellis_](https://twitter.com/_josh_ellis_) 🎉.

## Deprecated

```diff
useFrame((state) => {
- state.mouse
+ state.pointer
```

```diff
onClick={(event) => {
- event.sourceEvent
+ event.nativeEvent

- event.spaceX
- event.spaceY
+ event.pointer
```







---
title: 'Events and Interaction'
description: Let's make our meshes react to user input.
nav: 13
---

This tutorial will assume some React knowledge, and will be based on [this starter codesandbox](https://codesandbox.io/s/getting-started-01-12q81?from-embed), so just fork it and follow along!

After we have our continuous loop running the next step would be to allow our mesh to react to user interaction, so in this part let's attach a click handler to the cube and make it bigger on click.

## User Interaction

Any Object3D that has a raycast method can receive a large number of events, for instance a mesh:

```jsx
<mesh
  onClick={(e) => console.log('click')}
  onContextMenu={(e) => console.log('context menu')}
  onDoubleClick={(e) => console.log('double click')}
  onWheel={(e) => console.log('wheel spins')}
  onPointerUp={(e) => console.log('up')}
  onPointerDown={(e) => console.log('down')}
  onPointerOver={(e) => console.log('over')}
  onPointerOut={(e) => console.log('out')}
  onPointerEnter={(e) => console.log('enter')}
  onPointerLeave={(e) => console.log('leave')}
  onPointerMove={(e) => console.log('move')}
  onPointerMissed={() => console.log('missed')}
  onUpdate={(self) => console.log('props have been updated')}
/>
```

From this we can see that what we need to do is use the old `onClick` event we use on any DOM element to react to a user clicking the mesh.

Let's add it then:

```jsx
<mesh onClick={() => alert('Hellooo')} ref={myMesh}>
  <boxGeometry />
  <meshPhongMaterial color="royalblue" />
</mesh>
```

We did it! We created the most boring interaction in the story of 3D and we made an alert show up. Now let's make it actually animate our mesh.

Let's start by setting some state to check if the mesh is active:

```jsx
const [active, setActive] = useState(false)
```

After we have this we can set the scale with a ternary operator like so:

```jsx
<mesh scale={active ? 1.5 : 1} onClick={() => setActive(!active)} ref={myMesh}>
  <boxGeometry />
  <meshPhongMaterial color="royalblue" />
</mesh>
```

If you try to click on your mesh now, it scales up and down. We just made our first interactive 3D mesh!

What we did in this chapter was:

- Attached a click handler to our mesh
- Added some state to track if the mesh is currently active
- Changed the scale based on that state

Codesandbox id="98ppy" 

**Exercises**

- Change other props of the mesh like the `position` or even the `color` of the material.
- Use `onPointerOver` and `onPointerOut` to change the props of the mesh on hover events.

## Next steps

We just made our mesh react to user interaction but it looks pretty bland without any transition, right?
In the next chapter let's integrate `react-spring` into our project to make this into an actual animation.







##### Section: Tutorials
# Loading Models
---
title: 'Loading Models'
description: 3D Software to the web!
nav: 14
---

> All the models in this page were created by Sara Vieira and are freely available to download from any of the sandboxes.

There are many types of 3D model extensions, in this page we will focus on loading the three most common ones: `GLTF`, `FBX` and `OBJ`. All of these will use the `useLoader` function but in slightly different ways.

This whole section will assume you have placed your models in the public folder or in a place in your application where you can import them easily.

## Loading GLTF models

Starting with the open standard and the one that has more support in React Three Fiber we will load a `.gltf` model.

Let's start by importing the two things we need:

```js
import { useLoader } from '@react-three/fiber'
import { GLTFLoader } from 'three/examples/jsm/loaders/GLTFLoader'
```

With this we can create a Model component and place it in our scene like so:

```jsx
function Scene() {
  const gltf = useLoader(GLTFLoader, '/Poimandres.gltf')
  return <primitive object={gltf.scene} />
}
```

You can play with the sandbox and see how it looks here after I added an HDRI background:

Codesandbox id="6etx1" 

### Loading GLTF models as JSX Components

Here comes the really fancy part, you can transform these models into React components and then use them as you would any React component.

To do this, grab your `GLTF` model and head over to [https://gltf.pmnd.rs/](https://gltf.pmnd.rs/) and drop your `GLTF`, after that you should see something like:

![gltfjsx](gltfjsx.png)

Let's now copy the code and move it over to `Model.js`:

```jsx
/*
Auto-generated by: https://github.com/pmndrs/gltfjsx
*/

import React, { useRef } from 'react'
import { useGLTF } from '@react-three/drei'

export default function Model(props) {
  const groupRef = useRef()
  const { nodes, materials } = useGLTF('/Poimandres.gltf')
  return (
    <group ref={groupRef} {...props} dispose={null}>
      <mesh castShadow receiveShadow geometry={nodes.Curve007_1.geometry} material={materials['Material.001']} />
      <mesh castShadow receiveShadow geometry={nodes.Curve007_2.geometry} material={materials['Material.002']} />
    </group>
  )
}

useGLTF.preload('/Poimandres.gltf')
```

Now we can import our model like we would import any React component and use it in our app:

```jsx
import { Suspense } from 'react'
import { Canvas } from '@react-three/fiber'
import { Environment } from '@react-three/drei'

import Model from './Model'

export default function App() {
  return (
    <div className="App">
      <Canvas>
        <Suspense fallback={null}>
          <Model />
          <Environment preset="sunset" background />
        </Suspense>
      </Canvas>
    </div>
  )
}
```

You can play with the sandbox here:

Codesandbox id="vbnbf" 

## Loading OBJ models

In this case, we will use the trusted `useLoader` hook but in combination with `three.js` `OBJLoader`.

```js
import { OBJLoader } from 'three/examples/jsm/loaders/OBJLoader'
import { useLoader } from '@react-three/fiber'
```

With these imported let's get the mesh into our scene:

```jsx
function Scene() {
  const obj = useLoader(OBJLoader, '/Poimandres.obj')
  return <primitive object={obj} />
}
```

And here we go, we have an OBJ model showing on the web! Pretty cool ah?

You can play with the sandbox here:

Codesandbox id="51zks" 

## Loading FBX models

Let's again use the trusted `useLoader` but this time with the `FBXLoader` that comes from `three.js`

```js
import { useLoader } from '@react-three/fiber'
import { FBXLoader } from 'three/examples/jsm/loaders/FBXLoader'
```

To create our scene we can get the FBX as a return value of the useLoader by passing the `FBXloader` and the location of our file like so:

```jsx
function Scene() {
  const fbx = useLoader(FBXLoader, '/Poimandres.fbx')
  return <primitive object={fbx} />
}
```

You can play with the sandbox here:

Codesandbox id="ssrfg" 

### Loading FBX models using useFBX

[@react-three/drei](https://github.com/pmndrs/drei) exports a very useful helper when it comes to loading FBX models and it's called `useFBX`, in this case there is no need to import anything from `three.js` as it is all done behind the scenes and we can just pass the location of the file to `useFBX` like so:

```jsx
function Scene() {
  const fbx = useFBX('/Poimandres.fbx')
  return <primitive object={fbx} />
}
```

You can play with the sandbox here:

Codesandbox id="m6p73" 

## Showing a loader

If your model is big and takes a while to load, it's always good to show a small loader of how much is already is loaded and again [@react-three/drei](https://github.com/pmndrs/drei) is here to help with `Html` and `useProgress`.

- `Html` allows you place plain ol' HTML in your canvas and render it like you would a normal DOM element.
- `useProgress` is a hook that gives you a bunch of information about the loading status of your model.

With these two things, we can create a very bare-bones loading component like so:

```jsx
import { Html, useProgress } from '@react-three/drei'

function Loader() {
  const { progress } = useProgress()
  return <Html center>{progress} % loaded</Html>
}
```

We can then wrap our model in it using `Suspense` like so:

```jsx
export default function App() {
  return (
    <Canvas>
      <Suspense fallback={<Loader />}>
        <Model />
      </Suspense>
    </Canvas>
  )
}
```

The hook returns much more than just the progress so there is a lot you can do there to give the user more information about the loading status of the application. You can play with all of them in this sandbox:

Codesandbox id="nn2m7" 







##### Section: Tutorials
# Loading Textures
---
title: 'Loading Textures'
description: Let's load some fancy textures.
nav: 15
---

> All textures used in this chapter were downloaded from [cc0textures](https://cc0textures.com/).

## Using TextureLoader & useLoader

To load the textures we will use the `TextureLoader` from three.js in combination with `useLoader` that will allow us to pass the location of the texture and get the map back.

It's better to explain with code, let's say you downloaded [this texture](https://cc0textures.com/view?id=PavingStones092) and placed it in the public folder of your site, to get the color map from it you could do:

```js
const colorMap = useLoader(TextureLoader, 'PavingStones092_1K_Color.jpg')
```

Let's then with this information create a small scene where we can use this texture:

```jsx
import { Suspense } from 'react'
import { Canvas, useLoader } from '@react-three/fiber'
import { TextureLoader } from 'three/src/loaders/TextureLoader'

function Scene() {
  const colorMap = useLoader(TextureLoader, 'PavingStones092_1K_Color.jpg')
  return (
    <>
      <ambientLight intensity={0.2} />
      <directionalLight />
      <mesh>
        <sphereGeometry args={[1, 32, 32]} />
        <meshStandardMaterial />
      </mesh>
    </>
  )
}

export default function App() {
  return (
    <Canvas>
      <Suspense fallback={null}>
        <Scene />
      </Suspense>
    </Canvas>
  )
}
```

If everything went according to plan, you should now be able to apply this texture to the sphere like so:

```jsx
<meshStandardMaterial map={colorMap} />
```

Awesome! That works but we have a lot more textures to import and do we have to create a different useLoader for each of them?

That's the great part! You don't, the second argument is an array where you can pass all the textures you have and the maps will be returned and ready to use:

```js
const [colorMap, displacementMap, normalMap, roughnessMap, aoMap] = useLoader(TextureLoader, [
  'PavingStones092_1K_Color.jpg',
  'PavingStones092_1K_Displacement.jpg',
  'PavingStones092_1K_Normal.jpg',
  'PavingStones092_1K_Roughness.jpg',
  'PavingStones092_1K_AmbientOcclusion.jpg',
])
```

Now we can place them in our mesh like so:

```jsx
<meshStandardMaterial
  map={colorMap}
  displacementMap={displacementMap}
  normalMap={normalMap}
  roughnessMap={roughnessMap}
  aoMap={aoMap}
/>
```

The displacement will probably be too much, usually setting it to 0.2 will make it look good. Our final code would look something like:

```jsx
function Scene() {
  const [colorMap, displacementMap, normalMap, roughnessMap, aoMap] = useLoader(TextureLoader, [
    'PavingStones092_1K_Color.jpg',
    'PavingStones092_1K_Displacement.jpg',
    'PavingStones092_1K_Normal.jpg',
    'PavingStones092_1K_Roughness.jpg',
    'PavingStones092_1K_AmbientOcclusion.jpg',
  ])
  return (
    <mesh>
      {/* Width and height segments for displacementMap */}
      <sphereGeometry args={[1, 100, 100]} />
      <meshStandardMaterial
        displacementScale={0.2}
        map={colorMap}
        displacementMap={displacementMap}
        normalMap={normalMap}
        roughnessMap={roughnessMap}
        aoMap={aoMap}
      />
    </mesh>
  )
}
```

## Using useTexture

Another way to import these is using `useTexture` from [`@react-three/drei`](https://github.com/pmndrs/drei), that will make it slightly easier and there is no need to import the `TextureLoader`, our code would look like:

```js
import { useTexture } from "@react-three/drei"

...

const [colorMap, displacementMap, normalMap, roughnessMap, aoMap] = useTexture([
  'PavingStones092_1K_Color.jpg',
  'PavingStones092_1K_Displacement.jpg',
  'PavingStones092_1K_Normal.jpg',
  'PavingStones092_1K_Roughness.jpg',
  'PavingStones092_1K_AmbientOcclusion.jpg',
])
```

You can also use object-notation which is the most convenient:

```jsx
const props = useTexture({
  map: 'PavingStones092_1K_Color.jpg',
  displacementMap: 'PavingStones092_1K_Displacement.jpg',
  normalMap: 'PavingStones092_1K_Normal.jpg',
  roughnessMap: 'PavingStones092_1K_Roughness.jpg',
  aoMap: 'PavingStones092_1K_AmbientOcclusion.jpg',
})

return (
  <mesh>
    <sphereGeometry args={[1, 32, 32]} />
    <meshStandardMaterial {...props} />
  </mesh>
)
```

You can play with the sandbox and see how it looks:

Codesandbox id="rusfd" 







---
title: Basic Animations
description: This guide will help you understand refs, useFrame and how to make basic animations with Fiber
nav: 16
---

This tutorial will assume some React knowledge, and will be based on [this starter codesandbox](https://codesandbox.io/s/getting-started-01-12q81?from-embed), so just fork it and follow along!

We will build a really small, continuous animation loop, that will be the basic building block of more advanced animations later on.

## useFrame

`useFrame` is a Fiber hook that lets you execute code on every frame of Fiber's render loop. This can have a lot of uses, but we will focus on building an animation with it.

It's important to remember that **Fiber hooks can only be called inside a `<Canvas />` parent**!

```jsx
import { useFrame } from '@react-three/fiber'

function MyAnimatedBox() {
  useFrame(() => {
    console.log("Hey, I'm executing every frame!")
  })
  return (
    <mesh>
      <boxGeometry />
      <meshBasicMaterial color="royalblue" />
    </mesh>
  )
}
```

This loop is the basic building block of our animation, the callback we pass to `useFrame` will be executed every frame and it will be passed an object containing the state of our Fiber scene:

For example, we can extract time information from the `clock` parameter, to know how much time has elapsed in our application, and use that time to animate a value:

```jsx
useFrame(({ clock }) => {
  const a = clock.getElapsedTime()
  console.log(a) // the value will be 0 at scene initialization and grow each frame
})
```

`clock` is a [three.js Clock](https://threejs.org/docs/#api/en/core/Clock) object, from which we are getting the total elapsed time, which will be key for our animations.

## Animating with Refs

It would be tempting to just update the state of our component via `setState` and let it change the `mesh` via props, but going through state isn't ideal, when dealing with continuous updates, commonly know as [transient updates]().
Instead, we want to **directly mutate our mesh each frame**. First, we'll have to get a `reference` to it, via the `useRef` React hook:

```jsx
import React from 'react'

function MyAnimatedBox() {
  const myMesh = React.useRef()
  return (
    <mesh ref={myMesh}>
      <boxGeometry />
      <meshBasicMaterial color="royalblue" />
    </mesh>
  )
}
```

`myMesh` will now hold a reference to the actual three.js object, which we can now freely mutate in `useFrame`, without having to worry about React:

```jsx
useFrame(({ clock }) => {
  myMesh.current.rotation.x = clock.getElapsedTime()
})
```

Let's have a closer look:

- We are destructuring `clock` from the argument passed to `useFrame`, which we know is the state of our Fiber scene.
- We are accessing the `rotation.x` property of `myMesh.current` object, which is a reference to our mesh object
- We are assigning our time-dependent value `a` to the `rotation` on the `x` axis, meaning our object will now infinitely rotate between -1 and 1 radians around the x axis!

Codesandbox id="29gxw" 

**Exercises**

- Try `Math.sin(clock.getElapsedTime())` and see how your animation changes

## Next steps

Now that you understand the basic technique for animating in Fiber, [learn how event works](/react-three-fiber/tutorials/events-and-interaction)!

If you want to go deeper into animations, check these out:

- [Animating with React Spring](/react-three-fiber/tutorials/using-with-react-spring)







##### Section: Tutorials
# Using with React Spring
---
title: 'Using with React Spring'
description: Animating props with ease.
nav: 17
---

This tutorial will assume some React knowledge, and will be based on [this starter codesandbox](https://codesandbox.io/s/interaction-98ppy?file=/src/App.js), so just fork it and follow along!

We learned how to create small animations and also how to react to user interactions, but we haven't yet learned how to change these props in a way to create animations.

For that, we are gonna use `react-spring`. `react-spring` is a spring physics based animation library and it works perfectly with React Three Fiber as it comes from the same maintainers, and it also has exports specifically created for use with React Three Fiber.

## Spring Animations

Let's start by defining some concepts about `react-spring` as it works with animations in a way you may not be used to. Usually when defining an animation or even a transition in CSS, you tell the code how much time you want the transition to last.

```css
transition: opacity 200ms ease;
```

This is not how `react-spring` works, it instead works with `springs` and what that means is, the animation's flow depends on things like the mass, tension and friction of what you want to animate, and this is exactly what makes it so perfect to use with 3D.

## Using `react-spring`

Let's start by installing it:

```bash
npm install three @react-spring/three
```

After that, we import everything from `@react-spring/three` as it contains the components that were created specifically for use with React Three Fiber.

We need to import two things from `react-spring`:

```js
import { useSpring, animated } from '@react-spring/three'
```

Let's go over them, shall we?

- `useSpring` - A hook to transform values into animated-values
- `animated` - A component that is used instead of your DOM or mesh, so instead of using `mesh` you will be using `animated.mesh` if you want it to be affected by `react-spring`

Let's create our first spring and attach it to our mesh when the user clicks.

```js
const springs = useSpring({ scale: active ? 1.5 : 1 })
```

What we did here is create a constant called `springs`, this constant will hold the animated values.

`useSpring` itself takes one argument, and that is an object with all the things you want to animate. In this case, we just want to animate the scale and to hop between the value of 1 and the value of 1.5 depending on the active state.

We can also deconstruct the return value of `useSpring` and just get the value we want, like so:

```js
const { scale } = useSpring({ scale: active ? 1.5 : 1 })
```

Now that we have this animated value, let's place it in our mesh:

```jsx
<animated.mesh scale={scale} onClick={() => setActive(!active)} ref={myMesh}>
  <boxGeometry />
  <meshPhongMaterial color="royalblue" />
</animated.mesh>
```

If you now click on the cube, you can see that it doesn't just jump from one value to the other, but instead it animates smoothly between the two values.

One last touch we might want to add is the wobblier effect to the animation. For that we can import the `config` object from `react-spring`:

```js
import { useSpring, animated, config } from '@react-spring/three'
```

Lastly when we call the hook, we can pass a value for config and pass the `wobbly` configuration:

```js
const { scale } = useSpring({
  scale: active ? 1.5 : 1,
  config: config.wobbly,
})
```

You can check the other configuration options at the [`react-spring` documentation](https://react-spring.io).

What we did in this chapter was:

- Learn how to use `react-spring` with React Three Fiber
- Animate props in our 3D Mesh

Codesandbox id="gykbc" 

**Exercises**

- Animate the position of the mesh using `react-spring`

**Further Reading**

- [React Spring Documentation](https://www.react-spring.io/)







##### Section: Tutorials
# Using with TypeScript
---
title: Using with TypeScript
description: This guide will help through common scenarios and how to approach them with TypeScript.
nav: 18
---

This tutorial will assume some React and TypeScript knowledge. You can fork and follow along from [this starter codesandbox](https://codesandbox.io/s/brnsm).

## Typing with useRef

React's `useRef` won't automatically infer types despite pointing it to a typed ref.

You can type the ref yourself by passing a type through `useRef`'s generics:

```tsx
import { useRef, useEffect } from 'react'
import { Mesh } from 'three'

function Box(props) {
  const meshRef = useRef<Mesh>(null!)

  useEffect(() => {
    console.log(Boolean(meshRef.current))
  }, [])

  return (
    <mesh {...props} ref={meshRef}>
      <boxGeometry />
      <meshBasicMaterial />
    </mesh>
  )
}
```

The exclamation mark is a non-null assertion that will let TS know that `ref.current` is defined when we access it in effects.

## Typing shorthand props

react-three-fiber accepts short-hand props like scalars, strings, and arrays so you can declaratively set properties without side effects.

Here are the different variations of props:

```tsx
import { Euler, Vector3, Color } from 'three'

rotation: Euler || [x, y, z]
position: Vector3 || [x, y, z] || scalar
color: Color || 'hotpink' || 0xffffff
```

Each property has extended types which you can pull from to type these properties.

```tsx
import { Euler, Vector3, Color } from '@react-three/fiber'
// or
// import { ReactThreeFiber } from '@react-three/fiber'
// ReactThreeFiber.Euler, ReactThreeFiber.Vector3, etc.

rotation: Euler
position: Vector3
color: Color
```

This is particularly useful if you are typing properties outside of components, such as a store or a hook.

## Extend usage

react-three-fiber can also accept third-party elements and extend them into its internal catalogue.

```tsx
import { useRef, useEffect } from 'react'
import { GridHelper } from 'three'
import { extend } from '@react-three/fiber'

// Create our custom element
class CustomElement extends GridHelper {}

// Extend so the reconciler will learn about it
extend({ CustomElement })
```

The catalogue teaches the underlying reconciler how to create fibers for these elements and treat them within the scene.

You can then declaratively create custom elements with primitives, but TypeScript won't know about them nor their props.

```html
// error: 'customElement' does not exist on type 'JSX.IntrinsicElements'

<customElement />
```

### Node Helpers

react-three-fiber exports helpers that you can use to define different types of nodes. These nodes will type an element that we'll attach to the global JSX namespace.

```tsx
Node
Object3DNode
BufferGeometryNode
MaterialNode
LightNode
```

### Extending ThreeElements

Since our custom element is an object, we'll use `Object3DNode` to define it.

```tsx
import { useRef, useEffect } from 'react'
import { GridHelper } from 'three'
import { extend, Object3DNode } from '@react-three/fiber'

// Create our custom element
class CustomElement extends GridHelper {}

// Extend so the reconciler will learn about it
extend({ CustomElement })

// Add types to ThreeElements elements so primitives pick up on it
declare module '@react-three/fiber' {
  interface ThreeElements {
    customElement: Object3DNode<CustomElement, typeof CustomElement>
  }
}

// react-three-fiber will create your custom component and TypeScript will understand it
<customComponent />
```

## Exported types

react-three-fiber is extensible and exports types for its internals, such as render props, canvas props, and events:

```tsx
// Event raycaster intersection
Intersection

// `useFrame` internal subscription and render callback
Subscription
RenderCallback

// `useThree`'s returned internal state
RootState
Performance
Dpr
Size
Viewport
Camera

// Canvas props
Props

// Supported events
Events

// Event manager signature (is completely modular)
EventManager

// Wraps a platform event as it's passed through the event manager
ThreeEvent
```







##### Section: Tutorials
# Testing
---
title: 'Testing'
description: Let's test our 3D Scene
nav: 19
---

Like with every other application testing is an important factor when it comes to releasing an application into the wild and when it comes to React Three Fiber we can use React Three Test Renderer to achieve this.

We will be testing the [sandbox](https://codesandbox.io/s/98ppy) we created in [events and interactions](events-and-interaction).

## How to test React Three Fiber

Let's start by installing the React Three Test Renderer:

```bash
npm install @react-three/test-renderer --save-dev
```

Afterwards, if you are using Create React App you can just add a file that ends in `.test.js` and start writing your code, because React Three Test Renderer is testing library agnostic, so it works with libraries such as `jest`, `jasmine` etc.

Let's create an `App.test.js` and set up all our test cases:

```jsx
import ReactThreeTestRenderer from '@react-three/test-renderer'
import { MyRotatingBox } from './App'

test('mesh to have two children', async () => {
  const renderer = await ReactThreeTestRenderer.create(<MyRotatingBox />)
})

test('click event makes box bigger', async () => {
  const renderer = await ReactThreeTestRenderer.create(<MyRotatingBox />)
})
```

In here we created three tests and in each we made sure we created the renderer by using the `create` function.

Let's start with the first test and make sure our mesh has two children, the material and cube.

We can start by getting the scene and it's children from the test instance we just created like so:

```js
const meshChildren = renderer.scene.children
```

If you log this mesh out you can see that it returns an array of one element since that's all we have in the scene.

Using this we can make sure to get that first child and use the `allChildren` property on it like so:

```js
const meshChildren = renderer.scene.children[0].allChildren
```

There is also one property called `children` but this one is meant to be used for things like groups as this one does not return the geometry and the materials, for that we need `allChildren`.

Now to create our assertion:

```js
expect(meshChildren.length).toBe(2)
```

Our first test case looks like this:

```js
test('mesh to have two children', async () => {
  const renderer = await ReactThreeTestRenderer.create(<MyRotatingBox />)
  const mesh = renderer.scene.children[0].allChildren
  expect(mesh.length).toBe(2)
})
```

## Testing interactions

Now that we have gotten the first test out of the way we can test our interaction and make sure that when we click on the mesh it does indeed update the scale.

We can do that by utilizing the `fireEvent` method existing in a test instance.

We know we can get the mesh with:

```js
const mesh = renderer.scene.children[0]
```

Since we already have that we can fire an event in it like so:

```js
await renderer.fireEvent(mesh, 'click')
```

With that done, all that's left to do is the tree demonstration of our scene and make sure the scale prop on our mesh has updated:

```js
expect(mesh.props.scale).toBe(1.5)
```

In the end our test looks something like this:

```js
test('click event makes box bigger', async () => {
  const renderer = await ReactThreeTestRenderer.create(<MyRotatingBox />)
  const mesh = renderer.scene.children[0]
  expect(mesh.props.scale).toBe(1)
  await renderer.fireEvent(mesh, 'click')
  expect(mesh.props.scale).toBe(1.5)
})
```

If you want to learn more about React Three Test Renderer you can checkout the repo and their docs:

- [Repo](https://github.com/pmndrs/react-three-fiber/blob/master/packages/test-renderer)
- [React Three Test Renderer API](https://github.com/pmndrs/react-three-fiber/blob/master/packages/test-renderer/markdown/rttr.md#create)
- [React Three Test Instance API](https://github.com/pmndrs/react-three-fiber/blob/master/packages/test-renderer/markdown/rttr-instance.md)

## Exercises

- Check the color of the Box we created
- Check the rotation using the `advanceFrames` method.

Codesandbox id="hqut4" tests 







##### Section: Tutorials
# How does it work?
---
title: How does it work?
description: This is an advanced guide on the inner workings of Fiber, if you are just getting started, take a
  look at our introduction!
nav: 20
---

React Three Fiber is a React <a href="https://reactjs.org/docs/codebase-overview.html#renderers">renderer</a> for **three.js**.

This means that each Fiber component will effectively create a new THREE object that will be added to a `scene`.
Understanding how this works is not necessarily needed to use Fiber, but it will better arm you to deal with anything that you might need in your projects, reading other people's Fiber code and even help you contribute.

Let's take a small React example:

```jsx
import { Canvas } from '@react-three/fiber'

function MyApp() {
  return (
    <Canvas>
      <group>
        <mesh>
          <meshNormalMaterial />
          <boxGeometry args={[2, 2, 2]} />
        </mesh>
      </group>
    </Canvas>
  )
}
```

In three.js, this is equivalent to:

```js
import * as THREE from 'three'

const scene = new THREE.Scene() // <Canvas>

const group = new THREE.Group() // <group>

const mesh = new THREE.Mesh() // <mesh />
const material = new THREE.MeshNormalMaterial() // <meshNormalMaterial />
const geometry = new THREE.BoxGeometry(2, 2, 2) // <boxGeometry />

mesh.material = material
mesh.geometry = geometry

group.add(mesh)
scene.add(group)
```

Our `Canvas` element will create a new scene, and Fiber will instantiate new objects for each component and correctly compose them together in a scene graph!

Additionally, Fiber will:

- Setup a new perspective camera at [0, 0, 0] and set it as default
- Setup a **render loop** with automatic render to screen
- Setup pointer events via raycasting on all meshes with `onPointer` props
- Setup tone mapping
- Automatically handle window resize

**Let's break this down!**

## Creating THREE objects

In three.js, we can create new object using the classic JS API:

```js
const myBox = new THREE.BoxGeometry(1, 2, 3)
```

Object creation is handled transparently by the Fiber renderer, the name of the constructor `BoxGeometry` is equivalent to the camel case component `<boxGeometry />`, while the constructor arguments - in our example `[1, 2, 3]` - are passed via the `args` prop:

```jsx
<boxGeometry args={[1, 2, 3]} />
```

HintNote that the object will be created only when first adding the component to the React tree!Hint

## The `attach` props

Fiber always tries to correctly infer the relationship between components and their parents, for example:

```jsx
<group>
  <mesh />
</group>
```

Here, we always know that a group can only have children, so Fiber just calls the `add` method on the group:

```js
group.add(mesh)
```

For meshes and other three.js objects, rules can be different. Looking at the three.js documentation, we can see how a `THREE.Mesh` object is constructed using a `material` and a `geometry`.

With the `attach` prop, we can precisely tell the renderer what property to attach each component to:

```jsx
<mesh>
  <meshNormalMaterial attach="material" />
  <boxGeometry attach="geometry" />
</mesh>
```

This will _explicitly_ tell Fiber to render like this:

```js
mesh.material = new THREE.MeshNormalMaterial()
mesh.geometry = new THREE.BoxGeometry()
```

As you can see, the `attach` prop is telling Fiber to set the parent's `material` property to a reference to our `<meshNormalMaterial />` object.

Note that while we used geometry and material for this example, Fiber also infers the attach property from the
constructor name, so anything with `material` or `geometry` will automatically get attached to the correct property of
its parent.

## Props

With Fiber, you can pass any three.js property as a React property, and it will be assigned to the constructed object:

```jsx
<meshBasicMaterial color="red" />
```

is equivalent to:

```jsx
const material = new THREE.MeshBasicMaterial()
material.color = 'red'
```

Fiber will check the type of the property value and either:

- assign the new value directly
- if the value is an object with a `set` method, call that
- construct a new object if needed.
- convert between formats

```jsx
<mesh scale={[1, 2, 3]} />
```

is equivalent to:

```jsx
const mesh = new THREE.Mesh()
mesh.scale = new THREE.Vector3(1, 2, 3)

// on update, it will instead `set()` the vector
mesh.scale.set(3, 4, 5)
```

## Pointer Events

[Pointer Events](/react-three-fiber/api/events) are transparently handled by Fiber. On startup, it will create a [raycaster](https://threejs.org/docs/#api/en/core/Raycaster) for mouse picking.

Every object with `onPointer` props will be added to the array of objects checked every frame by the raycaster:

```jsx
<mesh onPointerDown={console.log}>...</mesh>
```

The ray's `origin` and `direction` are updated every time the mouse moves on the `<Canvas />` element or the window is resized.
Fiber also handles camera switching, meaning that the raycaster will always use the currently active camera.

When using the `raycast` prop, the object will instead be picked using a custom ray:

```jsx
import { useCamera } from '@react-three/drei'

return <mesh raycast={useCamera(anotherCamera)} />
```

## Render Loop

By default, Fiber will setup a render loop that renders the default `scene` from the default `camera` to a [WebGLRenderer](https://threejs.org/docs/#api/en/renderers/WebGLRenderer).

The loop is setup using [setAnimationLoop](https://threejs.org/docs/#api/en/renderers/WebGLRenderer.setAnimationLoop), which will execute its callback every time a new frame is renderable. This is what will happen every render:

1. All global before effects are executed
2. Clock delta is saved - implying all `useFrame` calls will share the same `delta`
3. `useFrame` callbacks are executed in order
4. `renderer.render(scene, camera)` is called, effectively rendering the scene to screen
5. All global after effects are executed
