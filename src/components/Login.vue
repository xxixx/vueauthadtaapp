<template>
     <div class="card card1">
                <div class="row justify-content-center my-auto">
                    <div class="col-md-8 col-10 my-5">
                        <div class="row justify-content-center px-3 mb-3">  </div>
                        <h3 class="mb-5 text-center heading">Login</h3>
                        <h6 class="msg-info">Please login to your account</h6>
                        <div class="form-group"> <label class="form-control-label text-muted">Username</label> <input type="text" id="email" name="email" placeholder="Phone no or email id" class="form-control"> </div>
                        <div class="form-group"> <label class="form-control-label text-muted">Password</label> <input type="password" id="psw" name="psw" placeholder="Password" class="form-control"> </div>
                        <div class="row justify-content-center my-3 px-3"> <button class="btn-block btn-color">Login to Tidi</button> </div>
                        <div class="row justify-content-center my-2"> <a href="#"><small class="text-muted">Forgot Password?</small></a> </div>
                    </div>
                </div>
                <div class="bottom text-center mb-5">
                    <button @click="gettest">gettest</button>
                     <button @click="posttest">posttest</button>
                    <p href="#" class="sm-text mx-auto mb-3">Don't have an account?<button class="btn btn-white ml-2">Create new</button></p>
                </div>
            </div>

</template>

<script>
import { mapState, mapActions} from 'vuex'
import axios from 'axios'
export default {
    computed : {
        ...mapState(["isLogin", "isLoginError"])
    },
    methods : {
        ...mapActions(["login"]),
        gettest(){
                    axios.get('https://reqres.in/api/login')
                    .then( response => {
                        // handle success
                        console.log(response);
                    })
                    .catch( error => {
                        // handle error
                        console.log(error);
                    })
                    .then( () => {
                        // always executed
                        //  this.$router.replace('/')
                    });
        },
      
        posttest(){
             axios.post('https://reqres.in/api/login', {
               "email": "eve.holt@reqres.in",
               "password": "pistol"
            })
            .then(function (response) {
                console.log(response);
            })
            .catch(function (error) {
                console.log(error);
            });
        }
     
    }

}
</script>

 <style>
     
    </style>