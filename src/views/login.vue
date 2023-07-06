<template>
  
  <v-card class="mx-auto pa-4 mt-4" width="100%" max-width="500" dir="rtl">
    <v-form v-if="!loginForm" dir="rtl" @submit.prevent="">
      <div class="text-center mb-4">
        <span style="color: orangered"> ایجاد حساب</span>
      </div>
      <v-text-field 
        v-model="userName"
        :class="userNameValidation"
        class="mb-4"
        clearable
        label="شماره تلفن یا نام کاربری"
        type="text"
        dir="ltr"
      />
      <v-text-field
        :class="userPasswordValidation"
        v-model="userPassword"
        class="mb-4"
        clearable
        label="رمز عبور"
        type="password"
        dir="ltr"
      />
      <v-text-field
        :disabled="isEmpty"
        :class="confirmPasswordValidation"
        v-model="confirmPassword"
        class="mb-4"
        clearable
        label="تایید رمز عبور"
        type="password"
        dir="ltr"
      />
      <span :class="warning">تعداد کاراکتر های وارد شده کمتر از 8 میباشد</span>

    </v-form>
    
    
    



    <v-form v-else-if="!creatForm" dir="rtl" @submit.prevent="">
      <div class="text-center mb-4">
        <span style="color: orangered"> ورود به حساب کاربری </span>
      </div>
      <v-text-field 
        v-model="userName"
        :class="userNameValidation"
        class="mb-4"
        clearable
        label="شماره تلفن یا نام کاربری"
        type="text"
        dir="ltr"
      />
      <v-text-field
        :class="userPasswordValidation"
        v-model="userPassword"
        class="mb-4"
        clearable
        label="رمز عبور"
        type="password"
        dir="ltr"
      />
      <span :class="warning">تعداد کاراکتر های وارد شده کمتر از 8 میباشد</span>
      <v-radio-group class="mt-4 text-center" color="success">
        <template v-slot:label>
          <div>انتخاب <strong>نحوه ورود به حساب کاربری:</strong></div>
        </template>
        <v-radio value="شماره تلفن همراه">
          <template v-slot:label>
            <div><strong class="text-orange">شماره تلفن همراه</strong></div>
          </template>
        </v-radio>
        <v-radio value="نام کاربری">
          <template v-slot:label>
            <div><strong class="text-primary">نام کاربری</strong></div>
          </template>
        </v-radio>
      </v-radio-group>
    </v-form>

    <v-btn
    v-on:click="creatForm = false,loginForm=true"
    class="botton"
    color="success"
    size="large"
    type="submit"
    variant="elevated"
    >
      ورود
    </v-btn>
    <v-btn
      v-on:click="loginForm=false,creatForm = true"
      class="botton"
      color="red"
      size="large"
      type="submit"
      variant="elevated"
    >
    ایجاد 
    </v-btn>
  </v-card>
  
</template>

<script>
export default {
data() {
return {
  userName: '',
  userPassword: '',
  userNameValidFormat: false,
  confirmPassword: '',
  isEmpty:true,
  loginForm: true,
  creatForm:false,
};
},
computed: {
userNameValidation() {
  if(this.userName.length >= 8) {
    return "valid"
  } else if(this.userName == 0) {
    return "start"
  } else {
    return "invalid"
  }
},
userPasswordValidation() {
  if(this.userPassword.length >= 8) {
    this.isEmpty = false
    return "valid"
  } else if(this.userPassword.length == 0) {
    this.isEmpty = true
    return "start" 
  } else {
    this.isEmpty = true
    return "invalid"
  }
},
  confirmPasswordValidation() {
  if(this.confirmPassword.length >= 8 && this.confirmPassword == this.userPassword) {
    return "valid"
  } else if(this.confirmPassword.length == 0) {
    return "start"
  } else {
    return "invalid"
  }
},
warning() {
  if(this.userPasswordValidation == "invalid") {
    return "ok"
  } else if(this.userPasswordValidation == "valid" || this.userPasswordValidation == "start") {
    return "no"
  }
}
},
}
</script>
<style>
.valid {
color: green;
}
.invalid {
color: red;
}
.no {
visibility: hidden;
}
.ok {
visibility: visible;
color: red;
}
.botton {
width: 50%;
}
</style>