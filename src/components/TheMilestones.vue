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
          <v-toolbar-title>Chucky's Physical Milestones</v-toolbar-title>
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
          <v-toolbar-title class="subheading">Chucky's Developmental Milestones</v-toolbar-title>
        </v-toolbar>
      </template>
    </v-data-iterator>
  </v-container>
</v-app>
</template>

<script>
  export default {
    data: () => ({
      itemsPerPage: 4,
      items: [
        {
          name: 'Birth Details',
          lbs: '6.2 oz',
          cm: 15.0,
          cir: 11,
          date: '11/18',
          time: '8:50 pm',
          hospital: 'Swedish',
          doc: 'Dr. Harrison',
        },
        {
          name: '2 months',
          lbs: '8.4 oz',
          cm: 6.0,
          cir: 13,
          date: '1/18',
          time: '11:00',
          hospital: 'PacMed',
          doc: 'Dr. Patel',
        },
        {
          name: '4 months',
          lbs: '6.2 oz',
          cm: 6.0,
          cir: 14,
          date: '3/18',
          time: '8:30',
          hospital: 'PacMed',
          doc: 'Dr. Patel',
        },
        {
          name: '6 months',
          lbs: '6.2 oz',
          cm: 6.0,
          cir: 18,
          date: '5/18',
          time: '10:00',
          hospital: 'PacMed',
          doc: 'Dr. Patel',
        },
      ],
    }),
  }
</script>
<style scoped>
#layout {
    margin-top: 10px
}
#header-top {
    background-color:#00BCD4
}
</style>