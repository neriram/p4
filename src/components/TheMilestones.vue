<template>
<v-app id="layout">
  <v-container fluid>
    <v-data-iterator
      :items="items"
      :items-per-page.sync="itemsPerPage"
      hide-default-footer
    >
      <template v-slot:header>
        <v-toolbar
          class="mb-2"
          color="#fc6b03"
          dark
          flat
        >
          <v-toolbar-title>Chucky's Milestones</v-toolbar-title>
        </v-toolbar>
      </template>

      <template v-slot:default="props">
        <v-row>
          <v-col
            v-for="item in props.items"
            :key="item.name"
            cols="12"
            sm="6"
            md="4"
            lg="3"
          >
            <v-card>
              <v-card-title class="subheading font-weight-bold">{{ item.name }}</v-card-title>

              <v-divider></v-divider>

              <v-list dense>
                <v-list-item>
                  <v-list-item-content>Date:</v-list-item-content>
                  <v-list-item-content class="align-end">{{ item.date }}</v-list-item-content>
                </v-list-item>

                <v-list-item>
                  <v-list-item-content>Time:</v-list-item-content>
                  <v-list-item-content class="align-end">{{ item.time }}</v-list-item-content>
                </v-list-item>

                <v-list-item>
                  <v-list-item-content>Weight:</v-list-item-content>
                  <v-list-item-content class="align-end">{{ item.lbs }}</v-list-item-content>
                </v-list-item>

                <v-list-item>
                  <v-list-item-content>Length:</v-list-item-content>
                  <v-list-item-content class="align-end">{{ item.cm }}</v-list-item-content>
                </v-list-item>

                <v-list-item>
                  <v-list-item-content>Head Circumference:</v-list-item-content>
                  <v-list-item-content class="align-end">{{ item.cir }}</v-list-item-content>
                </v-list-item>

                <v-list-item>
                  <v-list-item-content>Hospital:</v-list-item-content>
                  <v-list-item-content class="align-end">{{ item.hospital }}</v-list-item-content>
                </v-list-item>

                <v-list-item>
                  <v-list-item-content>Doctor:</v-list-item-content>
                  <v-list-item-content class="align-end">{{ item.doc }}</v-list-item-content>
                </v-list-item>
              </v-list>
            </v-card>
          </v-col>
        </v-row>
      </template>

      <template v-slot:footer>
        <v-toolbar
          class="mt-2"
          color="#00BCD4"
          dark
          flat
        >
          <v-toolbar-title class="subheading">New Milestones</v-toolbar-title>
        </v-toolbar>
      </template>
    </v-data-iterator>
  </v-container>
</v-app>
</template>

<script>
  export default {
    data: () => ({
      itemsPerPage: 3,
      items: [
        {
          name: 'Birth Details',
          lbs: '6.2 oz',
          cm: 6.0,
          cir: 16,
          date: '11/18',
          time: '8:50',
          hospital: 'Swedish',
          doc: 'Dr. Harrison',
        },
        {
          name: '2 months',
        //   calories: 237,
        //   fat: 9.0,
        //   carbs: 37,
        //   protein: 4.3,
        //   sodium: 129,
        //   calcium: '8%',
        //   iron: '1%',
        },
        {
          name: '4 months',
        //   calories: 262,
        //   fat: 16.0,
        //   carbs: 23,
        //   protein: 6.0,
        //   sodium: 337,
        //   calcium: '6%',
        //   iron: '7%',
        },
      ],
    }),
  }
</script>
<style scoped>
#layout {
    margin-top: 100px
}
#header-top {
    background-color:#00BCD4
}
</style>