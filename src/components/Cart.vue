<template>
     <ul class="list-group">
        <li class="list-group-item">
            Item - Price
        </li>

        <hr>

        <li v-for="(item, index) in items" :key="index" class="list-group-item">
            <span class="item-name">{{ item.title }}</span>
            <span class="item-price float-right">{{ item.price }}</span>
        </li>
        <hr>
        <li class="list-group-item">
            <span class="item-name">Total</span>
            <span class="item-price float-right">{{ totalPrice }}</span>
        </li>
    </ul>
</template>

<script>
export default {
    data() {
        return {
            total: 0,
            singlePrice: 0,
        }
    },
    props: ['items'],
    computed: {
        totalPrice() {
            this.items.forEach((item, index) => {
                let splitted = item.price.split('$');
                this.singlePrice = parseFloat(splitted[1]);
            })
            this.total += this.singlePrice;
            return this.total;
        }
    },
}
</script>

<style>

</style>