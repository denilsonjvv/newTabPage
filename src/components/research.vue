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

