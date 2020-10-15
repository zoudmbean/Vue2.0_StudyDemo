<template>
    <ul class="list-group">
        <li class="list-group-item">
            <div class="handle">
                <a href="#" @click.prevent="delItem">删除</a>
            </div>
            <p class="user"><span >{{comment.name}}</span><span>说:</span></p>
            <p class="centence">{{comment.content}}</p>
        </li>
    </ul>
</template>

<script>
export default {
    props:{ // 指定属性名和属性值的类型
        comment : Object,
        delComment:{
            type:Function
        },
        index:{
            type:Number
        }
    },
    methods:{
        delItem(){
            if(window.confirm(`您确认要删除 ${this.comment.name} 的评论吗？`)){
                this.delComment(this.index);
            }
        }
    }
}
</script>

<style>
    li {
        transition: .5s;
        overflow: hidden;
    }
    .list-group-item .centence {
        padding: 0px 50px;
    }
    .handle {
        width: 40px;
        border: 1px solid #ccc;
        background: #fff;
        position: absolute;
        right: 10px;
        top: 1px;
        text-align: center;
    }
    .handle a {
        display: block;
        text-decoration: none;
        cursor: pointer;
    }
</style>
