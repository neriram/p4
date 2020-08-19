<template>
<v-app>
    <TheMilestones />
    <TheCalendar />
</v-app>
</template>

<script>
import TheCalendar from '@/components/TheCalendar'
import TheMilestones from '@/components/TheMilestones'

export default {
    components: {
        TheMilestones,
        TheCalendar,
    },
  }

</script>