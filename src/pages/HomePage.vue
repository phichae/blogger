<template>
  <div>
    <p>{{ blogs }}</p>
    <BlogCard/>
  </div>
</template>

<script>
import { onMounted } from 'vue';
import Pop from '../utils/Pop.js';
import { blogsService } from '../services/BlogsService.js'
import { computed } from '@vue/reactivity';
import { AppState } from '../AppState.js';
import BlogCard from '../components/BlogCard.vue';

export default {
    setup() {
        async function getBlogs() {
            try {
                await blogsService.getBlogs();
            }
            catch (error) {
                Pop.error(error);
            }
        }
        onMounted(() => {
            getBlogs();
        });
        return {
            blogs: computed(() => AppState.blogs)
        };
    },
    components: { BlogCard }
}
</script>

<style scoped lang="scss">
.home {
  display: grid;
  height: 80vh;
  place-content: center;
  text-align: center;
  user-select: none;

  .home-card {
    width: 50vw;

    >img {
      height: 200px;
      max-width: 200px;
      width: 100%;
      object-fit: contain;
      object-position: center;
    }
  }
}
</style>
