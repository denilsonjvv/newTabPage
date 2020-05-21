<template>
  <div id="home">
    <div id="header">
      <Header/>
    </div>

    <div class="buttons">
      <div id="news">
        <News/>
      </div>

      <div id="codage_hacking">
        <Programming/>
      </div>

      <div id="lienUtilesAstuces">
        <usefullLink/>
      </div>

      <div id="rechercheEnquete">
        <Research/>
      </div>

      <div id="music">
        <Music/>
      </div>
    </div>

    <div id="app-videoLoop">
     <!--  <video id="videoLoop" autoplay loop muted >
       <source src="@/assets/ *** .mp4" type="video/mp4">
       Your browser does not support the video tag.
       </video> insert here your video but take care of your CPU usage, with htop, NetHogs etc. -->
     <img src="@/assets/insert-fresh-meme.jpg" width="100%" />
    </div>
  </div>
</template>

<script>
import header from "@/components/header"
import news from "@/components/news"
import programming from "@/components/programming"
import usefulllink from "@/components/usefulllink"
import research from "@/components/research"
import music from "@/components/music"

export default {
  name: 'Home',
  components: {
    Header : header,
    News : news,
    Programming: programming,
    UsefullLink: usefulllink,
    Research: research,
    Music: music

  }
}
</script>
