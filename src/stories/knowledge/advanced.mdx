import { Meta } from "@storybook/blocks";


<Meta title="Knowledge/Files/Advanced" />
##### Section: Advanced
# Scaling performance
---
title: Scaling performance
description: This is a short primer on how to scale performance.
nav: 10
---

Running WebGL can be quite expensive depending on how powerful your devices are. In order to mitigate this, especially if you want to make your application available to a broad variety of devices, including weaker options, you should look into performance optimizations. This article goes through a couple of them.

## On-demand rendering

three.js apps usually run in a game-loop that executes 60 times a second, React Three Fiber is no different. This is perfectly fine when your scene has _constantly_ moving parts in it. This is what generally drains batteries the most and makes fans spin up.

But if the moving parts in your scene are allowed to come to rest, then it would be wasteful to keep rendering. In such cases you can opt into on-demand rendering, which will only render when necessary. This saves battery and keeps noisy fans in check.

Open the sandbox below in a full screen and look into dev tools, you will see that it is completely idle when nothing is going on. It renders only when you move the model.

Codesandbox id="wvgxp" 

All you need to do is set the canvas `frameloop` prop to `demand`. It will render frames whenever it detects prop changes throughout the component tree.

```jsx
<Canvas frameloop="demand">
```

### Triggering manual frames

One major caveat is that if anything in the tree _mutates_ props, then React cannot be aware of it and the display would be stale. For instance, camera controls just grab into the camera and mutate its values. Here you can use React Three Fiber's `invalidate` function to trigger frames manually.

```jsx
function Controls() {
  const orbitControlsRef = useRef()
  const { invalidate, camera, gl } = useThree()
  useEffect(() => {
    orbitControlsRef.current.addEventListener('change', invalidate)
    return () => orbitControlsRef.current.removeEventListener('change', invalidate)
  }, [])
  return <orbitControls ref={orbitControlsRef} args={[camera, gl.domElement]} />
```

HintDrei's controls do this automatically for you.Hint

Generally you can call invalidate whenever you need to render:

```jsx
invalidate()
```

Hint

Calling `invalidate()` will not render immediately, it merely requests a
new frame to be rendered out. Calling invalidate multiple times will not render multiple times.
Think of it as a flag to tell the system that something has changed.

Hint

## Re-using geometries and materials

Each geometry and material means additional overhead for the GPU. You should try to re-use resources if you know they will repeat.

You could do this globally:

```jsx
const red = new THREE.MeshLambertMaterial({ color: "red" })
const sphere = new THREE.SphereGeometry(1, 28, 28)

function Scene() {
  return (
    <>
      <mesh geometry={sphere} material={red} />
      <mesh position={[1, 2, 3]} geometry={sphere} material={red} />
```

If you create a material or color in global space - outside of React Three Fiber's `Canvas` context - you should enable [ColorManagement](https://threejs.org/docs/#manual/en/introduction/Color-management) in three.js. This will allow certain conversions (for hexadecimal and CSS colors in sRGB) to be made automatically, producing correct colors in all cases.

```jsx
import * as THREE from 'three'

// r150
THREE.ColorManagement.enabled = true

// r139-r149
THREE.ColorManagement.legacyMode = false
```

### Caching with useLoader

HintEvery resource that is loaded with useLoader is cached automatically!Hint

If you access a resource via useLoader with the same URL, throughout the component tree, then you will always refer to the same asset and thereby re-use it. This is especially useful if you run your GLTF assets through [GLTFJSX](https://github.com/pmndrs/gltfjsx) because it links up geometries and materials and thereby creates re-usable models.

Codesandbox id="dix1y" 

```jsx
function Shoe(props) {
  const { nodes, materials } = useLoader(GLTFLoader, "/shoe.glb")
  return (
    <group {...props} dispose={null}>
      <mesh geometry={nodes.shoe.geometry} material={materials.canvas} />
    </group>
  )
}

<Shoe position={[1, 2, 3]} />
<Shoe position={[4, 5, 6]} />
```

## Instancing

Each mesh is a draw call, you should be mindful of how many of these you employ: no more than 1000 as the very maximum, and optimally a few hundred or less. You can win performance back by reducing draw calls, for example by instancing repeating objects. This way you can have hundreds of thousands of objects in a single draw call.

Codesandbox id="h873k" 

Setting up instancing is not so hard, consult [the three.js docs](https://threejs.org/docs/#api/en/objects/InstancedMesh) if you need help.

```jsx
function Instances({ count = 100000, temp = new THREE.Object3D() }) {
  const instancedMeshRef = useRef()
  useEffect(() => {
    // Set positions
    for (let i = 0; i < count; i++) {
      temp.position.set(Math.random(), Math.random(), Math.random())
      temp.updateMatrix()
      instancedMeshRef.current.setMatrixAt(i, temp.matrix)
    }
    // Update the instance
    instancedMeshRef.current.instanceMatrix.needsUpdate = true
  }, [])
  return (
    <instancedMesh ref={instancedMeshRef} args={[null, null, count]}>
      <boxGeometry />
      <meshPhongMaterial />
    </instancedMesh>
  )
}
```

## Level of detail

Sometimes it can be beneficial to reduce the quality of an object the further it is away from the camera. Why would you display it full resolution if it is barely visible. This can be a good strategy to reduce the overall vertex-count which means less work for the GPU.

Scroll in and out to see the effect:

Codesandbox id="12nmp" 

There is a small component in Drei called `<Detailed />` which sets up LOD without boilerplate. You load or prepare a couple of resolution stages, as many as you like, and then give them the same amount of distances from the camera, starting from highest quality to lowest.

```jsx
import { Detailed, useGLTF } from '@react-three/drei'

function Model() {
  const [low, mid, high] = useGLTF(["/low.glb", "/mid.glb", "/high.glb"])
  return (
    <Detailed distances={[0, 10, 20]}>
      <mesh geometry={high} />
      <mesh geometry={mid} />
      <mesh geometry={low} />
    <Detailed/>
  )
}
```

## Nested loading

Nested loading means that lesser textures and models are loaded first, higher-resolution later.

The following sandbox goes through three loading stages:

- A loading indicator
- Low quality
- High quality

Codesandbox id="7duy8" 

And this is how easy it is to achieve it, you can nest suspense and even use it as a fallback:

```jsx
function App() {
  return (
    <Suspense fallback={<span>loading...</span>}>
      <Canvas>
        <Suspense fallback={<Model url="/low-quality.glb" />}>
          <Model url="/high-quality.glb" />
        </Suspense>
      </Canvas>
    </Suspense>
  )
}

function Model({ url }) {
  const { scene } = useGLTF(url)
  return <primitive object={scene} />
}
```

## Performance monitoring

Drei has a new component [PerformanceMonitor](https://github.com/pmndrs/drei#performancemonitor) that allows you to monitor, and adapt to, device performance. This component will collect the average fps (frames per second) over time. If after a couple of iterations the averages are below or above a threshold it will trigger onIncline and onDecline callbacks that allow you to respond. Typically you would reduce the quality of your scene, the resolution, effects, the amount of stuff to render, or, increase it if you have enough framerate to fill.

Since this would normally cause ping-ponging between the two callbacks you define upper and lower framerate bounds, as long as you stay within that margin nothing will trigger. Ideally your app should find its way into that margin by gradually altering quality.

A simple example for regulating the resolution. It starts out with 1.5, if the system falls below the bounds it goes to 1, if it's fast enough it goes to 2.

```jsx
function App() {
  const [dpr, setDpr] = useState(1.5)
  return (
    <Canvas dpr={dpr}>
      <PerformanceMonitor onIncline={() => setDpr(2)} onDecline={() => setDpr(1)} >
```

You can also use the onChange callback to get notified when the average changes in whichever direction. This allows you to make gradual changes. It gives you a factor between 0 and 1, which is increased by incline and decreased by decline. The factor is initially 0.5 by default.

```jsx
import round from 'lodash/round'

const [dpr, set] = useState(1)
return (
 <Canvas dpr={dpr}>
  <PerformanceMonitor onChange={({ factor }) => setDpr(round(0.5 + 1.5 * factor, 1))}>
```

If you still experience flip flops despite the bounds you can define a limit of flipflops. If it is met onFallback will be triggered which typically sets a lowest possible baseline for the app. After the fallback has been called PerformanceMonitor will shut down.

```jsx
<PerformanceMonitor flipflops={3} onFallback={() => setDpr(1)}>
```

PerformanceMonitor can also have children, if you wrap your app in it you get to use usePerformanceMonitor which allows individual components down the nested tree to respond to performance changes on their own.

```jsx
<PerformanceMonitor>
  <Effects />
</PerformanceMonitor>

function Effects() {
  usePerformanceMonitor({ onIncline, onDecline, onFallback, onChange })
  // ...
}
```

## Movement regression

Websites like Sketchfab make sure the scene is always fluid, running at 60 fps, and responsive, no matter which device is being used or how expensive a loaded model is. They do this by regressing movement, where effects, textures, shadows will slightly reduce quality until still-stand

The following sandbox uses expensive lights and post-processing. In order for it to run relatively smooth it will scale the pixel ratio on movement and also skip heavy post-processing effects like ambient occlusion.

Codesandbox id="pz0q6" 

When you inspect the state model you will notice an object called `performance`.

```jsx
performance: {
  current: 1,
  min: 0.1,
  max: 1,
  debounce: 200,
  regress: () => void,
},
```

- current: Performance factor alternates between min and max
- min: Performance lower bound (should be less than 1)
- max: Performance upper bound (no higher than 1)
- debounce: Debounce timeout until it goes to upper bound (1) again
- regress(): Function that temporarily regresses performance

You can define defaults like so:

```jsx
<Canvas performance={{ min: 0.5 }}>...</Canvas>
```

### This is how you can put the system into regression

The only thing you have to do is call `regress()`. When exactly you do that, that is up to you, but it could be when the mouse moves, or the scene is moving, for instance when controls fire their change-event.

Say you are using controls, then the following code puts the system in regress when they are active:

```jsx
const regress = useThree((state) => state.performance.regress)
useEffect(() => {
  controls.current?.addEventListener('change', regress)
```

### This is how you can respond to it

HintMere calls to `regress()` will not change or affect anything!Hint

Your app has to opt into performance scaling by listening to the performance `current`! The number itself will tell you what to do. 1 (max) means everything is ok, the default. Less than 1 (min) means a regression is requested and the number itself tells you how far you should go when scaling down.

For instance, you could simply multiply `current` with the pixelratio to cut down on resolution. If you have defined `min: 0.5` that would mean it will half the resolution for at least 200ms (delay) when regress is called. It can be used for anything else, too: switching off lights when `current < 1`, using lower-res textures, skip post-processing effects, etc. You could of course also animate/lerp these changes.

Here is a small prototype component that scales the pixel ratio:

```jsx
function AdaptivePixelRatio() {
  const current = useThree((state) => state.performance.current)
  const setPixelRatio = useThree((state) => state.setDpr)
  useEffect(() => {
    setPixelRatio(window.devicePixelRatio * current)
  }, [current])
  return null
}
```

Drop this component into the scene, combine it with the code above that calls `regress()`, and you have adaptive resolution:

```jsx
<AdaptivePixelRatio />
```

There are pre-made components for this already in the [Drei library](https://github.com/pmndrs/drei/#performance).

## Enable concurrency

React 18 introduces concurrent scheduling, specifically time slicing via `startTransition` and `useTransition`. This will virtualize the component graph, which then allows you to prioritise components and actions. Think of how a virtual list avoids scaling issues because it only renders as many items as the screen can take, it is not affected by the amount of items it has to render, be it 10 or 100.000.000.

React 18 functions very similar to this, it can potentially defer load and heavy tasks in ways that would be hard or impossible to achieve in a vanilla application. It thereby holds on to a stable framerate even in the most demanding situations.

The following benchmark shows how powerful concurrency can be: https://github.com/drcmda/scheduler-test

It simulates heavy load by creating hundreds of THREE.TextGeometry instances (510 to be exact). This class, like many others in three.js, is expensive and takes a while to construct. If all 510 instances are created the same time **it will cause approximately 1.5 seconds of pure jank** (Apple M1), the tab would normally freeze. It runs in an interval and **will execute every 2 seconds**.

|          | Distributed | At-once |
| -------- | ----------- | ------- |
| three.js | ~20fps      | ~5fps   |
| React    | ~60fps      | ~60fps  |

<p align="center">
  <img
    aria-label="three.js distributed"
    style={{ width: '50%', display: 'inline-block' }}
    src="https://github.com/drcmda/scheduler-test/raw/master/assets/three-distributed.jpg"
  />
  <img
    aria-label="three.js at once"
    style={{ width: '50%', display: 'inline-block' }}
    src="https://github.com/drcmda/scheduler-test/raw/master/assets/three-at-once.jpg"
  />
  <img
    aria-label="React distributed"
    style={{ width: '50%', display: 'inline-block' }}
    src="https://github.com/drcmda/scheduler-test/raw/master/assets/react-distributed.jpg"
  />
  <img
    aria-label="React at once"
    style={{ width: '50%', display: 'inline-block' }}
    src="https://github.com/drcmda/scheduler-test/raw/master/assets/react-at-once.jpg"
  />
</p>

For more on how to use this API, see [use startTransition for expensive ops](/react-three-fiber/advanced/pitfalls#use-starttransition-for-expensive-ops).







##### Section: Advanced
# Performance pitfalls
---
title: Performance pitfalls
description: Performance 1x1
nav: 11
---

## Tips and Tricks

This is a good overview: https://discoverthreejs.com/tips-and-tricks

The most important gotcha in three.js is that creating objects can be expensive, think twice before you mount/unmount things! Every material or light that you put into the scene has to compile, every geometry you create will be processed. Share materials and geometries if you can, either in global scope or locally:

```jsx
const geom = useMemo(() => new BoxGeometry(), [])
const mat = useMemo(() => new MeshBasicMaterial(), [])
return items.map(i => <mesh geometry={geom} material={mat} ...
```

Try to use [instancing](https://codesandbox.io/s/r3f-instanced-colors-8fo01) as much as you can when you need to display many objects of a similar type!

## Avoid setState in loops

TLDR, don't, mutate inside `useFrame`!

- Threejs has a render-loop, it does not work like the DOM does. **Fast updates are carried out in `useFrame` by mutation**. `useFrame` is your per-component render-loop.

- It is not enough to set values in succession, _you need frame deltas_. Instead of `position.x += 0.1` consider `position.x += delta` or your project will run at different speeds depending on the end-users system. Many updates in threejs need to be paired with update flags (`.needsUpdate = true`), or imperative functions (`.updateProjectionMatrix()`).

- You might be tempted to setState inside `useFrame` but there is no reason to. You would only complicate something as simple as an update by routing it through Reacts scheduler, triggering component render etc.

### ❌ setState in loops is bad

```jsx
useEffect(() => {
  const interval = setInterval(() => setX((x) => x + 0.1), 1)
  return () => clearInterval(interval)
}, [])
```

### ❌ setState in useFrame is bad

```jsx
const [x, setX] = useState(0)
useFrame(() => setX((x) => x + 0.1))
return <mesh position-x={x} />
```

### ❌ setState in fast events is bad

```jsx
<mesh onPointerMove={(e) => setX((x) => e.point.x)} />
```

### ✅ Instead, just mutate, use deltas

In general you should prefer useFrame. Consider mutating props safe as long as the component is the only entity that mutates. Use deltas instead of fixed values so that your app is refresh-rate independent and runs at the same speed everywhere!

```jsx
const meshRef = useRef()
useFrame((state, delta) => (meshRef.current.position.x += delta))
return <mesh ref={meshRef} />
```

Same goes for events, use references.

```jsx
<mesh onPointerMove={(e) => (ref.current.position.x = e.point.x)} />
```

If you must use intervals, use references as well, but keep in mind that this is not refresh-rate independent.

```jsx
useEffect(() => {
  const interval = setInterval(() => ref.current.position.x += 0.1, 1)
  return () => clearInterval(interval)
}, [])
```

## Handle animations in loops

The frame loop is where you should place your animations. For instance using lerp, or damp.

### ✅ Use lerp + useFrame

```jsx
function Signal({ active }) {
  const meshRef = useRef()
  useFrame((state, delta) => {
    meshRef.current.position.x = THREE.MathUtils.lerp(meshRef.current.position.x, active ? 100 : 0, 0.1)
  })
  return <mesh ref={meshRef} />
```

### ✅ Or react-spring

Or, use animation libraries. React-spring has its own frame-loop and animates outside of React. Framer-motion is another popular alternative.

```jsx
import { a, useSpring } from '@react-spring/three'

function Signal({ active }) {
  const { x } = useSpring({ x: active ? 100 : 0 })
  return <a.mesh position-x={x} />
```

## Do not bind to fast state reactively

Using state-managers and selective state is fine, but not for updates that happen rapidly for the same reason as above.

### ❌ Don't bind reactive fast-state

```jsx
import { useSelector } from 'react-redux'

// Assuming that x gets animated inside the store 60fps
const x = useSelector((state) => state.x)
return <mesh position-x={x} />
```

### ✅ Fetch state directly

For instance using [Zustand](https://github.com/pmndrs/zustand) (same in Redux et al).

```jsx
useFrame(() => (ref.current.position.x = api.getState().x))
return <mesh ref={ref} />
```

## Don't mount indiscriminately

In threejs it is very common to not re-mount at all, see the ["disposing of things"](https://discoverthreejs.com/tips-and-tricks/) section in discover-three. This is because buffers and materials get re-initialized/compiled, which can be expensive.

### ❌ Avoid mounting runtime

```jsx
{
  stage === 1 && <Stage1 />
}
{
  stage === 2 && <Stage2 />
}
{
  stage === 3 && <Stage3 />
}
```

### ✅ Consider using visibility instead

```jsx
<Stage1 visible={stage === 1} />
<Stage2 visible={stage === 2} />
<Stage3 visible={stage === 3} />

function Stage1(props) {
  return (
    <group {...props}>
      ...
```

### ✅ Use startTransition for expensive ops

React 18 introduces the `startTransition` and `useTransition` APIs to defer and schedule work and state updates. Use these to de-prioritize expensive operations.

Since version 8 of Fiber canvases use concurrent mode by default, which means React will schedule and defer expensive operations. You don't need to do anything, but you can play around with the [experimental scheduler](https://github.com/drcmda/scheduler-test) and see if marking ops with a lesser priority makes a difference.

```jsx
import { useTransition } from 'react'
import { Points } from '@react-three/drei'

const [isPending, startTransition] = useTransition()
const [radius, setRadius] = useState(1)
const positions = calculatePositions(radius)
const colors = calculateColors(radius)
const sizes = calculateSizes(radius)

<Points
  positions={positions}
  colors={colors}
  sizes={sizes}
  onPointerOut={() => {
    startTransition(() => {
      setRadius(prev => prev + 1)
    })
  }}
>
  <meshBasicMaterial vertexColors />
</Points>
```

## Don't re-create objects in loops

Try to avoid creating too much effort for the garbage collector, re-pool objects when you can!

### ❌ Bad news for the GC

This creates a new vector 60 times a second, which allocates memory and forces the GC to eventually kick in.

```jsx
useFrame(() => {
  ref.current.position.lerp(new THREE.Vector3(x, y, z), 0.1)
})
```

### ✅ Better re-use object

Set up re-used objects in global or local space, now the GC will be silent.

```jsx
function Foo(props)
  const vec = new THREE.Vector()
  useFrame(() => {
    ref.current.position.lerp(vec.set(x, y, z), 0.1)
  })
```

## useLoader instead of plain loaders

Threejs loaders give you the ability to load async assets (models, textures, etc), but if you do not re-use assets it can quickly become problematic.

### ❌ No re-use is bad for perf

This re-fetches, re-parses for every component instance.

```jsx
function Component() {
  const [texture, set] = useState()
  useEffect(() => void new TextureLoader().load(url, set), [])
  return texture ? (
    <mesh>
      <sphereGeometry />
      <meshBasicMaterial map={texture} />
    </mesh>
  ) : null
}
```

Instead use useLoader, which caches assets and makes them available throughout the scene.

### ✅ Cache and re-use objects

```jsx
function Component() {
  const texture = useLoader(TextureLoader, url)
  return (
    <mesh>
      <sphereGeometry />
      <meshBasicMaterial map={texture} />
    </mesh>
  )
}
```

Regarding GLTF's try to use [GLTFJSX](https://github.com/pmndrs/gltfjsx) as much as you can, this will create immutable JSX graphs which allow you to even re-use full models.
