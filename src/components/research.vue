<template>
  <div class="dropdownMenu">
    <span class="title">research</span>
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
      { title: "Youtube", link: `https://www.youtube.com/results?search_query=fuckfuckfuckfuckfuckfuckfuckfuckfuckfuckfuckfuckfuckfuckfuckfuckfuckfuckfuckfuckfuckfuckfuckfuckfuckfuckfuckfuckfuckfuckfuck`},
      { title: `Faits&Documents`, link:`https://faitsetdocuments.com/specimens-et-index.html` },
      { title: 'Sci-Hub', link:"https://mg.scihub.ltd/" },
      { title: 'LibGen', link:"https://libgen.bban.top/"},
      { title: 'Rutube', link:"https://rutube.ru/search/?query"},
      { title: 'Euronews', link:"https://www.youtube.com/watch?v=_tp8hj7dw8M"},
    ],
  })
}
</script>

<style lang="scss" scoped>
.dropdownMenu{
  background-color: white;
  color: #c59baf;
  width: 5em;
  border-radius: 5px;
  float: right;
  box-shadow:3px 3px 3px gray;
  font-weight: 900;
  font-size: 2em;
  padding: 10px 10px 10px 10px;
  z-index: 2;
  .title{
    font-size: 0.9em;
  }
  &:hover {
    background-color: #c59baf;
    color: white;
    transition: 0.2s ease-out;
    box-shadow: 0 0 0 gray;
  }
  .label{
    font-size: 0.5em;
    background-color: white;
    padding: 10px 10px 10px 10px;
    width: 15em;
    z-index: 0;
    a{
      color: #876776;
    }
    &:hover {
      background-color:  #876776;
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
