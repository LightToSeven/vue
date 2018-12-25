<template lang="html">
    <div class="list">

            <p>{{ phone.name }}</p>
            <p>{{ phone.tel }}</p>
    </div>
</template>
<script >
    export default{
        props:['phone']
    }
</script>
<style lang="css">

</style>