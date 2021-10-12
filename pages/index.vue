<template>
  <div>
    <div style="width: 70%; padding: 10px">
      <div class="contentContainer">

      </div>
    </div>
    <div style="width: 30%; padding: 10px">
      <div class="contentContainer">

      </div>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import axios from "axios"

export default {
  data() {
    return {
      videos: [],
    }
  },
  head() {
    return {
      title: "Manufacturer List",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Joeshop data"
        }
      ]
    };
  },
  async Receive() {
    const config = {
      headers: {
        'Accept': 'application/json'
      }
    }
    try {
      const res = await this.$axios.get('https://api.streamtape.com', config);
      console.log(res.data)
      this.videos = res.data;
    } catch (err) {
      console.log(err)
    }
  },
  methods: {},
};
</script>
