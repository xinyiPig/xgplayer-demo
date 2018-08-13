<template>
  <div id="vs"></div>
</template>
<script>

import Player from 'xgplayer'
import 'xgplayer-mp4'
const URL = '../../static'
export default {
  data () {
    return {
      url: URL + '/xgplayer-demo-360p.mp4'
    }
  },
  mounted () {
    let player = new Player({
      id: 'vs',
      autoplay: true,
      volume: 0.3,
      url: this.url,
      poster: '//s2.pstatp.com/cdn/expire-1-M/byted-player-videos/1.0.0/poster.jpg',
      playsinline: true,
      thumbnail: {
        pic_num: 44,
        width: 160,
        height: 90,
        col: 10,
        row: 10,
        urls: ['//s3.pstatp.com/cdn/expire-1-M/byted-player-videos/1.0.0/xgplayer-demo-thumbnail.jpg']
      },
      bullet: {
        switch: 'on',
        url: '//s0.pstatp.com/cdn/expire-1-M/byted-player-videos/1.0.0/danmu.json',
        method: 'get'
      },
      height: window.innerHeight,
      width: window.innerWidth,
      whitelist: ['']
    })
    player.emit('resourceReady', [{ name: '超清', url: URL + '/xgplayer-demo-720p.mp4' }, { name: '高清', url: URL + '/xgplayer-demo-480p.mp4' }, { name: '标清', url: URL + '/xgplayer-demo-360p.mp4' }])
  }
}
</script>
<style scoped>
#vs{
  width: 100px
  ;
  height: 100px;
}
</style>
