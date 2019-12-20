<template>
    <div>
        <h1 style="margin-top:20px;text-align: left;margin-left: 80px">豆瓣电影排行榜</h1>
        <el-row style="text-align: left;margin-top: 30px ;color: #072;margin-left: 80px">
            <el-col :span="16">
                <span class="title-col" >豆瓣新片榜· · · · · ·</span>
            </el-col>
        </el-row>
        <el-col><hr/></el-col>
        <el-row v-for="movie in movieList">
            <el-col>
                <h1><img v-bind:src="movie.imgUrl"/></h1>
                <h2 class="title">{{movie.title}}</h2>
                <el-row>
                    <el-col span="16">
                        <div class="N">
                            <span >{{movie.actor}}</span>
                        </div>
                    </el-col>
                </el-row>
                <el-row>
                    <el-col span="16">
                        <div class="score">
                            <div style="display: inline-block">
                                <el-rate disabled v-model="movie.scoring"></el-rate>
                            </div>
                            <span style="color:#e09015">{{movie.score}}</span>
                            <span>({{movie.amount}}人评分)</span>
                        </div>
                    </el-col>
                </el-row>

            </el-col>
            <el-col style="margin-top: 20px"><hr/></el-col>
        </el-row>

    </div>
</template>
<script>
    export default {
        data() {
            return {
                movieList:[
                    {
                        title:'爱尔兰人 / 爱尔兰杀手(港) / 听说你刷房子了',
                        imgUrl:require('../assets/p/1.jpg'),
                        actor:'2019-09-27(纽约电影节) / 2019-11-01(美国点映) / 2019-11-27(美国网络) / 罗伯特·德尼罗 / 阿尔·帕西诺 / 乔·佩西 / 安娜·帕奎因 / 杰西·普莱蒙 / 哈威·凯特尔 / 斯蒂芬·格拉汉姆 / 鲍比·坎纳瓦尔 / 杰克·休斯顿 / 阿莱卡萨·帕拉迪诺 / 凯瑟琳·纳杜奇...',
                        scoring:4.5,
                        score:9.1,
                        amount:'48114'
                    },
                    {
                        title:'小丑 / 小丑起源电影：罗密欧 / Romeo',
                        imgUrl:require('../assets/p/2.jpg'),
                        actor:'2019-08-31(威尼斯电影节) / 2019-10-04(美国) / 杰昆·菲尼克斯 / 罗伯特·德尼罗 / 马克·马龙 / 莎姬·贝\n' +
                            '兹 / 谢伊·惠格姆 / 弗兰西丝·康罗伊 / 布莱恩·考伦 / 布莱恩·泰里·亨利 / 布莱特·卡伦 / 道格拉斯·霍\n' +
                            '奇斯 / 格伦·弗莱施勒 / 比尔·坎普...',
                        scoring:4.5,
                        score:8.8,
                        amount:'392795'
                    },
                    {
                        title:'82年生的金智英 / 82年生金智英 / Kim Ji-young,Born 1982',
                        imgUrl:require('../assets/p/3.jpg'),
                        actor:'2019-10-23(韩国) / 2019-11-07(中国香港) / 郑有美 / 孔侑 / 金美京 / 孔敏晶 / 朴成妍 / 李凤莲 / 金圣喆\n' +
                            '/ 李乌 / 李海云 / 孙成灿 / 金正英 / 李娜云 / 禹志贤 / 韩国 / 金度英 / 118分钟 / 82年生的金智英\n' +
                            '/ 剧情 / 刘英雅 Yeong-ah Yoo / 赵南珠 Nam-joo...',
                        scoring:4.4,
                        score:8.7,
                        amount:'64909'
                    },
                    {
                        title:'好莱坞往事 / 从前，有个荷里活(港) / 从前，有个好莱坞...(台)',
                        imgUrl:require('../assets/p/4.jpg'),
                        actor:'2019-05-21(戛纳电影节) / 2019-07-26(美国) / 2019(中国大陆) / 莱昂纳多·迪卡普里奥 / 布拉德·皮特\n' +
                            '/ 玛格特·罗比 / 埃米尔·赫斯基 / 玛格丽特·库里 / 蒂莫西·奥利芬特 / 茱莉亚·巴特斯 / 奥斯汀·巴特勒 / ' +
                            '达科塔·范宁 / 布鲁斯·邓恩 /...',
                        scoring:3.5,
                        score:7.3,
                        amount:'81405'
                    },
                    {
                        title:'婚姻故事/Marriage story',
                        imgUrl:require('../assets/p/5.jpg'),
                        actor:'2019-08-29(威尼斯电影节) / 2019-12-06(美国) / 斯嘉丽·约翰逊 / 亚当·德赖弗 / 梅里特·韦弗 / 劳拉·邓\n' +
                            '恩 / 雷·利奥塔 / 朱丽·哈基提 / 马克·奥布莱恩 / 华莱士·肖恩 / 阿伦·阿尔达 / 凯尔·柏海莫 / 米奇·萨姆纳 ' +
                            '/ 艾奇·罗伯逊 / 马修·马希尔...',
                        scoring:4.5,
                        score:8.8,
                        amount:'41350'
                    },
                    {
                        title:'准备好了没 / 弑婚游戏(台) / 爆血新婚夜(港)',
                        imgUrl:require('../assets/p/6.jpg'),
                        actor:'2019-08-21(美国) / 萨玛拉·维文 / 安迪·麦克道威尔 / 马克·奥布莱恩 / 亚当·布罗迪 / 亨利·科泽尼 / 妮\n' +
                            '基·瓜达尼 / 梅兰妮·斯科洛凡诺 / 克里斯蒂安·布鲁恩 / 伊利斯 莱韦斯克 / 约翰·拉尔斯顿 / 达妮埃拉·巴博萨 /' +
                            ' 伊拉娜·盖尔 /...',
                        scoring:3.4,
                        score:6.7,
                        amount:'29589'
                    },
                    {
                        title:'克劳斯：圣诞节的秘密 / 圣诞老人',
                        imgUrl:require('../assets/p/7.jpg'),
                        actor:'2019-11-08(西班牙) / 2019-11-08(英国) / J·K·西蒙斯 / 詹森·舒瓦兹曼 / 拉什达·琼斯 / 琼·库萨克 / 诺\n' +
                            '曼·麦克唐纳徳 / 威尔·萨索 / 塞尔希奥·巴勃罗斯 / 米拉·布雷纳 / 内达·玛格丽特·拉巴 / 悉尼·布朗 / 泰迪·布鲁' +
                            '姆 / 艾玛·香农 / 肯德尔·卓依...',
                        scoring:4.5,
                        score:8.6,
                        amount:'8887'
                    },
                ]
            }
        }
    }
</script>
<style scoped>
    img{
        float: left;
        margin-left: 80px;
        width: 180px;
        height: 230px;
    }
    .title{
        float: left;
        margin-left: 100px;
        color:#3377aa;
        font-size: 20px;
    }
    .N{
        margin-top: 20px;
        font-size: 16px;
        margin-left:100px;
    }
    .score{
        margin-left: 150px;
        margin-top: -50px;
    }
</style>

