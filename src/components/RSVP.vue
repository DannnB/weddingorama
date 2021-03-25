<template>
    <section class="rsvp">
        <h2>RSVP</h2>
        <p>Ceremony &amp; Reception guests only</p>
        <label>You code
            <input type="text" />
        </label>
        <br>
        <label>Name
            <input type="text" />
        </label>
        <br>
        <label>Number attending
            <input type="text" />
        </label>
        <br>
        <label>
            <input type="radio" name="attending"/>
            Attending
        </label>
        <br>
        <label>
            <input type="radio" name="attending"/>
            Not Attending
        </label>

        <form>
            <div class="person">
                <h3>Guest 1</h3>
                <label>Name
                    <input type="text"/>
                </label>
                
                <div class="menu">
                    <h4>Starter</h4>
                    <label>
                        <input type="radio" name="starter"/>
                        Option one
                    </label>
                    <label>
                        <input type="radio" name="starter"/>
                        Option two
                    </label>

                    <h4>Main</h4>
                    <label>
                        <input type="radio" name="main"/>
                        Option one
                    </label>
                    <label>
                        <input type="radio" name="main"/>
                        Option two
                    </label>

                    <h4>Dessert</h4>
                    <label>
                        <input type="radio" name="dessert"/>
                        Option one
                    </label>
                    <label>
                        <input type="radio" name="dessert"/>
                        Option two
                    </label>
                </div>
            </div>
            <button>Add another guest?</button>
            
            <div class="person">
                <h3>Guest 2</h3>
                <label>Name
                    <input type="text"/>
                </label>
                
                <div class="menu">
                    <h4>Starter</h4>
                    <label>
                        <input type="radio" name="starter"/>
                        Soup of the day
                    </label>
                    <label>
                        <input type="radio" name="starter"/>
                        Option two
                    </label>

                    <h4>Main</h4>
                    <label>
                        <input type="radio" name="main"/>
                        Option one
                    </label>
                    <label>
                        <input type="radio" name="main"/>
                        Option two
                    </label>

                    <h4>Dessert</h4>
                    <label>
                        <input type="radio" name="dessert"/>
                        Option one
                    </label>
                    <label>
                        <input type="radio" name="dessert"/>
                        Option two
                    </label>
                </div>
            </div>
            
        </form>
    </section>
</template>

<script>
export default {
    name: 'RSVP'
}
</script>

<style lang="scss" scoped>
    .person {
        margin: 10px 0;
        padding: 20px;
        background: rgb(230, 230, 230);
    }
</style>