<template>
    <div class="row">
        <div v-for="(item, index) in items" :key="index" class="col-md-4">
            <div class="card">
                <img class="card-img-top" :src="item.photo" alt="Card image">
                <div class="card-body">
                    <h5 class="card-title">{{item.title}}</h5>
                    <p class="card-text">{{item.price}}</p>
                    <a @click="addToCart(item)" href="#" class="btn btn-primary">+ Add</a>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
    props: ['items'],
    methods: {
        addToCart(item) {
            this.$emit('newItemAdded', item);
            }
        }
    }
</script>

<style>

</style>