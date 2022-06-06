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
    props: ['items'],
    computed: {
        totalPrice() {
            var total = 0;
                this.items.forEach(item => {
                    let splitted = item.price.split('$');
                    let singlePrice = parseFloat(splitted[1]);
                    // console.log(typeof total);
                    // console.log(typeof singlePrice);
                    total += singlePrice;
                })
                // console.log(total);
            }
    },
        // methods: {
        //     totalPrice() {
        //         let total = 0;
        //         this.items.forEach(item => {
        //             let price = item.price;
        //             let splitted = price.split('$');
        //             let singlePrice = parseFloat(splitted[1]);
        //             total = total + singlePrice;
        //             // console.log(typeof total);
        //             // console.log(typeof singlePrice);
        //             // console.log(typeof splitted[1]);
        //             // // console.log(typeof total);
                    
        //         })
                
        //         // console.log(typeof total);
        //         // console.log(typeof total);
        //         // return total;
        //     }
        // }
    }
</script>

<style>

</style>