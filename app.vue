<script setup lang="ts">
import { OrbitControls, GLTFModel } from '@tresjs/cientos'
</script>
<template>
<div style="height: 500px; width: 500px;">
    <TresCanvas shadows alpha>
      <TresPerspectiveCamera :position="[5, 5, 5]" minZoom="1" :args="[45, 1, 0.1, 1000]"/>
      <OrbitControls auto-rotate :enable-zoom="false" :enable-damping="true" :enable-pan="false"/>
      <Suspense>
        <GLTFModel path="/scene.gltf" ref="modelRef" />
        
      </Suspense>
      <TresDirectionalLight :position="[5, 5, 5]" :intensity="5" cast-shadow />
      <TresDirectionalLight :position="[-5, 5, -5]" :intensity="5" cast-shadow />
    </TresCanvas>
</div>
</template>