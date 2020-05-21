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
