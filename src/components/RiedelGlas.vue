<script setup>

</script>

<template>
    <p>Rosévinen bliver serveret i et specialdesignet Rosévinglas fra Riedel kaldet “Vinum Extreme Rose”. Glassets design er skabt til at efterkomme efterspørgslen på rosévin og er fundamentalt anderledes end andre vinglas. 
    Dette kommer til udtryk i:</p>

   <section class="flex_container">
        <div class="pink_box">
            <i class="wine_symbol fa-solid fa-wine-glass fa-2xl" style="color: #e05254;"></i>
            <p class="glas_p">Et diamantformet roséglas som gør det til det perfekte valg til at fuldende smagsoplevelsen</p>
        </div>
        <div class="pink_box">
            <i class="wine_symbol fa-solid fa-wine-glass fa-2xl" style="color: #e05254;"></i>
            <p class="glas_p">Formen på glasset dirigerer strømmen af vin til spidsen af tungen, som introducerer vinens fulde smagsoplevelse</p>
        </div>
        <div class="pink_box">
            <i class="wine_symbol fa-solid fa-wine-glass fa-2xl" style="color: #e05254;"></i>
            <p class="glas_p">Designet på glasset giver vinen rig mulighed for at få luft og udvikle velsmagende aromaer</p>
        </div>
        <div class="pink_box">
            <i class="wine_symbol fa-solid fa-wine-glass fa-2xl" style="color: #e05254;"></i>
            <p class="glas_p">Glassets runding og indsnævring i toppen skaber en stor fordampningsflade, der intensiverer vinens aroma</p>
        </div>
    </section>

    <p>Derudover er glasset særligt velegnet til “New World” vine, som bringer de bløde frugtige noter frem. 
    Glasset har en værdi af 195kr!

    Vil du også afprøve Riedelglasset og oplevelse en helt fantastisk smagsoplevelse? 
    Så køb billet til Rosé Festival Odense 2024 lige her. </p>

    <div class="btn blue glas_btn">KØB BILLET</div>
</template>

<style scoped>
    .flex_container {
        display: flex;
        flex-flow: row wrap;
        width: 100%;
        justify-content: center;
    }

    .pink_box {
        background-color: #FCE9E6;
        width: 150px;
        height: 265px;
        margin: 20px;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .glas_p {
        text-align: center;
    }

    .glas_btn {
        margin: 30px auto 0 20px;
    }

    .wine_symbol {
        margin: 30px 0 20px 0;
    }

    @media screen and (min-width: 601px) {
        .pink_box {
            height: 295px;
        }
    }

    @media only screen and (min-width: 960px) {
        .pink_box {
            height: 190px;
            width: 250px;
        }
    }
</style>