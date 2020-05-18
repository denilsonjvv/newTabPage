<template>
  <div class="dropdownMenu">
    <span class="title">programming</span>

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
      {title: "Vue-cli", link:'https://www.youtube.com/watch?v=KeFdy1kVH4A&list=PL4cUxeGkcC9iCKx06qSncuvEPZ7x1UnKD'},
      {title: "Firebase", link:'https://www.youtube.com/watch?v=aN1LnNq4z54&list=PL4cUxeGkcC9jUPIes_B8vRjn1_GaplOPQ'},
      {title: "Vuex", link:'https://www.youtube.com/watch?v=2uZYKcKHgU0&list=PL4cUxeGkcC9g0MQZfHwKcuB0Yswgb3gA5'},
      {title: "vue js", link:'https://www.youtube.com/watch?v=5LYrN_cAJoA&list=PL4cUxeGkcC9gQcYgjhBoeQH7wiAyZNrYa&index=1'},
      {title: "discord Vuejs", link:'https://discordapp.com/invite/HBherRA'},
      {title: "vue documentation", link:'https://vuejs.org/'},
    ],
  })
}
</script>

<style lang="scss" scoped>
.dropdownMenu{
  background-color: white;
  width: 5em;
  color: #759cb3;
  border-radius: 5px;
  overflow: hidden;
  box-shadow: 3px 3px 3px grey;
  font-weight: 900;
  font-size: 2em;
  padding: 10px 10px 10px 10px;
  z-index: 2;
  .title{
    font-size: 0.7em;

    //it s very ugly right now but it's normal, it's not responsiv!
  }
  &:hover {
    background-color: #759cb3;
    color: white;
    transition: 0.2s ease-out;
    box-shadow: 0 0 0;
  }
  .label{
    font-size: 0.5em;
    background-color: white;
    padding: 10px 5px 10px 5px;
    z-index: 0;
    a{
      color: #759cb3;
    }
    &:hover {
      background-color: #759cb3;
      a{
        color: white;
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
