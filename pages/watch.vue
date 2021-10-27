<template>
  <div style="display: flex">
    <div style="width: 70%; padding: 10px">
      <div class="contentContainer">
        <iframe id="player" allow="autoplay" allowfullscreen="allowfullscreen" allowtransparency="" frameborder="0"
                height="600px" scrolling="no" src="https://streamtape.com/e/rxo0mLxVPlTbbgb/" width="100%"></iframe>

        <div style="background: #1c1c1c; padding: 10px; border-radius: 8px; margin-top: 5px;">
          <div style="float: right">
            <button class="hostbut"> Videovard</button>
            <button class="hostbut"> Streamtape</button>
          </div>

          <div style="display: inline-table;width: 100%">
            <AddTable v-for="(video,index ) in videos" :key="video.id" :index="index" :video="video"
                      @change-vid="changeVid"/>
          </div>

        </div>
      </div>
    </div>
    <div style="width: 30%; padding: 10px">
      <div class="contentContainer" style="background: #1c1c1c">
      </div>
    </div>
  </div>
</template>

<script>
import AddTable from "../components/AddTable"

export default {
  components: {
    AddTable
  },
  data() {
    return {
      videos: [],
    }
  },
  async created() {
    const config = {
      headers: {
        'Accept': 'application/json'
      }
    }
    try {
      const res = await this.$axios.get('https://api.streamtape.com/file/listfolder?login=95f997da4f7076b742c9&key=OaxeDLWr24HZvOk&folder=QmBRBdDd4Io', config);
      this.videos = res.data.result.files
    } catch (err) {
      console.log(err)
    }
  },
  methods: {
    changeVid(id) {
      document.getElementById("player").src = "https://streamtape.com/e/" + id + "/"
    },
    async videoVard() {
      const config = {
        headers: {
          'Accept': 'application/json'
        }
      }
      try {
        const res = await this.$axios.get('https://api.videovard.sx/v2/api/file/list?key=623qroxdsftzw5nijhi&fld_id=mljkf9oaml', config);
        this.videos = res.data.result.files
      } catch (err) {
        console.log(err)
      }
    },

  },
};
</script>
