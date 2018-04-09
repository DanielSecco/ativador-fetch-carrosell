<template>
  <div class="filters">
    <div class="filter">
      <label for="autocomplete-dropdown">Autocomplete dropdown: </label>
      <autocomplete-dropdown
        id="autocomplete-dropdown"
        :options="fruitOptions"
        v-model="selectedFruit"
        placeholder="Enter"
      ></autocomplete-dropdown>
    </div>
   <div class="result">
      Selected: <strong>{{ selectedFruit}}</strong>
    </div>
  </div>
</template>
<script>
    import AutocompleteDropdown from '@/components/comps/AutocompleteDropdown'
    //var especiesNames = window.dados1[0];
    import * as conf from '@/main'
    var postData = {};
    var opt1 = {};
    // console.log(conf.list);
     readAllData('trees')
                    .then(function(data) {
                        // window.ltt= data;
                        for (var dt of data) {
                            //postData.push( [dt.name_public, dt.cod_tree]);
                            postData[dt.name_public] = dt.name_scientific;
                        };
                        //var spcicieImg = list.filter( spc => spc.cod_tree === obj.cod_tree)[0];
                        //console.log(ltt);
                       window.opt1 =  postData ;
                        console.log(postData);
                        console.log(window.opt1);
         return opt1;
                    });
    
    export default {
        components: {
            'autocomplete-dropdown': AutocompleteDropdown,
        },
        methods: {
            
        },
        mounted() {
            
            
        },
        data() {
            return {
                selectedFruit: 'Apple',
                fruitOptions: window.opt1 ,
                selectedDateRange: null
            }
        },
    }
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .filters {
        width: 800px;
        margin: 0 auto;
    }
    .filter {
        text-align: left;
    }
    .result {
        margin: 30px 0;
        text-align: left;
    }
    label {
        display: block;
    }
</style>