<template>
  <div>
    <b-container>
      <b-row class="justify-content-md-center mt-4">
        <b-card
          header="Signup"
          header-bg-variant="primary"
          header-text-variant="white"
        >
          <b-card-text>
            <b-form @submit="onSubmit">
              <b-form-group description="Enter your username" lebel="Username">
                <b-form-input v-model="username" required></b-form-input>
              </b-form-group>

              <b-form-group description="Enter your password" lebel="Password ">
                <b-form-input
                  v-model="password"
                  type="password"
                  required
                ></b-form-input>
              </b-form-group>

              <b-form-group>
                <b-button
                  type="submit"
                  variant="outline-primary"
                  :disabled="acceptableSubmition"
                  >Sign up</b-button
                >
              </b-form-group>
            </b-form>
          </b-card-text>
        </b-card>
      </b-row>
    </b-container>
  </div>
</template>

<script>
export default {
  name: "SignUp",
  data() {
    return {
      username: "",
      password: "",
    };
  },

  methods: {
    onSubmit(event) {
      event.preventDefault();
      alert(this.username + " " + this.password);
    },

    computed: {
      acceptableSubmition() {
        return this.username.length > 0 && this.password.length > 0
          ? false
          : true;
      },
    },
  },
};
</script>