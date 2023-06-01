<template>
        <div @click="setActive" class="row justify-content-center">
            <div class="card col-10">
                <div class="card-body">
                    <section class="row justify-content-between ">
                        <div class="col-4">
                            <img class="img-fluid" :src="blog.imgUrl" :alt="blog.title">
                        </div>
                        <div class="col-7">
                            <h1>{{ blog.title }}</h1>
                            <p>{{ blog.creator.name }}</p>
                        </div>
                    </section>
                </div>
            </div>
        </div>
</template>


<script>
import { AppState } from '../AppState.js';
import { Blog } from '../models/Blog.js'
import { logger } from '../utils/Logger.js';
export default {

    props: {
        blog: {type: Blog, required: true}
    },
    setup(props){
        return {
            // setActive() {
            //     AppState.activeBlog = props.blog
            //     logger.log(AppState.activeBlog)
            // }
        }
    }
}
</script>


<style lang="scss" scoped>

</style>