<template>
    <div id="components" class="form">
        <span>Enter the keywords</span><br>
        <textarea v-model="keywords"></textarea><br>
        <span>Keywords : {{ keywords }}</span>
    </div>
</template>

<script>
export default {
    data() {
        return {
            keywords: {}
        }
    }
}
</script>


<style>
</style>