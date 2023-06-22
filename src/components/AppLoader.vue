<script>
export default {
    
}
</script>
<template lang="">
    <div>
        <div class="loaderGroup">
            <div>Pokévue loading. . .</div>
            <div class="loader">

            </div>
        </div>
    </div>
</template>
<style lang="scss" scoped>
    .loaderGroup{
        display: flex;
        flex-direction: column;
    }
    .loader{
        height: 80px;
        width: 80px;
        border-radius: 50%;
        border: 15px solid rgba(255, 255, 255, 0.7);
        border-top: 15px solid rgb(72, 72, 72);
        animation: spin 2s linear infinite;
        align-self: center;
        margin-top: 20px;
    }
    @keyframes spin{
        0% {transform: rotate(0deg)};
        100% {transform: rotate(360deg);}
    }
</style>