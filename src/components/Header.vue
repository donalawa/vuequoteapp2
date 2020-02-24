<template>
    <div class="row mb-5">
        <div class="col-sm-12">
            <h1>Beautiful Quotes</h1>
             <div class="progress">
            <div class="progress-bar" :style="{width: (quoteLength / max) * 100 + '%'}">
                    {{ quoteLength }} / {{ max }}
            </div>
        </div>
        </div>
       
    </div>
</template>

<script>
export default {
    props: ['max','quoteLength']
}
</script>

<style scoped>

</style>