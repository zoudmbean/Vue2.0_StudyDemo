<template>
    <div id="app">
        <div>
            <header class="site-header jumbotron">
                <div class="container">
                    <div class="row">
                    <div class="col-xs-12">
                        <h1>请发表对React的评论</h1>
                    </div>
                    </div>
                </div>
            </header>
            <div class="container">
                <Add :addComment="addComment"/>
                <List :comments="comments" :delComment="delComment"/>
                
            </div>
        </div>
    </div>
</template>

<script>
import List from './components/List.vue'
import Add from './components/Add.vue'
export default {
    data() {
        return {
            comments : [
                {
                    name:'Bob',
                    content:'Vue很好用'
                },
                {
                    name:'Marry',
                    content:'今天天气不错哦！'
                },
                {
                    name:'Jack',
                    content:'Fuck，下雨了。'
                },
                {
                    name:'Cat',
                    content:'我的食物到了。。。'
                }
            ]
        }
    },
    components : {
        List,Add
    },
    methods:{
        addComment(comment){
            this.comments.unshift(comment);
        },
        delComment(index){
            this.comments.splice(index,1);
        }
    }
}
</script>

<style>
    

    

    

    

    

    .user {
    font-size: 22px;
    }
</style>
