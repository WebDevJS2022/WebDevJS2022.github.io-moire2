<template>
    <li class="catalog__item">
        <a class="catalog__pic" href="#"
        @click.prevent="$emit('gotoPage', 'product', {id: product.id})">
            <img :src="product.image" :alt="product.title">
        </a>

        <h3 class="catalog__title">
            <a href="#">
                {{ product.title }}
            </a>
        </h3>

        <span class="catalog__price">
            {{ product.price }} ₽
        </span>

        <ul class="colors colors--black">
            <li class="colors__item" v-for="color in product.colors" :key="color.id">
                <label class="colors__label" for="input1">
                    <input aria-labelledby="#input1" id="input1"
                    class="colors__radio sr-only" type="radio"
                    v-for="color in product.colors" :key="color.id"
                        :value="color.id">
                    <span class="colors__value" :style="{'background-color': color.code}">
                    </span>
                </label>
            </li>
        </ul>
    </li>
</template>

<script>

export default {
  name: 'ProductItem',
  props: ['product'],
};
</script>
