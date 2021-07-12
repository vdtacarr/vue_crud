<template>
    <div id="list">
        <p v-if="products.length == 0">Ürün Listesi Boş</p>
        <table  v-else class="table">
            <thead>
                <tr>
                    <th>
                        Id
                    </th>
                    <th>Ürün Adı</th>
                    <th>Kategori</th>
                    <th>Açıklama</th>
                    <th>Birim Fİyat</th>
                    <th>Stok Adedi</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for = "product in products" :key="product.id">
                    <td v-if="updateId===product.id">
                        <input v-model="product.id" type="text" class="form-control" id ="id">
                    </td>
                    <td v-else>
                        {{product.id}}
                    </td>
                    <td>{{product.categoryId}}</td>
                    <td>{{product.productName}}</td>
                    <td>{{product.quantityPerUnit}}</td>
                    <td>{{product.unitPrice}}</td>
                    <td>{{product.unitsInStock}}</td>
                    <td>
                        <button class="btn btn-sm btn-primary" @click="handleUpdate(product)">GÜncelle</button>
                        <button class="btn btn-sm btn-danger" @click="handleDelete(product)">Sİl</button>
                    </td>

                </tr>
            </tbody>

        </table>
    </div>
</template>
<script>
export default {
    name:"product-list",
    data(){
        return{
            updateId:null
            }
            },
    props:{
        products:Array
    },
    methods:{
        handleDelete(product){
            this.$emit("delete:product",product);

        },
        handleUpdate(product){
            this.updateId === product.id 
        }
        

        }
    
}

</script>

<style scoped>
#list{
    margin: 100px;
}
</style>