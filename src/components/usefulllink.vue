<template>
  <div class="dropdownMenu">
    <span class="title">Usefull links</span>

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
      {title: "DIY", link:'https://www.diy.fr/'},
      {title: "Archlinuxfr", link:'https://archlinux.fr/'},
      {title: "CamelCamelCamel (Amazon prices)", link:'https://fr.camelcamelcamel.com/?utm_campaign=locale_redir&utm_source=C:US-L:FR-G:FR&utm_medium=www'},
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
  color: #b896af;
  font-weight: 900;
  font-size: 2em;
  padding: 10px 10px 10px 10px;
  border-radius: 5px;
  box-shadow: 3px 3px 3px grey;
  z-index: 2;
  .title{
    font-size: 0.7em;
    //it s very ugly right now but it's normal, it's not responsiv!
  }
  .label{
    font-size: 0.5em;
    background-color: white;
    padding: 10px 5px 10px 5px;
    z-index: 0;
    a{
      color: #b896af;
    }
    &:hover {
      background-color: #b896af;
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
