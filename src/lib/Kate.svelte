<script>
    import { GLTF } from '@threlte/extras'
    import { useFrame } from '@threlte/core'

    let t
    let rotation = 0;
    useFrame(({clock})=> {
        t = clock.getElapsedTime()
        rotation += 0.01;
    })
</script>

<GLTF castShadow
    receiveShadow
    url={'/sokate_left.glb'}
    position={{ x:0, y:(-5 + Math.sin(t / 2)) / 10, z:-3 }}
    rotation={{x:0.1 + Math.cos(t / 4.5) / 10, y:-8 + Math.sin(t / 4) / 4, z:0.3 - (1 + Math.sin(t / 4)) / 8}}
    scale={0.1}
    useDraco
/>