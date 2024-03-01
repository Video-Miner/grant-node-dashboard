<template> 
    <div class="row">
        <GradientCard title="Pool Commission" :statistic="commission" icon="tim-icons icon-coins" color="bg-c-primary" />
        <GradientCard title="Total Payouts" :statistic="totalPayouts" icon="tim-icons icon-money-coins" color="bg-c-secondary" />
        <GradientCard title="Go-Livepeer Version" :statistic="lpVersion" icon="tim-icons icon-tag" color="bg-c-tertiary" />
    </div>
</template>

<script>
import GradientCard from '@/components/Cards/GradientCard'
export default {
    name: 'poolStats',
    components: {
        GradientCard
    },
    computed: {
        commission() { return this.$store.state.status.commission * 100 + " %" },
        lpVersion() { return this.$store.state.status.lpVersion.split("-")[0] || process.env.VUE_APP_VERSION_BACKUP },
        totalPayouts() { 
            let tp = this.$store.state.status.totalPayouts;
            let output = "0.00 Ξ" ;
            if (tp)
                output = tp.substring(0, 5) + " Ξ" ;

            return output
         }
    }
}
</script>

<style>

</style>