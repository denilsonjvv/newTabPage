<template>
  <div class="dropdownMenu">
    <span class="title">music</span>
    <div class="menu">
      <div v-for="item in items" :key="item.title">
          <div class="label">
            <a v-bind:href="item.link">{{item.title}} </a>
          </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data: () => ({
    items: [
      { title: "macross", link: `https://macross82-99.bandcamp.com/music`},
      { title: `yung bae`, link:`https://yungbaebae.bandcamp.com/` },
      { title: 'night tempo', link:`https://nighttempo.bandcamp.com/` },
      { title: 'trevor something', link:"https://trevorsomething.bandcamp.com/"},
    ],
  })
}
</script>

<style lang="scss" scoped>
.dropdownMenu{
  background-color: white;
  color: #bda0cb;
  width: 5em;
  padding: 10px 10px 10px 10px;
  border-radius: 5px;
  float: left;
  box-shadow:3px 3px 3px gray;
  font-weight: 900;
  font-size: 2em;
  z-index: 2;
  overflow: hidden;
  .title{
    font-size: 1em;
  }
  &:hover {
    background-color: #bda0cb;
    color: white;
    transition: 0.2s ease-out;
    box-shadow:0 0 0 gray;
  }
  .label{
    font-size: 0.5em;
    background-color: white;
    padding: 10px 5px 10px 5px;
    width: 15em;
    z-index: 0;
    a{
      color: #776580;
    }
    &:hover {
      background-color: #bda0cb;
      a{
        color:white;
      }
    }
  }
  .menu{
    position: absolute;
    opacity: 0;
    transform: translateY(-50px);
    background-color: white;
    margin: auto;
    width: 150px;
    list-style: none;
    pointer-events: none;
    transition: 0.2s ease-out;
    z-index: 0;
  }
  &:hover {
    > .menu{
      opacity: 1;
      pointer-events: all;
      transform: translateY(0);
      z-index: 0;
    }
  }
}
</style>
