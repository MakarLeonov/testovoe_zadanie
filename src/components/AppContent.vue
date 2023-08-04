<template>
    <section>
        <ProductCard v-for="(product, index) in products" :key="product.id" :product="product"/>
    </section>
</template>
<script>
import ProductCard from './productCard.vue';

export default {
    components: { ProductCard },
    data() {
        return {
            products: [
                {id: 1, brand: 'Бренд', name: 'Полное название товара в несколько строк для вида с обрывом в конце...', currentCost: '5 990', formerCost: '5 990', inStock: true},
                {id: 2, brand: 'Бренд', name: 'Полное название товара в несколько строк для вида с обрывом в конце...', currentCost: '5 990', formerCost: '5 990', inStock: true},
                {id: 3, brand: 'Бренд', name: 'Полное название товара в несколько строк для вида с обрывом в конце...', currentCost: '5 990', formerCost: '5 990', inStock: false},
                {id: 4, brand: 'Бренд', name: 'Полное название товара в несколько строк для вида с обрывом в конце...', currentCost: '5 990', formerCost: '5 990', inStock: true},
                {id: 5, brand: 'Бренд', name: 'Полное название товара в несколько строк для вида с обрывом в конце...', currentCost: '5 990', formerCost: '5 990', inStock: true},
                {id: 6, brand: 'Бренд', name: 'Полное название товара в несколько строк для вида с обрывом в конце...', currentCost: '5 990', formerCost: '5 990', inStock: true},
                {id: 7, brand: 'Бренд', name: 'Полное название товара в несколько строк для вида с обрывом в конце...', currentCost: '5 990', formerCost: '5 990', inStock: true},
                {id: 8, brand: 'Бренд', name: 'Полное название товара в несколько строк для вида с обрывом в конце...', currentCost: '5 990', formerCost: '5 990', inStock: true},
                {id: 9, brand: 'Бренд', name: 'Полное название товара в несколько строк для вида с обрывом в конце...', currentCost: '5 990', formerCost: '5 990', inStock: false},
                {id: 10, brand: 'Бренд', name: 'Полное название товара в несколько строк для вида с обрывом в конце...', currentCost: '5 990', formerCost: '5 990', inStock: false},
                {id: 11, brand: 'Бренд', name: 'Полное название товара в несколько строк для вида с обрывом в конце...', currentCost: '5 990', formerCost: '5 990', inStock: true},
                {id: 12, brand: 'Бренд', name: 'Полное название товара в несколько строк для вида с обрывом в конце...', currentCost: '5 990', formerCost: '5 990', inStock: true},
            ]
        }
    },
}
</script>
<style lang="scss" scoped>

section {
    flex-grow: 1;
    display: flex;
    gap: 24px;
    flex-wrap: wrap;
    padding-bottom: 100px;

}

@media (max-width: 1330px) {
    section {
        justify-content: space-between;
    }
}

@media (max-width: 800px) {
    section { 
        gap: 12px;
    }
}

    
</style>