
<template>
    <div class="card">
        <slot></slot>
    </div>
</template>

<script>
export default {
    
}
</script>


<style scoped>
.card {
    /* display: flex;
    flex-direction: column;
    margin: 20px;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 4px 3px 10px 2px #d4d4d4; */

    border-radius: 12px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
    padding: 1rem;
    margin: 2rem auto;
    max-width: 40rem;
}
</style>