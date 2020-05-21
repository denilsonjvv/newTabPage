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
