<template>
  <div class="player-wrapper">
    <!-- 播放器 -->
    <video id="player" preload="auto" playsinline webkit-playsinline></video>
  </div>
</template>

<script>
export default {
  name: 'HomeView',
  mounted() {
    const streamKey = this.$route.query.key || false
    this.streamKey = streamKey
    if (streamKey) {
      const liveSrc = `webrtc://6721.liveplay.myqcloud.com/live/${streamKey}`
      const player = TCPlayer('player')
      player.src(liveSrc)
    }
  }
}
</script>
<style scoped>
#player {
  width: 100vw;
  height: 100vh;
}
</style>
