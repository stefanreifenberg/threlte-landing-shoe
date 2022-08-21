<script>
    import { GLTF } from '@threlte/extras'
    import { useFrame } from '@threlte/core'

    let t
    useFrame(({clock})=> {
        t = clock.getElapsedTime()
    })
</script>

<GLTF castShadow
    receiveShadow
    url={'/shoe-draco.glb'}
    position={{ x:0, y:(0.1 + Math.sin(t / 2)) / 10, z:-0.22 }}
    rotation={{x:0.1 + Math.cos(t / 4.5) / 10, y:Math.sin(t / 4) / 4, z:0.3 - (1 + Math.sin(t / 4)) / 8}}
    scale={0.225}
    useDraco
/>