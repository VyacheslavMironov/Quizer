<template>
    <div class="container mx-auto">
        <form class="mt-5 col-6 mx-auto">
            <div v-if="error.length > 0" class="alert alert-danger" role="alert">
                {{ error }}
            </div>
            <div class="mb-3">
                <label for="exampleInputEmail1" class="form-label">Email address</label>
                <input type="email" v-model="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
            </div>
            <div class="mb-3">
                <label for="exampleInputPassword1" class="form-label">Password</label>
                <input type="password" v-model="password" class="form-control" id="exampleInputPassword1">
            </div>
            <button type="button" v-on:click="auth" class="btn btn-primary">Submit</button>
        </form>
    </div>
</template>

<script>
    export default {
        data(){
            return {
                email: null,
                password: null,
                error: "",
                user: {
                    name: "Иван",
                    surname: "Бубликов",
                    age: 21,
                    email: "ivan.bub@mail.ru",
                    password: "123"
                }
            }
        },
        methods: {
            auth: function()
            {
                if (this.email == this.user.email)
                {
                    if (this.password == this.user.password)
                    {
                        localStorage.setItem("userName", this.user.name)
                        localStorage.setItem("userSurName", this.user.surname)
                        localStorage.setItem("userEmail", this.user.email)
                        localStorage.setItem("userAge", this.user.age)
                        this.error = ""
                        this.email = ""
                        this.password = ""
                        return location.href = "/"
                    } else {
                        this.error = "Введите правильный пароль!"
                    }
                } else {
                    this.error = "Не верный E-mail!"
                }
            }
        }
    }
</script>