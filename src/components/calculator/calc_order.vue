<template>
    <div class="calc calc__column">

        <p></p>
    </div>
</template>


    <script>
    export default {
         name: 'CalcOrder' ,
        data() {
            return {
                  current_image: 1,
                  current_slide: 1,
                  object: {
                    ru: 'RU',
                    kaz: 'KAZ',
                    en: 'USA',
                  },
                  languages: {
                    ru: require('../../assets/images/ru.png'),
                    kaz: require('../../assets/images/kaz.png'),
                    en: require('../../assets/images/en.png'),
                  },
                  link: require('../../assets/images/kaz.png')
            }
        },
        components: {
        },
        methods: {
            logout() {
                localStorage.removeItem("access_token");

                this.$router.push("calculator");
            }
        }
    }
    </script>



    <style scoped lang="scss"> 
    .calc__column {
    display: flex;
    flex-direction: column;
    }
    .calc__row {
    display: flex;
    flex-direction: row;
    }
    .calc__ac {
    align-items: center;
    }
    .calc__jb {
    justify-content: space-between;
    }
    .calc__ja {
    justify-content: space-around;
    } 
    
    .calc {
        background-color: #fafafd;
    }

        .calc__header {

            background-color: var(--main-kenes-blue);
            padding: 15px;

            .calc__title {
                font-size: 22px;
                color: white;
                font-weight: bold;
            }
            .calc__user {
                margin-bottom: 5px;
            }

            .calc__logout {
                color: white;
                cursor: pointer;
            }
            .calc__logout:hover {
                border-bottom: 2px solid white;
            }
        }

        @media only screen and (max-width: 600px) {
            .calc__column {
                width: 100%;
            }   
            .calc__row {
                width: 100%;
            }
            .calc__title {
                font-size: 14px !important;
            }
            
            .calc__header {
                justify-content: space-between;
                .calc__column {
                    width: unset;
                }

            }
        }
    </style>
