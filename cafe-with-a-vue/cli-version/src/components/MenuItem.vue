<template>
    <div class="menu-item">
        <div>
            <h3>{{ name }}</h3>
            <img
            class="menu-item__image"
            v-bind:src="image.source"
            v-bind:alt="image.alt"
            />
            <p v-if="inStock">En stock</p>
            <p v-else>En rupture de stock</p>
            <div>
                <label for="add-item-quantity"
                    >Quantité : {{ quantity }}</label
                >
                <input
                    v-model.number="quantity"
                    id="add-item-quantity"
                    type="number"
                />
                <button @click="addToShoppingCart(quantity)">
                    Ajouter au panier d'achat
                </button>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "MenuItem",
        props: ["image", "quantity", "addToShoppingCart", "inStock", "name"]
    }
</script>