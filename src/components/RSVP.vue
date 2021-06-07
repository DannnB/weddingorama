<template>
    <section class="rsvp">
        <h2>Online RSPV</h2>
        <p>Please go through the steps below to send us your RSVP details</p>
        <div class="form-steps">
            <div class="step-1">
                <h3 class="title is-3">Step One - Where are you invited for?</h3>
                <button>Ceremony</button>
                <button>Evening</button>
            </div>
            <div class="step-2">
                <h3 class="title is-3">Step Two - Accept or Decline</h3>
                <label>
                    <input type="checkbox" name="accept-decline"/>
                    Accepts with pleasure
                </label>
                <label>
                    <input type="checkbox" name="accept-decline"/>
                    Declines with regrets
                </label>
            </div>
            <div class="step-3">
                <h3 class="title is-3">Step Three - Guest Names and Song Request</h3>
                <h4 class="title is-4">Guest Names</h4>
                <label>
                    <span>1</span>
                    <input type="text"/>
                </label>
                <label>
                    <span>2</span>
                    <input type="text"/>
                </label>
                <label>
                    <span>3</span>
                    <input type="text"/>
                </label>
                <label>
                    <span>4</span>
                    <input type="text"/>
                </label>
                <label>
                    Song Request
                    <input type="text"/>
                </label>
            </div>
        </div>
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
    label {
        display: block;
        position: relative;
        width: 100%;
        box-sizing: border-box;
        span {
            display: inline-block;
            position: relative;
            top: -11px;
            width: 40px;
            height: 45px;
            color: #ffffff;
            background: #6A4964;
        }
        input {
            height: 40px;
            border: 1px solid #6A4964;
        }
    }
</style>