<template>
    <div class="page landing">
        <div class="user-details">
            <img src="http://placehold.it/300x146"/>
            <form>
                <label for="">First name</label>
                <input type="text" name="firstname" placeholder="Firstname"/>
                <label for="">Last name</label>
                <input type="text" name="firstname" placeholder="Lastame"/>
                <hr>
                <label for="">Email</label>
                <input type="text" name="firstname" placeholder="Email"/>
                <label for="">Confirm Email</label>
                <input type="text" name="firstname" placeholder="Confirm email"/>
            </form>
            <button type="submit">Create your page</button>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.landing {
    background-color: #AC11F4;
    height: 100vh;
    position: relative;
}
.user-details {
    display: flex;
    width: 400px;
    border: 1px solid black;
    background-color: #fff;
    padding: 60px;
    flex-direction: column;
    img {

    }
    button {
        height: 52px;
        width: 100%;
        max-width: 280;
        background: #6A4964;
        border: none;
        color: #fff;
        text-transform: uppercase;
        font-size: 1.2rem;
    }
}
</style>