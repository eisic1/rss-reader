<template>
<div class="frame">
    <div v-if="feed.hasOwnProperty('category')" class="feed" @click="showItems">
        <b-icon-chevron-right class="icon" v-show="right" /><b-icon-chevron-double-down class="icon" v-show="down" /><p class="title"> {{ feed.category }}</p>
        <b-icon-trash-fill @click="deleteItem(feed.id)" class="basket" />
    </div>
    <div class="childrenFeed" v-else :style="{'margin-left': `${depth * 35}px`}">
        <a class="link" :href="feed.url">{{ feed.title }}</a>
    </div>
    <Feed 
        v-if="expanded"
        v-for="child in feed.children"
        :key="child.url"
        :feed="child"
        :depth="depth + 1"
    />
</div>
</template>

<script>
    export default {
        name: 'Feed',
        props:{
            feed: Object,
            depth: {
                type: Number,
                default: 0
            }
        },
        data(){
            return{
                expanded: false,
                right: true,
                down: false
            }
        },
        methods: {
            showItems(){
                this.expanded = !this.expanded;
                this.right = !this.right;
                this.down = !this.down;
            },
            deleteItem(id){
                this.$emit('delete-feed', id);
            }
        }
    }
</script>

<style scoped>
    p{
        margin: 0 auto 0 auto;
    }
    .title{
        display: inline-block;
    }
    .frame{
        margin-left: 20px;
    }
    .icon{
        margin-right: 15px;
    }
    .basket{
        float: right;
        margin-right: 20px;
    }
    .feed:hover, .childrenFeed:hover{
        background-color: #837c7c;
    }
    .feed, .childrenFeed{
        height: 20px;
    }
    .link{
        text-decoration: none;
        color: white;
    }
</style>