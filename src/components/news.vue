<template>
  <div class="dropdownMenu">
    <span class="title">News</span>

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
      { title: "Reddit", link: `https://www.reddit.com/`},
      { title: 'The Verge', link:"https://www.theverge.com/" },
      { title: 'whatever you want', link:"https://www.google.com/?hl=us"},
      { title: 'whatever you want again', link:"https://www.google.com/?hl=us"},
      { title: 'whatever you want again again', link:"https://www.google.com/?hl=us"},
    ],
  })
}
</script>

<style lang="scss" scoped>
.dropdownMenu{
  background-color: white;
  color: #73a2a0;
  width: 5em;
  font-weight: 900;
  font-size: 2em;
  padding: 10px 10px 10px 10px;
  z-index: 1;
  overflow: hidden;
  border-radius: 5px;
  box-shadow:3px 3px 3px gray;
  .title{
    font-size: 0.9em;
  }
  &:hover {
    background-color: #73a2a0;
    color: white;
    transition: 0.2s ease-out;
    box-shadow: 0 0 0 gray;
  }
  .label{
    font-size: 0.5em;
    background-color: white;
    padding: 10px 5px 10px 5px;
    z-index: 0;
    a{
      color: #73a2a0;
      z-index: 0;
    }
    &:hover {
      background-color: #73a2a0;
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
