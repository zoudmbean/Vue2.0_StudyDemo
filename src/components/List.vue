<template>
    <div class="col-md-8">
        <h3 class="reply">评论回复：</h3>
        <h2 style='display: none'>暂无评论，点击左侧添加评论！！！</h2>
        <Item v-for="(comment,index) in comments" :key="index" :comment="comment" :index="index" :delComment="delComment"/>
    </div>
</template>

<script>
import Item from './Item.vue'
export default {
    props:['comments','delComment'],
    components : {
        Item
    }
}
</script>

<style>
    .reply {
        margin-top: 0px;
    }
</style>
