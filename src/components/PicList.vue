<template>

    <div>
        名称：<input type="text" style="line-height: 30px" placeholder="请输入名称" v-model="keyWord">
    </div>

    <div class="" id="box">
        <ul>
            <li v-for="v in filterFruitList" :key="v.id">
                <img v-bind:src="v.src" alt="">
                <h4>名称：{{ v.picName }}</h4>
            </li>
        </ul>
    </div>

</template>

<script>
export default {
    name: "PicList",
    data() {
        return {
            keyWord: '',
            // 模拟数据, 可使用
            list: [
                {
                    id: 1,
                    src: require('../assets/pic/1.jpg'),
                    picName: 'abc',
                },
                {
                    id: 2,
                    src: require('../assets/pic/2.jpg'),
                    picName: 'aghh',
                },
                {
                    id: 3,
                    src: require('../assets/pic/3.jpg'),
                    picName: 'hfhc',
                },
                {
                    id: 4,
                    src: require('../assets/pic/4.jpg'),
                    picName: 'urur',
                },
                {
                    id: 5,
                    src: require('../assets/pic/5.jpg'),
                    picName: 'hjgnh',
                },
                {
                    id: 6,
                    src: require('../assets/pic/6.jpg'),
                    picName: 'jfgbnxf',
                },
                {
                    id: 7,
                    src: require('../assets/pic/7.jpg'),
                    picName: 'jfja',
                },
                {
                    id: 8,
                    src: require('../assets/pic/8.jpg'),
                    picName: 'itydit',
                },
                {
                    id: 9,
                    src: require('../assets/pic/9.jpg'),
                    picName: 'zsdvzdf',
                }
            ]

        }
    },
    computed: {
        filterFruitList() {
            return this.list.filter((item) => {
                return item.picName.indexOf(this.keyWord) !== -1;
            })
        }
    },

}
</script>

<style scoped>

#box ul {
    display: flex;
    flex-wrap: wrap;
    position: absolute;
    top: 200px;
}

#box li {
    padding: 3px;
    list-style: none;
    margin-right: 15px;
    border: 1px solid #eee;
}

#box img {
    width: 200px;
    height: 150px;
}


</style>