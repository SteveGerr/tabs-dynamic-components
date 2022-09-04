<template>
    <div class="container">
        <div class="container__tabs">
            <b-button-group>
                <b-button @click="CurentComponent = 'ComponentOne'" variant="success">Tab 1</b-button>
                <b-button @click="CurentComponent = 'ComponentTwo'" variant="info">Tab 2</b-button>
            </b-button-group>
        </div>
        <component :is="CurentComponent"></component>
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
    .container {
        max-width: 500px;
        margin: auto;
    }
    .container__tabs {
        margin-bottom: 10px;
    }

</style>