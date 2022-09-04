<template>
    <div class="container">
        <div class="container__tabs">
            <button @click="CurentComponent = 'ComponentOne'">Tab 1</button>
            <button @click="CurentComponent = 'ComponentTwo'">Tab 2</button>
        </div>
        <Transition name="fade" mode="out-in">
            <component :is="CurentComponent"></component>
        </Transition>
    </div>
</template>

<script>
    import ComponentOne from "./ComponentOne.vue"
    import ComponentTwo from "./ComponentTwo.vue"
export default {
    name: "tabs",
    components: {
        ComponentOne,
        ComponentTwo
    },
    data() {
        return {
            CurentComponent: 'ComponentOne'
        }
    }

}
</script>

<style>
    * {
        box-sizing: border-box;
    }
    .container {
        max-width: 500px;
        min-height: 500px;
        margin: 0 auto;
    }
    .container__tabs {
        margin-bottom: 10px;
    }

    .component-one {
        background: url('https://autoiwc.ru/images/bmw/bmw-3.webp');
    }
    .component-two {
        background: url('https://www.mod-files.com/uploads/tuningfiles/0fe044a7f236bcf6683e1577566ac0__tuningtype_.jpg');
    }
    .component-one,
    .component-two {
        min-height: 281px;
        border-radius: 5px;
        background-size: cover;
        background-repeat: no-repeat;
    }

    .fade-enter-active,
    .fade-leave-active {
        transition: opacity 0.5s ease;
    }

    .fade-enter-from,
    .fade-leave-to {
        opacity: 0;
    }

</style>