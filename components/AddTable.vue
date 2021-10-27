<template>
  <button class="episbut" :value="video.linkid" @click="changeVid(video.linkid)">{{index+1}}</button>
</template>

<script>
export default {
  video: "video",
  indice: "index",
  props: ['video',"index"],
  data() {
    return {
    }
  },
  methods: {
    changeVid(id) {
      this.$emit('change-vid', id)
    }
  }
}
</script>
