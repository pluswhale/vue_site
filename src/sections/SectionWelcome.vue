<template>
    <div id="section_1" class="section">
        <h1>Section 1</h1>
        <catalog/>
    </div>
</template>

<script>
import Catalog from "@/components/MiniComponents/Catalog/Catalog.vue";
    export default {
        components: {Catalog}
    }
</script>

<style lang="scss" scoped>

.section {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

</style>