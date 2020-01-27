<template>
  <div>
            
    <section>
      <form @submit.prevent="validateBeforeSubmit">
        <div class="field">
    
          <div class="control has-icons-left has-icons-right">
            <input class="input" onblur="if (this.value == '') {this.value = 'Full Name';}" onfocus="if (this.value == 'Full Name') {this.value = '';}"
                :value="fullName" @input="$emit('update:fullName', $event.target.value)" type="text">
                    <span class="icon is-small is-left">
                      <i class="fa fa-user"></i>
                    </span>
          </div>
         </div>
        <div class="field">
          <div class="control has-icons-left has-icons-right">
            <input class="input" onblur="if (this.value == '') {this.value = 'Title';}" onfocus="if (this.value == 'Title') {this.value = '';}" :value="title" @input="$emit('update:title', $event.target.value)" type="text">
                    <span class="icon is-small is-left">
                      <i class="fa fa-id-badge"></i>
                    </span>
          </div>
        </div>

  <div v-show="!mobilePhoneSwitch"></div>

        <div class="field">
          <div class="control has-icons-left has-icons-right">
            <input class="input" onblur="if (this.value == '') {this.value = 'Office';}" onfocus="if (this.value == 'Office') {this.value = '';}" :value="phone" @input="$emit('update:phone', $event.target.value)" type="text">
                    <span class="icon is-small is-left">
                      <i class="fa fa-phone"></i>
                    </span>
          </div>
        </div>
          <div v-show="mobilePhoneSwitch">
          <div class="field" style="margin-bottom: .75rem;">
          <div class="control has-icons-left has-icons-right">
            <input class="input" onblur="if (this.value == '') {this.value = 'Mobile';}" onfocus="if (this.value == 'Mobile') {this.value = '';}" :value="mobilePhone" @input="$emit('update:mobilePhone', $event.target.value)" type="text">
                   <span class="icon is-small is-left">
                      <i class="fa fa-mobile fa-lg"></i>
                    </span>
          </div>
        </div>
        </div>
        <div class="field">
          <div class="control has-icons-left has-icons-right">
            <input class="input" onblur="if (this.value == '') {this.value = 'Email';}" onfocus="if (this.value == 'Email') {this.value = '';}" :value="email" @input="$emit('update:email', $event.target.value)" type="text">
                    <span class="icon is-small is-left">
                      <i class="fa fa-envelope"></i>
                    </span>
          </div>
          
        </div>
        </form>
    </section>
         <button @click="changeTitle">Add/Remove: Mobile Phone</button>      
  </div>
</template>

<script>
export default {
  name: 'inputInformation',
  props: {
    fullName: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    mobilePhone: {
      type: String,
      required: true
    },
    phone: {
      type: String,
      required: true
    },
    email: {
      type: String,
      required: true
    },
    mobilePhoneSwitch: {
      type: Boolean,
      required: true
    }
  },
  methods: {
    changeTitle () {
      this.$emit('changeTitle', this.mobilePhoneSwitch = !this.mobilePhoneSwitch)
    }
  }
}
</script>

<style scoped>
h1,
h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #013d63;
}
</style>