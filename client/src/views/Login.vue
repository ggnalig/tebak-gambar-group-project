<template>
    <div class="container">
        <div class="title">
            <h2>Welcome to <strong>Guess The Word</strong> Game !</h2>
        </div>
        <img class="image mt-5" src="https://media0.giphy.com/media/SsIZQ5my0eba5y3r2m/giphy.gif" />
        <div class="row mt-5 d-flex justify-content-center">
            <div class="form">
                <form @submit.prevent="inputNick">
                    <div class="form-group">
                        <label for="formGroupExampleInput">Please insert your nick name !</label>
                        <input
                            type="text"
                            class="form-control"
                            id="formGroupExampleInput"
                            placeholder="Your nick name"
                            v-model="nick"
                        />
                    </div>
                    <button type="submit" class="btn btn-primary">Submit</button>
                </form>
            </div>
        </div>
        <!-- <audio autoplay controls class="mt-5">
            <source src="musicSaja.mp3" type="audio/mpeg" />
        </audio> -->
    </div>
</template>

<script>
export default {
    name: 'Login',
    data: () => {
        return {
            nick: null
        };
    },
    methods: {
        inputNick() {
            console.log(this.nick);
            localStorage.nick = this.nick;
            localStorage.id = this.nick + new Date().getTime();
            localStorage.point = 0;
            this.$router.push('/');
        }
    }
};
</script>

<style scoped>
.image {
    height: 150px;
    width: 150px;
    border-radius: 10px;
}

.form {
    width: 40%;
}
</style>
