<template>
	<div class="container">
		<div class="form">
		<h3>{{ msg }}</h3>
		</div>
		<div class="form-body">
		<div class="form-body-left">
		<label for="salutation" >
			<b>Anrede</b>
			<form>
				<select>
				<option value="mr">Herr</option>
				<option value="mrs">Frau</option>
				<option value="company">Firma</option>
				</select>
			</form>
		</label>

    <label for="username"><b>Benutzername*</b></label>
    <input type="text" placeholder="Benutzername" name="uname" v-model='uname' required>

    <label for="text"><b>Passwort*</b></label>
    <input type="password" placeholder="Passwort" name="psw" v-model='psw' required>

    <label for="psw"><b>Passwort Wiederholen*</b></label>
    <input type="password" placeholder="Passwort Wiederholen" name="psw" v-model='pswagain' required>

    <label for="email"><b>Email Adresse*</b></label>
    <input type="email" placeholder="Email Adresse" name="email" v-model='email' required>

    <div class="form-body-left-context">
      <a href="https://vuejs.org/guide/introduction.html" target="_blank">
       <input type="checkbox"  v-model='subtitle' required /> Ja, ich habe die AGB gelesen und stimme zu.</a>
    </div>
</div>

	<div class="form-body-right">
    <label for="name"><b>Vorname*</b></label>
    <input type="text" placeholder="Vorname" name="name" v-model='name' required>

    <label for="surname"><b>Nachname*</b></label>
    <input type="text" placeholder="Nachname" name="surname" v-model='surname' required>

    <label for="street"><b>Straße</b></label>
    <input type="text" placeholder="Straße" name="street">

    <label for="post"><b>PLZ</b></label>
    <input type="text" placeholder="PLZ" name="post">

    <div class="form-body-right-context">
    <button :disabled="isBtnDisabled" type="submit" class="btn">WEITER</button>
    </div>
    </div>
    </div>
  
    <div class="form-footer" >
        <sub>© Copyright 2022 -Beispiel-  Alle Rechte vorbehalten.</sub>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
      data: function () {
        return {
          uname:"",
          name: "",
          surname: "",
          psw: "",
          pswagain:"",
          email:"",
          subtitle:"",
        };
      },
      computed: {
        isBtnDisabled() {
          return (  
            this.name.length === 0 ||
            this.surname.length === 0 ||
            this.psw.length === 0 ||
            this.pswagain.length === 0 || 
            this.uname.length === 0 ||
            this.email.length === 0 ||
            this.subtitle.length === 0
          );
        },
      },
}
</script>