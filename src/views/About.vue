<template>
<div class="row line">
  <div class="col-3 left">
    <div class="margin">
        <b-icon-grid1x2-fill class="icon_gap icon" />
        <p class="drop">All Feeds</p>
    </div>
    <div >
      <Feeds @delete-feed="deleteFeed" :feeds="feeds" />
    </div>
  </div>
  <div class="col-9 right">
    <div class="about">
      <p class="text">Welcome to the RSS Reader, a simple way to manage RSS feeds and read content. To begin using the RSS Reader, 
        add your first feed by clicking the button below.</p>
      <b-button class="add" @click="openModal" v-b-modal.urlModal  variant="primary" >+ADD FEED</b-button>
      <Modal @add-feed="addFeed" v-if="showModal" @close="closeModal" />
    </div>
  </div>
</div>
</template>

<script>
  import Modal from '../components/AddFeedModal.vue'
  import Feeds from '../components/Feeds.vue'

  export default{
    data() {
      return {
        showModal: false,
        feeds: []
      }
    },
    components:{
      Modal,
      Feeds
    },
    methods: {
      addFeed(feed){
        this.feeds = [...this.feeds, feed];
        this.showModal = false;
      },
      openModal(){
        this.showModal = true;
      },
      closeModal(){
        this.showModal = false;
      },
      deleteFeed(id){
        if(confirm('Are you sure?')){
          this.feeds = this.feeds.filter((feed) => feed.id !== id)
        }
      }
    },
    created(){
      this.feeds = [
        {
          id: 1,
          category: 'Youtube',
          children:[
            {
              title: 'Početna strana',
              url: 'https://www.youtube.com/'
            }
          ]
          
        },
        {
          id: 2,
          category: 'Facebook',
          children:[
            {
              title: 'Početna strana',
              url: 'https://www.facebook.com/'
            }
          ]
        },
        {
          id: 3,
          category: 'Google',
          children:[
            {
              title: 'Početna strana',
              url: 'https://www.google.com/'
            }
          ]
        }
      ]
    }
  }
</script>

<style scoped lang="scss">
.align{
  margin-top: 15px;
    text-align: left;
}
  .line{
    margin-top: 80px;
  }
  .text{
    font-size: 17px;
    color: white;
  }

  .add{
    padding: 5px 15px 5px 15px;
  }

  .about{
    padding: 10px;
  }

  .right{
    background-color: #333333;
  }

  .left{
    background-color: #4d4d4d;
    color: white;
    height: 100vh;
    border-right: 2px solid #4d4d4d;
    box-shadow: 0 0 10px 3px #4d4d4d;
  }
  .icon{
    font-size: 20px;
  }
  .drop{
    font-size: 20px;
    display: inline-block;
    margin-left: 15px;
  }
  .margin{
    margin-top: 10px;
    margin-left: 20px;
  }
</style>
