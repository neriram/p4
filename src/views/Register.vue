<template>
<v-app id="reg">
  <v-card flat>
    <v-snackbar
      v-model="snackbar"
      absolute
      top
      right
      color="success"
    >
    
      <span>Registration successful!</span>
      <v-icon dark>mdi-checkbox-marked-circle</v-icon>
    </v-snackbar>
    <v-form ref="form" @submit.prevent="submit">
      <v-container fluid>
          <h1 class="h1">Enter your details to start using bbBook</h1>
        <v-row>
          <v-col cols="12" sm="6">
            <v-text-field
              v-model="form.first"
              :rules="rules.name"
              color="purple darken-2"
              label="First name"
              required
            ></v-text-field>
          </v-col>
          <v-col cols="12" sm="6">
            <v-text-field
              v-model="form.last"
              :rules="rules.name"
              color="blue darken-2"
              label="Last name"
              required
            ></v-text-field>
          </v-col>
           <v-col cols="12" sm="6">
          <v-text-field
            v-model="email"
            :rules="[rules.required, rules.email]"
            label="E-mail"
          ></v-text-field>
        </v-col>
           <v-col cols="12" sm="6">
          <v-text-field
            :append-icon="show2 ? 'mdi-eye' : 'mdi-eye-off'"
            :rules="[rules.required, rules.min]"
            :type="show2 ? 'text' : 'password'"
            name="input-10-2"
            label="Password"
            hint="At least 8 characters"
            value=""
            class="input-group--focused"
            @click:append="show2 = !show2"
          ></v-text-field>
        </v-col>
          <v-col cols="12">
            <v-textarea
              v-model="form.bio"
              color="teal"
            >
              <template v-slot:label>
                <div>
                  Bio <small>(optional)</small>
                </div>
              </template>
            </v-textarea>
          </v-col>
          <!-- <v-col cols="12" sm="6">
            <v-select
              v-model="form.favoriteAnimal"
              :items="animals"
              :rules="rules.animal"
              color="pink"
              label="Favorite animal"
              required
            ></v-select> -->
          <!-- </v-col> -->
              <v-col cols="12" sm="6">
            <v-text-field
              v-model="form.first"
              :rules="rules.name"
              color="purple darken-2"
              label="Baby's name"
              required
            ></v-text-field>
          </v-col>
          <v-col cols="12" sm="6">
            <v-slider
              v-model="form.age"
              :rules="rules.age"
              color="orange"
              label="Age"
              hint="Be honest"
              min="1"
              max="100"
              thumb-label
            ></v-slider>
          </v-col>
          <v-col cols="12">
            <v-checkbox
              v-model="form.terms"
              color="green"
            >
              <template v-slot:label>
                <div @click.stop="">
                  Do you accept the
                  <a href="javascript:;" @click.stop="terms = true">terms</a>
                  and
                  <a href="javascript:;" @click.stop="conditions = true">conditions?</a>
                </div>
              </template>
            </v-checkbox>
          </v-col>
        </v-row>
      </v-container>
      <v-card-actions>
        <v-btn text @click="resetForm">Cancel</v-btn>
        <v-spacer></v-spacer>
        <v-btn
          :disabled="!formIsValid"
          text
          color="primary"
          type="submit"
        >Register</v-btn>
      </v-card-actions>
    </v-form>
    <v-dialog v-model="terms" width="70%">
      <v-card>
        <v-card-title class="title">Terms</v-card-title>
        <v-card-text v-for="n in 5" :key="n">
          {{ content }}
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            text
            color="purple"
            @click="terms = false"
          >Ok</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
    <v-dialog v-model="conditions" width="70%">
      <v-card>
        <v-card-title class="title">Conditions</v-card-title>
        <v-card-text v-for="n in 5" :key="n">
          {{ content }}
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            text
            color="purple"
            @click="conditions = false"
          >Ok</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-card>
</v-app>
</template>

<script>
  export default {
    data () {
      const defaultForm = Object.freeze({
        first: '',
        last: '',
        bio: '',
        favoriteAnimal: '',
        age: null,
        terms: false,
      })

      return {
        form: Object.assign({}, defaultForm),
        rules: {
          age: [
            val => val < 10 || `I don't believe you!`,
          ],
          animal: [val => (val || '').length > 0 || 'This field is required'],
          name: [val => (val || '').length > 0 || 'This field is required'],
        },
        // animals: ['Dog', 'Cat', 'Rabbit', 'Turtle', 'Snake'],
        // conditions: false,
        // content: `Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. Praesent libero. Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum imperdiet. Duis sagittis ipsum. Praesent mauris. Fusce nec tellus sed augue semper porta. Mauris massa. Vestibulum lacinia arcu eget nulla. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Curabitur sodales ligula in libero. Sed dignissim lacinia nunc.`,
        // snackbar: false,
        // terms: false,
        // defaultForm,
      }
    },
     email: '',
        rules: {
          required: value => !!value || 'Required.',
          counter: value => value.length <= 20 || 'Max 20 characters',
          email: value => {
            const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
            return pattern.test(value) || 'Invalid e-mail.'
          },
        },
        

    computed: {
      formIsValid () {
        return (
          this.form.first &&
          this.form.last &&
          this.form.favoriteAnimal &&
          this.form.terms
        )
      },
    },

    methods: {
      resetForm () {
        this.form = Object.assign({}, this.defaultForm)
        this.$refs.form.reset()
      },
      submit () {
        this.snackbar = true
        this.resetForm()
      },
    },
  }
</script>
<style scoped>
#reg {
    margin-top: 150px
}
.h1 {
    color: #fc6b03
}
</style>