<template>
    <div class="card">
        <div class="card-body">

        </div>
    </div>
</template>


<script>
import { computed } from '@vue/reactivity';
import { Blog } from '../models/Blog.js'
export default {

    props: {
        blog: {type: Blog, required: true}
    },
    setup(props){
        return {
            imgUrl: computed(() => `url(${this.imgUrl})`)
        }
    }
}
</script>


<style lang="scss" scoped>

</style>