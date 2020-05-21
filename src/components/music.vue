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

