<template>
  <HomeSection>
    <template #title>
      <Edit3Icon />Posts
    </template>

    <div class="columns is-multiline">
      <div v-for="post in posts" :key="post.link" class="column is-half">
        <PostCard :post="post" />
      </div>
    </div>

    <SaikaLink to="/posts" class="view-all"
      >View all <ChevronRightIcon
    /></SaikaLink>
  </HomeSection>
</template>

<script>
import { Edit3Icon, ChevronRightIcon } from 'vue-feather-icons'
import PostCard from './PostCard.vue'
import HomeSection from './HomeSection.vue'

export default {
  components: {
    Edit3Icon,
    ChevronRightIcon,
    PostCard,
    HomeSection
  },

  props: {
    posts: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>
.view-all {
  display: inline-flex;
  align-items: center;

  & svg {
    width: 1rem;
    height: 1rem;
  }
}
</style>
