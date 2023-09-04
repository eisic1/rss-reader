<template>
 <!--   <div class="modal fade show" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true"> -->
    <!--    <transition>
            <div class="modal-mask">
                <div class="modal-wrapper">
                    <div class="modal-dialog">
                        <div class="modal-content">
                        <div class="modal-header">
                            <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
                            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                        </div>
                        <div class="modal-body">
                            ...
                        </div>
                        <div class="modal-footer">
                            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
                            <button type="button" class="btn btn-primary">Save changes</button>
                        </div>
                        </div>
                    </div>
                </div>
            </div>
        </transition> -->
  <!--  </div> -->
 <!-- <b-modal class="bg-secondary" centered id="urlModal" header-close-variant="dark" header-bg-variant="dark" header-text-variant="secondary"
   body-bg-variant="dark" body-text-variant="white" title="Add Feed" hide-footer  no-close-on-backdrop >
        <p class="my-4">Add the RSS URL for a feed below or the URL for the site</p>
        <div class="col-12 text-center">
            <b-button variant="primary" size="sm" class="mt-2 mr-2" @click="verifyPin">Continue</b-button>
            <b-button  variant="danger" size="sm" class="mt-2 ml-2" @click="hidePinModal">Cancel</b-button>
        </div>
    </b-modal> 
    <b-modal visible centered id="userModal" header="test" title="Confirm Approval" hide-footer hide-header-close no-close-on-backdrop no-close-on-esc>
                <div class="col-12 text-center">-->
                    <!--<p class="col-12">After being approved, the disbursement cannot be undone.</p>-->
             <!--   </div>
                <div class="col-12">
                    <div class="ml-5 mr-5">
                    <b-form-input  type="password" id="pin-input" v-model="pin"  required></b-form-input>
                    </div>
                </div>
                <div class="col-12 text-center">
                    <slot name="pin-error" class="text-danger text-center" v-show="comment">{{comment}}</slot>
                </div>
                <div class="col-12">
                </div>
                <div class="col-12 text-center">
                    <b-button variant="primary" size="sm" class="mt-2 mr-2" @click="verifyPin">Continue</b-button>
                    <b-button  variant="danger" size="sm" class="mt-2 ml-2" @click="hidePinModal">Cancel</b-button>
                </div>
            </b-modal> -->
            <div class="mask">
                <div class="wrapper">
                    <div class="container">
                        <div>
                            <p class="h4">Add Feed</p>
                        </div>
                        <div class="mt-4">
                            <p>Add the RSS URL for a feed below , or the URL for the site</p>
                            <p class="paragraph">CATEGORY</p>
                            <input type="text" v-model="category" class="inUrl" placeholder="Enter your category" />
                            <p class="paragraph">TITLE</p>
                            <input type="text" v-model="title" class="inUrl" placeholder="Enter your title" />
                            <p class="paragraph">URL</p>
                            <input type="text" v-model="url" class="inUrl" placeholder="Enter your URL" />
                        </div>
                        <div class="mt-3">
                            <b-button class="add" @click="addItem" variant="primary">ADD</b-button>
                            <b-button class="close" @click="$emit('close')">CLOSE</b-button>
                        </div>
                    </div>
                </div>
            </div>
</template>

<script>

    export default {
        name: 'Modal',
        data(){
            return{
                title: '',
                url: '',
                category: '',
                children: []
            }
        },
        props: {
            showModal: Boolean
        },
        methods: {
            addItem(){
                if(!this.title){
                    alert('Please enter a title');
                    return
                }

                const newChild = {
                    title: this.title,
                    url: this.url
                }

                this.children.push(newChild);

                const newFeed = {
                    id: Math.floor(Math.random() * 100000),
                    category: this.category,
                    children: this.children
                }

                this.$emit('add-feed', newFeed);

                this.title = '';
                this.url = '';
                this.children = [];
            }

        }
    }

</script>


<style scoped>
.mask{
    position: fixed;
    z-index: 9998;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.8);
    display: table;
    transition: opacity 0.3s ease;
}

.wrapper {
  display: table-cell;
  vertical-align: middle;
}

.container{
    width: 500px;
    margin: 0px auto;
    padding: 20px 30px;
    background-color: #2c2c2c;
    color: white;
    border-radius: 3px;
    box-shadow: 0 10px 10px  rgba(68, 65, 65, 0.33);
    transition: all 0.3s ease;
    font-family: Helvetica, Arial, sans-serif;
}

.add{
    padding: 5px 25px 5px 25px;
}

.close{
    outline: none;
    border: none;
    color: blueviolet;
    cursor: pointer;
    background-color: #2c2c2c;
    text-transform: none;
    margin-left: 5px;
}

.close:hover{
    background-color: #2c2c2c;
    color: blueviolet;
}

.inUrl{
    border: none;
        background: none;
        display: block;
        margin: 0 auto 5px auto;
        padding: 14px 10px;
        width: 100%;
        outline: none;
        color: white;
        border-bottom: 1px solid #6b6666;
}

.paragraph{
    margin: 0 auto 0 auto;
}
</style>