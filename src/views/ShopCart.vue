<template>
    <div>
        <h1>Your cart</h1>

        <CartItemCard 
            v-for="product in products"
            :key="product.id"
            :product="product" />

        <CartSummaryPaymentCard />

    </div>
</template>

<script>
import CartItemCard from '../components/ShopCart/CartItemCard.vue';
import CartSummaryPaymentCard from '../components/ShopCart/CartSummaryPaymentCart.vue'




export default {
    computed: {
        products() {
            return this.$store.getters.cartItems;
        }
    },
    components: { CartItemCard, CartSummaryPaymentCard }
}
</script>