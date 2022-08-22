<script>
  import { ContactShadows } from '@threlte/extras'
  import { fade } from 'svelte/transition';
  import Model from './lib/Model.svelte'
  import Kate from './lib/Kate.svelte'
  import {
    Canvas,
		AmbientLight,
		PerspectiveCamera,
    SpotLight
	} from '@threlte/core'

  let kate = false;
  function handleClick() {
    kate = !kate;
	}

</script>

{#if kate}
<div class="canvas-wrapper" transition:fade>
  <Canvas>
    <AmbientLight color={0xffffff} intensity={2} />
    <SpotLight position={{x:1, y:6, z:1.5}} angle={0.2} penumbra={1} intensity={2.5} shadow shadow-mapSize={[2048, 2048]} />
      <SpotLight position={{x:-5, y:5, z:-1.5}} angle={0.03} penumbra={1} intensity={4} shadow shadow-mapSize={[1024, 1024]} />
      <SpotLight position={{x:5, y:5, z:-5}} angle={0.3} penumbra={1} intensity={4} shadow shadow-mapSize={[256, 256]} color="#FF3820" />
    <PerspectiveCamera fov={50} position={{ x: 0, y:0, z: 1.1 }}>
    </PerspectiveCamera>
    <Kate />
    <ContactShadows frames={1} rotation={{x:Math.PI / 2}} position={{x:0,y:0.33,z:0}} far={0.4} width={2} height={2} blur={4} />
  </Canvas>
</div>

<div class="content-kate" transition:fade>
  <div class="left-div">
    THE SO KATE
    <br />
    IS ONE OF THE
    <br />
    MOST ICONIC 
    <br />
    SHOES OF ALL 
    <br />
    CHRISTIAN LOUBOUTIN 
    <br />
    DESIGNS.
    <div class="sub-kate" transition:fade></div>
  </div>
  <div class="right-div-kate" transition:fade>
    <div class="jumbo-kate" transition:fade>
      SO 
      <br />
      <br />
      KATE
    </div>
  </div>
</div>
<button on:click={handleClick} class="button-kate">
</button>
{:else}
<div class="canvas-wrapper" transition:fade>
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

<div class="content-m1" transition:fade>
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
    <div class="sub-m1"></div>
  </div>
  <div class="right-div-m1" transition:fade>
    <div class="jumbo-m1">
      M1
    </div>
  </div>
</div>
<button on:click={handleClick} class="button-m1">
</button>
{/if}



<style>
  .button-kate {
    position: absolute;
    z-index: 2;
    top: 85%;
    left: 50%;
    background-color: #f7f4af;
    color: white;
    border: none;
    padding: 5px;
    font-size: 31px;
    height: 50px;
    width: 50px;
    cursor: pointer;
    border-radius: 70%;
  }
  .button-m1 {
    position: absolute;
    z-index: 2;
    top: 85%;
    left: 50%;
    background-color: #FF3820;
    color: white;
    border: none;
    padding: 5px;
    font-size: 31px;
    height: 50px;
    width: 50px;
    cursor: pointer;
    border-radius: 70%;
  }

  .content-kate {
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
    color: #FF3820;
  }
  @media (max-width: 425px) {
    .content-kate {
      grid-template-columns: 1fr;
    }
  }
  .content-m1 {
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
  @media (max-width: 425px) {
    .content-m1 {
      grid-template-columns: 1fr;
    }
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

  /* add meria query to left-div*/
  @media (max-width: 768px) {
    .left-div {
      padding: 50px;
    }
  }

  .sub-kate {
    align-self: end;
    width: 200px;
    height: 2px;
    background: #FF3820;
  }

  .sub-m1 {
    align-self: end;
    width: 200px;
    height: 2px;
    background: #f7f4af;
  }

  .right-div-kate {
    position: relative;
    display: flex;
    width: 100%;
    height: 100%;
    background: #FF3820;
    color: #252525;
  }

  .right-div-m1 {
    position: relative;
    display: flex;
    width: 100%;
    height: 100%;
    background: #f7f4af;
    color: #252525;
  }

  .jumbo-m1 {
    align-self: center;
    padding: 100px;
    font-size: 3.5em;
    color: #252525;
  }
  .jumbo-kate {
    align-self: center;
    padding: 100px;
    font-size: 1.8em;
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