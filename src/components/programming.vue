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
