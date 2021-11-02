<template>
    <div class="container mt-50">
        <div class="columns">
            <div class="column is-6 is-offset-3" >
                <h3 class="title is-3">Iniciar</h3><hr>
                <form action="#" @submit.prevent="login">
                    <div class="field">
                    <label class="label">Email</label>
                    <div class="control">
                        <input class="input" type="email" placeholder="e.g. alexsmith@gmail.com" v-model="correo">
                    </div>
                    </div>

                    <div class="field">
                    <label class="label">Contraseña</label>
                    <div class="control">
                        <input class="input" type="password" v-model="contrasena" >
                    </div>
                    </div>

                    <button type="submit" class="button is-primary">Iniciar sesion</button>
                </form>

                <div class="notification is-danger mt-10" v-if="error">
                {{error}}
                </div>
            </div>
        </div>
    </div>
</template>
<script>
//import db from '@/firebase/init.ts'
//import firebase from 'firebase';
export default {
    data(){
        return{
            correo: '',
            contrasena: '',
            error: ''
        }
    },
    name: 'Login',
    methods:{
        login(){
            this.error=''
            if(this.correo && this.contrasena){
                //enviar formulario
/*                 firebase.auth().signInWithEmailAndPassword(this.email, this.password)
                .then(user =>{
                    this.$route.push({name: '/Dashboard'})
                }).catch(err=>{
                    this.error = err.message
                })
*/
            } else{
                this.error= 'todos los campos son obligatorios.'
            }
        }
    }
}
</script>