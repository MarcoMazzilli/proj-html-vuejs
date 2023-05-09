<script>
import dbHeaderMenu from '../../../data/dbHeaderMenu';

export default {
    data(){
        return{
            dbHeaderMenu,
        }
    }
    
}
</script>

<template>
<div class="menus-header">

    <div class="container">
        
        <div class="row">

            <div class="col col-3">
                <a href="">
                    <img src="/logo.png" alt="Logo Dog-Milo">
                </a>
            </div>

            <div class="col col-9">
                <ul>
                    <li v-for="link in dbHeaderMenu" :key="link" >
                        <a :href="link.url">{{ link.name }}</a>
                    </li>
                </ul>
            </div>

        </div>

    </div>  

</div>
</template>

<style lang="scss" scoped>
@import '../../../scss/general/_variables.scss';

.menus-header{
    height: 95px;
    background-color: $backgroundMain;

    .container{
        height: 100%;
        .row{
            height: 100%;
            
            .col{
                height: 100%;
                &:first-child{
                    display: flex;
                    align-items: center;
                    
                }
                &:last-child{
                    display: flex;
                    align-items: center;
                    justify-content: flex-end;

                    ul{
                        display: flex;
                        align-content: center;
                        list-style: none;
                        margin: 0;

                        li a{
                            font-size: 21px;
                            font-weight: 600;
                            margin: 0 20px;
                            text-decoration: none;
                            color: $txtColor;
                            transition: all .3s;

                            &:hover {
                                color: $brandMain;
                            }
                        }
                        li:last-of-type a{
                            color: white;
                            margin-right: 0;
                            background-color: $brandMain;
                            padding: 15px 25px;
                            border-radius: 50px;
                            transition: .3s;

                            &:hover{
                                background-color: $hoverBtn;
                            }
                        }
                    }
                }
            }
        }
    }
}
</style>