    <template>
        <div>
            <div class="compent">
                <div v-for="(item,index) in list" :key="index">
                    <div class="tree-title">
                        {{item.table}}
                    </div>
                <div class="tree-children" v-if="item.nodes">
                    <trees-compt :list="item.nodes"> </trees-compt>
                </div>
                </div>
            </div>
        </div>
    </template>
    
    <script>
        export default {
            name:"TreesCompt",
            props:{
                list:Array
            }
        }
    </script>
    
    <style scoped>
    .tree-title{
        cursor: pointer;
        text-align: left;
        background: #666;
        margin-top: 8px;
        line-height: 20px;
        width:fit-content;
       border-radius: 10%;
       font-size: 14px;
       padding: 2px 8px 2px 8px;
    }
    .tree-children{
        margin-left: 20px;
    }
    </style>