<template>
    <section class="sms">
        <h3>Sign up for text alerts</h3>
        <p>This will help us keep you updated on any issues or changes. Including COVID-19 infomation.</p>
        <form>
            <input placeholder="Mobile number...">
            <button type="submit">GO</button>
        </form>
    </section>
</template>

<script>
export default {
    name: 'Location'
}
</script>

<style lang="scss" scoped>
.sms {
    form {
        input {
            box-sizing: border-box;
            height: 30px;
            border-radius: 0;
            border: 0;
            background: #F2F2F2;
            outline: none;
            padding: 10px;
        }
        button {
            background: #6A4964;
            border: 0;
            height: 30px;
            color: white;
            width: 67px
        }
    }
}
</style>