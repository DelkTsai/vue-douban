<template>
    <div class="find">
        <h1>{{finds.title}}</h1>
        <vue-carousel>
            <li v-for="find in finds.items" :key="find.id" :style="{borderColor: find.color}">
                <a :style="{color: find.color}" @click="toClass(find.tag)">{{find.name}}</a>
            </li>
        </vue-carousel>
    </div>
</template>

<script>
    import VueCarousel from './vue-carousel.vue'

    export default {
        props: ['finds'],
        data() {
            return {

            }
        },
        methods: {
            toClass(tag) {
                this.$emit('toClass', tag);
            }
        },
        components: {
            VueCarousel
        }
    }
</script>

<style lang="less">
.find {
    ul {
        padding: 15px 0 30px 0;
        height: 121px;
        width: 1300px;
        display: flex;
        flex-wrap: wrap;
        li {
            flex-shrink: 0;
            margin: 0 8px 8px 0;
            padding: 0 25px;
            border-radius: 5px;
            border: 1px solid;
            height: 50px;
            line-height: 50px;
            letter-spacing: .1rme;
            overflow: auto;
            text-align: center;
            font-size: 1.7rem;
        }
    }
}
</style>
