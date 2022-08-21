<script>
  import { ContactShadows } from '@threlte/extras'
  import Model from './lib/Model.svelte'
  import {
    Canvas,
		AmbientLight,
		PerspectiveCamera,
    SpotLight
	} from '@threlte/core'
</script>

<div class="canvas-wrapper">
  <Canvas>
    <AmbientLight color={0xffffff} intensity={2} />
    <SpotLight position={{x:1, y:6, z:1.5}} angle={0.2} penumbra={1} intensity={2.5} shadow shadow-mapSize={[2048, 2048]} />
      <SpotLight position={{x:-5, y:5, z:-1.5}} angle={0.03} penumbra={1} intensity={4} shadow shadow-mapSize={[1024, 1024]} />
      <SpotLight position={{x:5, y:5, z:-5}} angle={0.3} penumbra={1} intensity={4} shadow shadow-mapSize={[256, 256]} color="#ffffc0" />
    <PerspectiveCamera fov={50} position={{ x: 0, y:0, z: 1.1 }}>
    </PerspectiveCamera>
    <Model />
    <ContactShadows frames={1} rotation={{x:Math.PI / 2}} position={{x:0,y:0.33,z:0}} far={0.4} width={2} height={2} blur={4} />
 
  </Canvas>
</div>

<div class="content">
  <div class="left-div">
    THE SISTRUM
    <br />
    IS DESIGNED
    <br />
    TO REPRESENT
    <br />
    CONTINUAL
    <br />
    AGITATION.
    <div class="sub"></div>
  </div>
  <div class="right-div">
    <div class="jumbo">
      M1
    </div>
  </div>
</div>

<style>
  .content {
    position: absolute;
    width: 100%;
    height: 100%;
    margin: 0;
    padding: 0;
    display: grid;
    grid-template-columns: 1fr auto;
    align-items: start;
    font-family: 'ThunderBlack';
    font-size: 4em;
    line-height: 0.74em;
    color: #f7f4af;
  }

  .left-div {
    position: relative;
    display: grid;
    grid-template-rows: 1fr auto;
    width: 50%;
    height: 100%;
    padding: 100px;
    white-space: nowrap;
    font-family: 'ThunderThin';
    line-height: 1em;
  }
  .sub {
    align-self: end;
    width: 200px;
    height: 2px;
    background: #f7f4af;
  }

  .right-div {
    position: relative;
    display: flex;
    width: 100%;
    height: 100%;
    background: #f7f4af;
    color: #252525;
  }
  .jumbo {
    align-self: center;
    padding: 100px;
    font-size: 3.5em;
    color: #252525;
  }

   .canvas-wrapper {
    position: absolute;
	  top: 0;
	  left: 0;
	  width: 100%;
	  height: 100%;
    z-index: 1;
  }
</style>