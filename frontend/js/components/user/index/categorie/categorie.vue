<template>
    <div id="sideSliderCats">
        <div id="sideSlidesCatsWrapper">
            <div id="hamCats">
                <ham></ham>
                دسته بندی
            </div>
            <div id="allCats">
                <ul>
                    <li v-for="(c,i) in mainCats" :key="i" class="parentLi"><arrow></arrow>  {{c.title}} 
                        <div class="subMenu">
                            <div class="subTitleWrapper">
                                <div class="SubTitle"><p>{{c.title}}</p></div>
                                <ul>
                                    <li v-for="sub in c.subs"><a :href="getUrl(sub.title)">{{sub.title}}</a></li>
                                </ul>
                            </div>
                        </div>
                    </li>
                    <!-- <li class="parentLi"> <arrow></arrow>دست1 
                    <div class="subMenu">
                            <div class="subTitleWrapper">
                                <div class="SubTitle"><p>دسته 1</p></div>
                                <ul>
                                    <li><a href="#">زیردسته 1</a></li>
                                    <li><a href="#">زیردسته 2</a></li>
                                    <li><a href="#">زیردسته 3</a></li>
                                    <li><a href="#">زیردسته4</a></li>
                                    <li><a href="#">زیردسته 5</a></li>
                                    <li><a href="#">مشاهده همه</a></li>
                                </ul>
                            </div>
                        </div>
                    </li>
                    <li class="parentLi"><arrow></arrow> دست1
                    <div class="subMenu">
                            <div class="subTitleWrapper">
                                <div class="SubTitle"><p>دسته 1</p></div>
                                <ul>
                                    <li><a href="#">زیردسته 1</a></li>
                                    <li><a href="#">زیردسته 2</a></li>
                                    <li><a href="#">زیردسته 3</a></li>
                                    <li><a href="#">زیردسته4</a></li>
                                    <li><a href="#">زیردسته 5</a></li>
                                    <li><a href="#">مشاهده همه</a></li>
                                </ul>
                            </div>
                        </div>
                    </li>
                    <li class="parentLi"><arrow></arrow> دست1 
                    <div class="subMenu">
                            <div class="subTitleWrapper">
                                <div class="SubTitle"><p>دسته 1</p></div>
                                <ul>
                                    <li><a href="#">زیردسته 1</a></li>
                                    <li><a href="#">زیردسته 2</a></li>
                                    <li><a href="#">زیردسته 3</a></li>
                                    <li><a href="#">زیردسته4</a></li>
                                    <li><a href="#">زیردسته 5</a></li>
                                    <li><a href="#">مشاهده همه</a></li>
                                </ul>
                            </div>
                        </div>
                    </li>
                    <li class="parentLi"><arrow></arrow> دست1 
                    <div class="subMenu">
                            <div class="subTitleWrapper">
                                <div class="SubTitle"><p>دسته 1</p></div>
                                <ul>
                                    <li><a href="#">زیردسته 1</a></li>
                                    <li><a href="#">زیردسته 2</a></li>
                                    <li><a href="#">زیردسته 3</a></li>
                                    <li><a href="#">زیردسته4</a></li>
                                    <li><a href="#">زیردسته 5</a></li>
                                    <li><a href="#">مشاهده همه</a></li>
                                </ul>
                            </div>
                        </div>
                    </li> -->
                    
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
    import arrow from "../../template/arrow/arrow.vue"
    import ham from "../../template/hamIcon/ham.vue"
    export default{
        components:{
            ham,
            arrow
        },
        props:['mainCats'],
        created(){
            console.log("cats",this.mainCats)
        },
        methods:{
            getUrl(url){
                return `/categories/${url}`
            }
        }
    }
</script>


<style scoped>
    ul li:hover .subMenu{
        display:block;
        animation:fadeIn 0.2s linear
    }
    @keyframes fadeIn{
        from{
            opacity:0
        }
        to{
            opacity:1;
        } 
    }
    ul li:hover{
        border-top:1px solid rgb(129, 129, 129);
        border-bottom:1px solid rgb(129, 129, 129);
    }
    .subMenu{
        position: absolute;
        display:none;
        right:100%;
        z-index:667;
        background-color: white;
        height:max-content;
        top:-20px;
        width:300px;
        border-left:1px solid rgb(223, 223, 223)
    }
    .subTitleWrapper{
        display:flex;
        flex-direction:column;
        align-items: flex-end;
        padding:10px
    }
    .subtitle{
        font-size:20pt;
    }
    .subMenu ul li a{
        font-size:12pt;
        color:rgb(71, 71, 245) !important
    }
    .arrow{
        width:20px;
        height:20px;   
    }
    #sideSlidesCatsWrapper{
        width:100%;
        padding:10px;
    }

    #sideSliderCats{
        display:flex;
        justify-content: flex-start;
        width:240px;
    }
    ul{
        width:100%
    }
    ul>li{
        line-height: 2rem;
        width:100%;
        display:flex;
        justify-content: space-between;
    }
    .subMenu li{
        display:flex;
        justify-content:flex-end
    }
    .parentLi{
        position: relative;
        font-size:20px
    }
    .parentLi:hover .subMenu{
        display:block
    }
    #hamCats{
        display:flex;
        align-items:center
    }
    @media (max-width:801px)
	{
		#sideSliderCats{
			display:none
		}
	}

</style>

