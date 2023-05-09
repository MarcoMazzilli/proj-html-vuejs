<script>
import dbContacts from '../../../data/dbContacts';
import Socialbox from '../Socialbox.vue';

export default {
    data() {
        return {
            dbContacts,
        };
    },
    props: {
        name: String,
        url: String,
        logo: String
    },
    components: {
        Socialbox
    }
}
</script>

<template>
    <div class="contacts-header">

        <div class="container">
            <div class="row">

                <div class="col">

                    <!-- CONTACTS  -->
                    <div class="mail">
                        <i class="fa-solid fa-envelope"></i></div>
                        <span>{{ dbContacts.mail }}</span>

                    <div class="phone">
                        <i class="fa-solid fa-phone"></i></div>
                        <span>{{ dbContacts.phoneNumber }}</span>
                </div>

                <div class="col">

                    <Socialbox v-for="social in dbContacts.social" :key="social"
                    :name="social.name"
                    :url="social.url"
                    :logo="social.logo"
                    />



                </div>
            </div>
            
        </div>
        
        
    </div>
</template>

<style lang="scss" scoped>
@import '../../../scss/general/_variables.scss';
.dbg{
    background-color: rgba(255, 208, 0, 0.2);
    border: 1px solid black;
}

.contacts-header{
    height: 55px;
    background-color: $brandSecondary;

    .container{
        height: 100%;
        .row{
            height: 100%;

            .col:first-child{
                height: 100%;
                display: flex;
                align-items: center;

                i{
                    color: $brandMain;
                    margin-right: 10px;
                }
                span{
                    color: white;
                    margin-right: 15px;
                }
            }
            .col:last-child{
                height: 100%;
                display: flex;
                align-items: center;
                justify-content: flex-end;
            }
        }
    }        
}

</style>