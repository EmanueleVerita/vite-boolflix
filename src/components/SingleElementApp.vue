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
            {{ Math.ceil(elementData.vote_average / 2) }}
          </li>

          <li>
            <div>
                <span v-for="numero in Math.ceil(elementData.vote_average / 2)">
                    ★
                </span>
                <span v-for="numero in ( 5 - Math.ceil(elementData.vote_average / 2))">
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