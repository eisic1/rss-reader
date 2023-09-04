<template>
<div>
    <div :key="feed.id" v-for="feed in feeds">
      <Feed @delete-feed="$emit('delete-feed', feed.id)" :feed="feed" />
    </div>
</div>
</template>

<script>
    import Feed from './Feed.vue'

    export default {
        name: 'Feeds',
        props:{
            feeds: Array
        },
        components:{
            Feed
        },
        emits: ['delete-feed']
    }
</script>