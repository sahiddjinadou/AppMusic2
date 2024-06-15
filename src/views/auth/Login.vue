<template>
    <div class="login-container">
        <form action="">
            <div>
                <label for="">Adresse Email</label>
                <input type="email" name="" id="" placeholder="Entrer votre adresse mail">
            </div>
            <div>
                <label for="">Mot de passe</label>
                <input type="password" name="" id="" placeholder="Entrer votre mot de passe">
            </div>
            <div>
                <input type="checkbox" name="" id="">
                <label for="">Rester connecter</label>
            </div>
            <div>
                <input type="submit" value="Se connecter">
            </div>
        </form>
    </div>
</template>

<script setup lang='ts'>

</script>



<style scoped>
.login-container {
    display: flex;
    justify-content: center;
    margin-block: 3rem;
    /* border: 1px solid red; */
    
}

form {
    width: 90%;
    padding-block: 2rem;
    background: white;
    box-shadow: 0 1px 1px rgba(0, 0, 0, 0.2),
	            0 8px 0 -3px #f6f6f6,
	            0 9px 1px -3px rgba(0, 0, 0, 0.2),
	            0 16px 0 -6px #f6f6f6,
	            0 17px 2px -6px rgba(0, 0, 0, 0.2);
                /* border: 1px solid rgb(25, 0, 255); */

}
form > div {
    margin: 1rem;
}
input[type="email"], input[type="password"]{
    display: block;
    height: 2.2rem;
    width: 100%;
    background-color: rgba(0, 0, 255, 0.151);
    border: none;
    padding-inline: .5rem;

}
[type="submit"] {
    background-color: var(--fistColor);
    color: var(--whiteColor);
    padding-inline: 1rem;
    padding-block: 0.5rem;
    font-size: 1rem;
    border: none;
    border-radius: 25px;
    font-weight: bold;
}


@media (min-width: 768px) {
    form {
        width: 70%
    }
}

@media (min-width: 1024px) {
    form {
        width: 40%
    }
}
</style>