<template>
  <Renderer ref="renderer" antialias :orbit-ctrl="{ enableDamping: true }" resize="window">
    <Camera :position="{ z: 10 }" />
    <Scene>
      <PointLight :position="{ y: 50, z: 50 }" />
      <Box ref="box" :rotation="{ y: Math.PI / 4, z: Math.PI / 4 }">
        <PhysicalMaterial color="#ffffff" />
      </Box>
    </Scene>
  </Renderer>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import { Box, Camera, PhysicalMaterial, MeshPublicInterface, PointLight, Renderer, RendererPublicInterface, Scene } from 'troisjs'

export default defineComponent({
  components: { Box, Camera, PhysicalMaterial, PointLight, Renderer, Scene },
  mounted() {
    const renderer = this.$refs.renderer as RendererPublicInterface
    renderer.three.setSize(640, 480)
    const box = this.$refs.box as MeshPublicInterface
    if (renderer && box) {
      renderer.onBeforeRender(() => {
        box.mesh.rotation.x += 0.01
      })
    }
  },
})
</script>
