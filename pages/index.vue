<template>
  <div style="display: flex">
    <div style="width: 70%; padding: 10px">
      <div class="contentContainer">

      </div>
    </div>
    <div style="width: 30%; padding: 10px">
      <div class="contentContainer" style="background: #1c1c1c">

      </div>
    </div>
  </div>
</template>

<script>

export default {
  data() {
    return {
      shows: [],
    }
  },
  async created() {
    const config = {
      headers: {
        'Accept': 'application/json'
      }
    }
    try {
      const res = await this.$axios.get('https://api.videovard.sx/v2/api/folder/list?key=623qroxdsftzw5nijhi&fld_id=3336', config);
      console.log(res)
      // this.shows = res.data.result.folders
    } catch (err) {
      console.log(err)
    }
  }
}
</script>
