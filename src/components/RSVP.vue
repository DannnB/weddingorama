<template>
    <section class="rsvp">
        <h2>Online RSPV</h2>
        <p>More infomation will coming soon, including a gift list and schedule!</p>
        <p v-if="!rsvp_finished"><strong>Please go through the steps below to send us your RSVP details</strong></p>
        <form class="form-steps" v-if="!rsvp_finished">
            <div class="step step-1">
                <h3 class="title is-3">Step One - When are you invited for?</h3>
                <button class="btn" :class="{active: rsvp.type === 'ceremony'}" @click.prevent="setType('ceremony')">Ceremony</button>
                <button class="btn" :class="{active: rsvp.type === 'evening'}" @click.prevent="setType('evening')">Evening</button>
            </div>
            <div class="step step-2" v-if="steps.one">
                <h3 class="title is-3">Step Two - Accept or Decline</h3>
                <label>
                    <input v-model="accepts_declines" type="radio" value="accepts" required name="accept-decline"/>
                    Accepts with pleasure
                </label>
                <label>
                    <input v-model="accepts_declines" type="radio" value="declines" required name="accept-decline"/>
                    Declines with regrets
                </label>
            </div>
            <div class="step step-3-decline" v-if="accepts_declines === 'declines'">
                <h4 class="title is-4">Please enter your name and then click send to let us know</h4>
                <label>
                    <input type="text" v-model="decline_name"/>
                </label>
                <button class="btn btn-primary" @click.prevent="decline">Send Decline</button>
            </div>
            <div class="step step-3" v-if="accepts_declines === 'accepts'">
                <h3 class="title is-3">Step Three - Guest Names and Song Request</h3>
                <h4 class="title is-4">Guest Names</h4>
                <label class="margin">
                    <span>1</span>
                    <input v-model="rsvp.guests.names.one" required class="is-numbered" type="text"/>
                </label>
                <label class="margin">
                    <span>2</span>
                    <input v-model="rsvp.guests.names.two" class="is-numbered" type="text"/>
                </label>
                <label class="margin">
                    <span>3</span>
                    <input v-model="rsvp.guests.names.three" class="is-numbered" type="text"/>
                </label>
                <label class="margin">
                    <span>4</span>
                    <input v-model="rsvp.guests.names.four" class="is-numbered" type="text"/>
                </label>
                <h4 class="title is-4">Song Request</h4>
                <label class="margin">
                    <input v-model="song_request" type="text"/>
                </label>
            </div>
            <div class="step step-4" v-if="rsvp.guests.names.one">
                <h3 class="title is-3">Step Four - Food Menu</h3>
                <h4 class="title is-4">Please see the menu supplied. Each box is numbered in relation to your guest names you filled out.</h4>
                <!-- TODO: output gues names with numbers -->
                <div class="guest-menu">
                    <div class="guest guest-1" v-if="rsvp.guests.names.one">
                        <h3 class="title is-3">Guest 1: {{rsvp.guests.names.one}}</h3>
                        <div class="courses">
                            <div class="course starter">
                                <h4 class="title is-4">Starter</h4>
                                <label>
                                    <input v-model="rsvp.guests.one.starter" type="radio" value="A" required name="starter-1"/>
                                    A
                                </label>
                                <label>
                                    <input v-model="rsvp.guests.one.starter" type="radio" value="B" required name="starter-1"/>
                                    B
                                </label>
                            </div>
                            <div class="course main">
                                <h4 class="title is-4">Main</h4>
                                <label>
                                    <input v-model="rsvp.guests.one.main" type="radio" value="A" required name="main-1"/>
                                    A
                                </label>
                                <label>
                                    <input v-model="rsvp.guests.one.main" type="radio" value="B" required name="main-1"/>
                                    B
                                </label>
                            </div>
                            <div class="course dessert">
                                <h4 class="title is-4">Dessert</h4>
                                <label>
                                    <input v-model="rsvp.guests.one.dessert" type="radio" value="A" required name="dessert-1"/>
                                    A
                                </label>
                                <label>
                                    <input v-model="rsvp.guests.one.dessert" type="radio" value="B" required name="dessert-1"/>
                                    B
                                </label>
                            </div>
                        </div>
                        <div class="requirements">
                            <h4 class="title is-4">Dietary requirements</h4>
                            <label>
                                <input v-model="rsvp.guests.one.dietary_requirements" type="text"/>
                            </label>
                        </div>
                    </div>
                    <div class="guest guest-2" v-if="rsvp.guests.names.two">
                        <h3 class="title is-3">Guest 2: {{rsvp.guests.names.two}}</h3>
                        <div class="courses">
                            <div class="course starter">
                                <h4 class="title is-4">Starter</h4>
                                <label>
                                    <input v-model="rsvp.guests.two.starter"  type="radio" value="A" required name="starter-2"/>
                                    A
                                </label>
                                <label>
                                    <input v-model="rsvp.guests.two.starter"  type="radio" value="B" required name="starter-2"/>
                                    B
                                </label>
                            </div>
                            <div class="course main">
                                <h4 class="title is-4">Main</h4>
                                <label>
                                    <input v-model="rsvp.guests.two.main"  type="radio" value="A" required name="main-2"/>
                                    A
                                </label>
                                <label>
                                    <input v-model="rsvp.guests.two.main"  type="radio" value="B" required name="main-2"/>
                                    B
                                </label>
                            </div>
                            <div class="course dessert">
                                <h4 class="title is-4">Dessert</h4>
                                <label>
                                    <input v-model="rsvp.guests.two.dessert"  type="radio" value="A" required name="dessert-2"/>
                                    A
                                </label>
                                <label>
                                    <input v-model="rsvp.guests.two.dessert"  type="radio" value="B" required name="dessert-2"/>
                                    B
                                </label>
                            </div>
                        </div>
                        <div class="requirements">
                            <h4 class="title is-4">Dietary requirements</h4>
                            <label>
                                <input v-model="rsvp.guests.two.dietary_requirements" type="text"/>
                            </label>
                        </div>
                    </div>
                    <div class="guest guest-3" v-if="rsvp.guests.names.three">
                        <h3 class="title is-3">Guest 3: {{rsvp.guests.names.three}}</h3>
                        <div class="courses">
                            <div class="course starter">
                                <h4 class="title is-4">Starter</h4>
                                <label>
                                    <input v-model="rsvp.guests.three.starter" type="radio" value="A" required name="starter-3"/>
                                    A
                                </label>
                                <label>
                                    <input v-model="rsvp.guests.three.starter" type="radio" value="B" required name="starter-3"/>
                                    B
                                </label>
                            </div>
                            <div class="course main">
                                <h4 class="title is-4">Main</h4>
                                <label>
                                    <input v-model="rsvp.guests.three.main" type="radio" value="A" required name="main-3"/>
                                    A
                                </label>
                                <label>
                                    <input v-model="rsvp.guests.three.main" type="radio" value="B" required name="main-3"/>
                                    B
                                </label>
                            </div>
                            <div class="course dessert">
                                <h4 class="title is-4">Dessert</h4>
                                <label>
                                    <input v-model="rsvp.guests.three.dessert" type="radio" value="A" required name="dessert-3"/>
                                    A
                                </label>
                                <label>
                                    <input v-model="rsvp.guests.three.dessert" type="radio" value="B" required name="dessert-3"/>
                                    B
                                </label>
                            </div>
                        </div>
                        <div class="requirements">
                            <h4 class="title is-4">Dietary requirements</h4>
                            <label>
                                <input v-model="rsvp.guests.three.dietary_requirements" type="text"/>
                            </label>
                        </div>
                    </div>
                    <div class="guest guest-4" v-if="rsvp.guests.names.four">
                        <h3 class="title is-3">Guest 4: {{rsvp.guests.names.four}}</h3>
                        <div class="courses">
                            <div class="course starter">
                                <h4 class="title is-4">Starter</h4>
                                <label>
                                    <input v-model="rsvp.guests.four.starter" type="radio" value="A" required name="starter-4"/>
                                    A
                                </label>
                                <label>
                                    <input v-model="rsvp.guests.four.starter" type="radio" value="B" required name="starter-4"/>
                                    B
                                </label>
                            </div>
                            <div class="course main">
                                <h4 class="title is-4">Main</h4>
                                <label>
                                    <input v-model="rsvp.guests.four.main" type="radio" value="A" required name="main-4"/>
                                    A
                                </label>
                                <label>
                                    <input v-model="rsvp.guests.four.main" type="radio" value="B" required name="main-4"/>
                                    B
                                </label>
                            </div>
                            <div class="course dessert">
                                <h4 class="title is-4">Dessert</h4>
                                <label>
                                    <input v-model="rsvp.guests.four.dessert" type="radio" value="A" required name="dessert-4"/>
                                    A
                                </label>
                                <label>
                                    <input v-model="rsvp.guests.four.dessert" type="radio" value="B" required name="dessert-4"/>
                                    B
                                </label>
                            </div>
                        </div>
                        <div class="requirements">
                            <h4 class="title is-4">Dietary requirements</h4>
                            <label>
                                <input v-model="rsvp.guests.four.dietary_requirements" type="text"/>
                            </label>
                        </div>
                    </div>
                </div>

                <div class="submit">
                    <p>If you want a copy of your RSVP please enter your email below.</p>
                    <label>
                        <input v-model="rsvp.contact_email" type="email" placeholder="email..."/>
                    </label>
                    <button class="btn btn-primary" @click.prevent="send">Send your RSVP</button>
                </div>
            </div>
        </form>
        <p v-if="rsvp_finished">Thank you for filling out the form! For any questions or changes please contact us on phone or social media.</p>
    </section>
</template>

<script>
import axios from 'axios';
export default {
    name: 'RSVP',
    data() {
        return {
            steps: {
                one: false,
                two: false,
                three_decline: false,
                three: false,
                four: false,
            },
            accepts_declines: null,
            decline_name: '',
            song_request: '',
            rsvp: {
                type: null,
                contact_email: '',
                guests: {
                    names: {
                        one: '',
                        two: '',
                        three: '',
                        four: '',
                    },
                    one: {
                        starter: '',
                        main: '',
                        dessert: '',
                        dietary_requirements: ''
                    },
                    two: {
                        starter: '',
                        main: '',
                        dessert: '',
                        dietary_requirements: ''
                    },
                    three: {
                        starter: '',
                        main: '',
                        dessert: '',
                        dietary_requirements: ''
                    },
                    four: {
                        starter: '',
                        main: '',
                        dessert: '',
                        dietary_requirements: ''
                    },
                }
            },
            rsvp_finished: false
        }
    },
    methods: {
        setType(type) {
            this.rsvp.type = type;
            this.steps.one = true;
        },
        decline() {
            const declined = {
                accepts_declines: this.accepts_declines,
                type: this.rsvp.type,
                name: this.decline_name,
            }
            var data = JSON.stringify(declined);

            var config = {
            method: 'post',
            url: 'https://api.codehubble.com/api/forms/rspv',
            headers: { 
                'Content-Type': 'application/json'
            },
            data : data
            };

            axios(config)
            .then(function (response) {
                console.log(JSON.stringify(response.data));
            })
            .catch(function (error) {
                console.error(error);
            });

            this.rsvp_finished = true;
        },
        send() {
            const form = {
                accepts_declines: this.accepts_declines,
                rsvp: this.rsvp,
                song_request: this.song_request

            }
            var data = JSON.stringify(form);

            var config = {
            method: 'post',
            url: 'https://api.codehubble.com/api/forms/rspv',
            headers: { 
                'Content-Type': 'application/json'
            },
            data : data
            };

            axios(config)
            .then(function (response) {
                console.log(response.data);
                // if(response.data.status === 'success') {
                //     this.rsvp_finished = true;
                // }
            })
            .catch(function (error) {
                console.error(error);
            });
            this.rsvp_finished = true;
        }
    }
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
        font-size: 1.2rem;
        &.margin {
            margin: 10px 0;
        }
        span {
            display: inline-block;
            position: relative;
            top: -0px;
            width: 40px;
            height: 45px;
            color: #ffffff;
            background: #6A4964;
            border: 1px solid #6A4964;
            box-sizing: border-box;
            padding-top: 10px;
        }
        input {
            width: 100%;
            height: 40px;
            border: 1px solid #6A4964;
            position: relative;
            top: -2px;
            box-sizing: border-box;
            padding-left: 10px;
            &.is-numbered {
                height: 44px;
                width: 88%;
            }
        }
        input[type="radio"] {
            width: 20px;
            padding-top: 10px;
            height: 14px;
            margin-top: 20px;
        }
    }
    .step {
        margin: 20px 0;
    }
    .guest-menu {
        .guest {
            border: 1px solid #6A4964;
            padding: 10px 10px 30px 10px;
            margin: 10px 0;
        }
        .courses {
            display: flex;
            justify-content: space-evenly;
            .course {
            }
        }
        .requirements {
            input {
                width: 90%;
            }
        }
    }
</style>