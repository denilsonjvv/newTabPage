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
<style lang="scss">
#home{
  width: 50vw;
  text-align: center;
  margin: 0 auto;
  #header{
    width: 100%;
    height: 130px;
    justify-content: center;
    box-shadow:5px 5px 5px gray,
    -2px -2px 2px white;
    border-radius: 10px;

    overflow: hidden;
  }
  .buttons{
    width: 100%;
    padding-top: 30px;

    display: grid;
    grid-template-columns: repeat(12, 1fr);
    grid-gap: 10px;
    grid-auto-rows: minmax(8vh, auto);
  }
  #news{
    grid-column: 1/5;
    grid-row: 1;
  }
  #codage_hacking{
    grid-column: 5/9;
    grid-row: 1;
  }
  #lienUtilesAstuces{
    grid-column: 9/13;
    grid-row: 1;
  }
  #rechercheEnquete{
    grid-column: 1/7;
    grid-row: 2;
  }
  #music{
    grid-column: 7/13;
    grid-row: 2;
  }
  #app-videoLoop{
    background-color: transparent;
    pointer-events: none;
    #videoLoop{
      margin-top: 10px;
      width: 35vw;
    }
  }
}
</style>
