<template>
    <div id="order">
        <div class="input-group mb-2">
            <div class="input-group-prepend">
                <label class="input-group-text" for="fishtype"><i class="fas fa-fish"></i> &nbsp; Fish Type</label>
            </div>
            <select  class="custom-select" id="fishtype">
                <option
                 v-for="post in posts"
                 :value="post.id">{{post.title}}
                 </option>               
            </select>
        </div>

        <div class="input-group">
            <div class="input-group-prepend">
                <label class="input-group-text" for="orderquantity"><i class="fas fa-weight-hanging"></i> &nbsp; &nbsp; Quantity</label>
            </div>
                            
            <select  class="custom-select" id="fishtype">
                <option
                 v-for="post in posts"
                 :value="post.id">{{post.quantity}}
                 </option>               
            </select>
                            
                            
        </div>

            <div class="text-right">
                <button class="btn mt-2" style="background: #16ADD6;"><i class="fas fa-shopping-basket text-white"></i> <span class="pl-2">Add to Cart</span></button>
            </div>
    </div>


</template>

<script>
    import {mapGetters} from 'vuex'

    export default {
        name: "Posts",
        mounted() {
            this.$store.dispatch('fetchPosts')
        },
        methods: {
            deletePost(post) {
                this.$store.dispatch('deletePost',post)
            }
        },
        computed: {
            ...mapGetters([
                'posts'
            ])
        }
    }
</script>

<style scoped>

</style>