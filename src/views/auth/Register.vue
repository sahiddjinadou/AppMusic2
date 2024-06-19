<template>
    <div class="login-container flex">
        <form action="">
            <div>
                <label for="lname" >Nom d'utilisateur</label>
                <input type="text" name="" id="lname" placeholder="Entrer un nom d'utilisateur">
            </div>
            <div>
                <label for="">Adresse Email</label>
                <input type="email" name="" id="" placeholder="Entrer votre adresse mail">
            </div>
            <div>
                <label for="passw">Mot de passe</label>
                <input type="password" name="" id="passw" placeholder="Entrer votre mot de passe">
            </div>
            <div>
                <label for="confirm">Confirmer votre mot de passe</label>
                <input type="password" name="" id="confirm" placeholder="Confirmer votre mot de passe">
            </div>
            <div class="btnContainer flex">
                <div>
                    <input type="submit" value="S'inscrire">
                </div>
                <div>
                    <RouterLink to="login" type="button">Se connecter</RouterLink>
                </div>
            </div>
        </form>


    </div>
</template>

<script setup lang='ts'>

</script>



<style scoped>
a {
    color: inherit;
    font-size: 1rem;
    padding: .5rem;

}
a:hover {
    background-color: initial;
    text-decoration: underline;

  }

.flex {
    display: flex;
    align-items:center;
 
}
.login-container {
    margin-block: 3rem;
    justify-content: center;
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

}
form > div {
    margin: 1rem;
}
label {
    font-weight: 500;
}

input[type="email"], input[type="password"], input[type="text"] {
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

.btnContainer {
    justify-content: space-between;

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