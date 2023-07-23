<script>
    export default{
        data(){
            return{

            };

        },
        computed:{
            flag(){
                if(this.elementData.original_language == 'it'){

                    return 'https://flagicons.lipis.dev/flags/4x3/it.svg';

                }
            
                else if(this.elementData.original_language == 'en'){

                    return 'https://flagicons.lipis.dev/flags/4x3/gb.svg';

                }
                

                else{

                    return 'https://flagicons.lipis.dev/flags/4x3/un.svg';

                }
               
                },
                vote(){
                    return Math.ceil(this.elementData.vote_average / 2);
            }
        },
        props: {
            elementData: {
                type: Object,
                default: null
            }
        }
    }
</script>




<template>
    <div>
        <ol>
          <li>
            <img :src="`https://image.tmdb.org/t/p/w342${elementData.poster_path}`" alt="">
          </li>

          <li>
            {{ elementData.title ?? elementData.name }}
          </li>

          <li>
            {{ elementData.original_title ?? elementData.original_name }}
          </li>

          <li>
            <img class="flag" :src="flag" alt="">
            
          </li>

          <li>
            <div>
                <span v-for="numero in vote">
                    ★
                </span>
                <span v-for="numero in ( 5 - vote)">
                    ☆
                </span>
            </div>
          </li>
        </ol>
    </div>
</template>




<style lang="scss">

    img{
        width: 100%;

        &.flag{
            width: 40px;
        }
       

    }

</style>