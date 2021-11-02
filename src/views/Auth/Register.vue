<template>
    <div class="container mt-50">
        <div class="columns">
            <div class="column is-6 is-offset-3" >
                <h3 class="title is-3">Crear una cuenta</h3><hr>
                <form action="#" @submit.prevent="register">
                    <div class="field">
                    <label class="label">Nombre</label>
                    <div class="control">
                        <input class="input" type="text" placeholder="e.g Alex" v-model="nombre">
                    </div>
                    </div>

                    <div class="field">
                    <label class="label">Apellido</label>
                    <div class="control">
                        <input class="input" type="text" placeholder="e.g Smith" v-model="apellido">
                    </div>
                    </div>

                    <div class="field">
                    <label class="label">Correo</label>
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

                    <div class="field">
                    <label class="label">Rol</label>
                    <div class="control">
                    <label class="radio">
                        <input type="radio" name="rol">
                        Administrador
                    </label>
                    <label class="radio">
                        <input type="radio" name="rol">
                        Cliente
                    </label>
                    </div>
                    </div>

                    <button type="submit" class="button is-primary">Registrarme</button>
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
            nombre: '',
            apellido:'',
            correo: '',
            contrasena: '',
            rol: '',

            error: ''
        }
    },
    name: 'Register',
    methods:{
        register(){
            this.error=''
            if(this.nombre && this.apellido && this.correo && this.contrasena && this.rol){
                //enviar formulario
/*                 firebase.auth().createUserWithEmailAndPassword(this.correo, this.contrasena)
                .then(user =>{
                    this.nombre=''
                    this.correo='',
                    this.contrasena=''
                    console.log(user)
                }).catch(err =>{
                    this.error=err.message
                }) */
            } else{
                this.error= 'todos los campos son obligatorios.'
            }
        }
    }
}
</script>