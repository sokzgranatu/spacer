<template>
<div class="claimWrapper">
    <h1 class="claim">SPACER</h1>
    <p class="subclaim">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Lorem, ipsum.</p>
    <p class="subclaim">Lorem ipsum dolor sit amet consectetur adipisicing.</p>
</div>
</template>

<script>
export default {
  name: 'Claim',
};
</script>

<style lang="scss" scoped>
    .claimWrapper{
        display: flex;
        text-align: center;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        color: white;
    }

    .claim{
        font-size: 50px;
        margin: 0;
    @media (min-width: 768px){
        font-size: 80px;
    }
    }
    .subclaim{
        margin: 20px 0 0 0;
        font-size: 13px;
        @media (min-width: 768px){
            font-size: 17px;
            letter-spacing: 1px;
            line-height: 1px;
        }
    }
</style>
