<template>
    <div class="component-container">
        <header class="header">
            <h2><span>Julien</span><br><span>Malassigne</span></h2>
            <h3>Developpeur web</h3>
            <h3>Full Stack</h3>
            <p>Ma phrase</p>
        </header>
        <button class="starting__button" @click.prevent="$emit('openNav')">Commencer la visite</button>
    </div>
</template>

<script>

export default {
    name: 'Home'
}
</script>

<style lang="scss" scoped>
.component-container {
    padding: 30px;
    height: 100%;
    width: 100%;
}

button {
    position: relative;
    bottom: -300px;
}
</style>
