<template>
<v-app>
    
    <TheProfile />
    <TheMilestones />
     <TheCalendar />
    
    
</v-app>
</template>

<script>
import TheProfile from '@/components/TheProfile'
import TheCalendar from '@/components/TheCalendar'
import TheMilestones from '@/components/TheMilestones'

export default {
    components: {
        TheProfile,
        TheMilestones,
        TheCalendar,
    },
  }

</script>
<style scoped>
/* #contain {
    margin-top: 100px;
    padding-top: 50px;
    padding-right: 300px;
    margin-right: 200px;
    padding-bottom: 00px;
    display: flex;
    align-items: center;
    position: relative;

} */
</style>