<template>
  <div class="gameObject"/>
</template>

<style scoped>
.gameObject {
  position: absolute;

  left: v-bind("positionCss.left");
  bottom: v-bind("positionCss.top");

  height: v-bind("positionCss.height");
  width: v-bind("positionCss.width");

  transform: translate(v-bind("positionCss.translation"));

  transform-origin: left;

  rotate: v-bind("positionCss.rotation");

  border-radius: 100%;

  background-repeat: no-repeat;
  background-size: contain;
  background-position: center;

  z-index: v-bind("positionCss.elevation");
}
</style>

<script setup>
const props = defineProps(["data", "resolution"])

let rotation = 0
let translation = "-50%, 50%"
let elevation = 20

if(props.data.rotation && props.data.type == "Explosion"){
    translation = "-50%, 0%"
    rotation = (180 - props.data.rotation) + "deg"
    elevation = 10
}

const positionCss = computed(() => ({
  left: `${props.data.center.x * props.resolution}rem`,
  top: `${props.data.center.y * props.resolution}rem`,

  height: `${2*props.data.radius * props.resolution}rem`,
  width: `${2*props.data.radius * props.resolution}rem`,

  rotation,
  translation,
  elevation
}));
</script>
