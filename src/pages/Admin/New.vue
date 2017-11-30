<template>
  <product-form @save-product="addProduct" :model="model" :manufacturers="manufacturers" :isEditing="false"></product-form>
</template>

<script>
import ProductFrom from '../../components/product/ProductForm.vue';

export default {
  name : 'New',
  data(){
    return {
      model : {},
       manufacturers: [
          {
            _id: 'sam',
            name: 'Samsung',
          },
          {
            _id: 'apple',
            name: 'Apple',
          },
        ],
    }
  },
  methods : {
    addProducts(model){
      console.log('model', model);
    }
  },
  components: {
      'product-form': ProductFrom
    }
}

</script>
