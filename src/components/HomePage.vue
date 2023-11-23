<template>
    <head>
        <title>Jakub Borkowski - Studia</title>
    </head>
            <br>
            <div class="show">
                <div class="box">
                    <img src="@/assets/prof.jpg" alt="" class="box-img">\
                    <h1>{{ name }}</h1>
                    <h5>{{ graduateTitle }}</h5>
                    <p>{{ description }}</p>
                    <ul>
                        <li>
                            <a href="https://www.facebook.com/jakub.borkowski.319/" target="_blank">
                                <font-awesome-icon icon="fa-brands fa-square-facebook" class="icon-cog" size="4x"/>
                            </a>
                        </li>
                        <li>
                            <a href="https://twitter.com/betonMonster" target="_blank">
                                <font-awesome-icon icon="fa-brands fa-twitter" class="icon-cog" size="4x"/>
                            </a>
                        </li>
                        <li>
                            <a href="https://www.instagram.com/kubskozak/" target="_blank">
                                <font-awesome-icon icon="fa-brands fa-instagram" class="icon-cog" size="4x"/>
                            </a>
                        </li>
                        <li>
                            <a href="https://github.com/JakupBorkowski" target="_blank">
                                <font-awesome-icon icon="fa-brands fa-github" class="icon-cog" size="4x"/>
                            </a>
                        </li>
                        <li>
                            <a href="mailto:jakub.zdzislaw.borkowski@gmail.com" target="_blank">
                                <font-awesome-icon icon="fa-brands fa-google" class="icon-cog" size="4x"/>
                            </a>
                        </li>
                        <li>
                            <a href="https://www.linkedin.com/in/jakub-borkowski-341a45242/" target="_blank">
                                <font-awesome-icon icon="fa-brands fa-linkedin" class="icon-cog" size="4x"/>
                            </a>
                        </li>
                    </ul>
    
    
                </div>
                

            </div>
            
            <br>
            <div class="show">
                <div class="box2">
                    <h5>POZNANE TECHNOLOGIE</h5>
                    <ul>
                        <li><a><img name = "slide1" src="technologies/css-3.png"></a></li>
                        <li><a><img name = "slide2" src="technologies/python.png"></a></li>
                        <li><a><img name = "slide3" src="technologies/c-.png"></a></li>
                        <li><a><img name = "slide4" src="technologies/c-sharp.png"></a></li>
                        <li><a><img name = "slide5" src="technologies/js.png"></a></li>
                        <li><a><img name = "slide6" src="technologies/mysql.png"></a></li>
                        <li><a><img name = "slide7" src="technologies/java.png"></a></li>
                        <li><a><img name = "slide8" src="technologies/docker.png"></a></li>
                    </ul>
                </div>
            </div>
            <br>
</template>


<script>

export default {
    methods:{
        moveTechnologies: function(){
            let tmpI = this.i;
            let tmpITab =[];
            tmpITab.push(tmpI);
            for(let k = 0; k < 8; k++)
            {
                tmpI = tmpI + 1;
                if(tmpI <= this.images.length - 1)
                {
                    tmpITab.push(tmpI);
                }
                else
                {
                    tmpI = 0;
                    tmpITab.push(tmpI);
                }
            }
            if(this.i < this.images.length - 1)
            {
                this.i++;
            }
            else{
                this.i=0;
            }
            document.getElementsByName("slide1")[0].src=this.images[tmpITab[0]];
            document.getElementsByName("slide2")[0].src=this.images[tmpITab[1]];
            document.getElementsByName("slide3")[0].src=this.images[tmpITab[2]];
            document.getElementsByName("slide4")[0].src=this.images[tmpITab[3]];
            document.getElementsByName("slide5")[0].src=this.images[tmpITab[4]];
            document.getElementsByName("slide6")[0].src=this.images[tmpITab[5]];
            document.getElementsByName("slide7")[0].src=this.images[tmpITab[6]];
            document.getElementsByName("slide8")[0].src=this.images[tmpITab[7]];

            this.timeoutId = setTimeout(this.moveTechnologies, this.slideDelay)
        }
    },
    mounted(){
        this.moveTechnologies();
    },
    beforeRouteLeave(){
        clearTimeout(this.timeoutId);
        console.log("opuszczam routa z homepage'a");
    },
    data(){
        return{
            timeoutId: null,
            i: 0,
            slideDelay: 1000,
            name: "Jakub Zdzisław Borkowski",
            graduateTitle: "Magister Inżynier Automatyki i Robotyki",
            description: "Witaj! Jestem Kuba i aktualnie zakończyłem studia magisterskie na Politechnice Poznańskiej. Kierunek, który studiuję to Automatyka i Robotyka. Poza uczelnią pracuję jako Automatyk, Robotyk, Elektryk w firmie Ster-projekt. Swój wolny czas staram się spędzać aktywnie. Kocham wspinaczki górskie i jestem klientem wielu poznańskich siłowni. Dodatkowo lubię poprogramować. Prawdopodobnie to sprawiło, że własnie to czytasz. Jeżeli chcesz dowiedzieć się czegoś więcej o mnie skorzystaj z odnośników poniżej.",    
            images:['technologies/css-3.png',
                    'technologies/python.png',
                    'technologies/c-.png',
                    'technologies/c-sharp.png',
                    'technologies/js.png',
                    'technologies/mysql.png',
                    'technologies/java.png',
                    'technologies/docker.png',
                    'technologies/raspberry-pi.png',
                    'technologies/Icon-SOLIDWORKS-Electrical.png',
                    'technologies/tia.jpg',
                    'technologies/vsc.png',
                    'technologies/vs.png',
                    'technologies/gt3.png',
                    'technologies/gx3.png'
                ]
        }
    },
}

</script>


<style>

.icon-cog{
    color: white;
}
.icon-cog:hover{
    color: rgba(71.4,200.4,242.9,1);
}
.font-awesome-icon{
    width:200px;
    height:200px;
}

.box, .box2, .box-ang{
    max-width: 900px;
    background-color: rgba(0,0,0,0.4);
    padding-top: 10px;
    padding-left: 40px;
    padding-right: 40px;
    border-radius: 50px;;
    text-align: center;
    /*margin-top: 1%;*/
    
    color: white;

    font-family: 'Century Gothic', sans-serif;
    line-height: 1.9;
}

.box-img{
    border-radius: 50%;
    width:200px;
    height:200px;
}

.box h1,
.box2 h1,
.box-ang h1{
    font-size: 40px;
    letter-spacing: 3px;
    font-weight: 100;
}

.box h5,
.box2 h5,
.box-ang h5{
    font-size: 25px;
    letter-spacing: 2px;
    font-weight: 100;
}

.box p,
.box2 p,
.box-ang p{
    text-align: justify;
}

.box ul,
.box2 ul,
.box-ang ul{
    margin:0;
    padding: 0;
    width: auto;

}

.box li,
.box-ang li,
.box2 li{
    display:inline-block;
    margin: 10px;
    list-style: none;
}

.box li a i,
.box-ang li a i,
.box2 li a i{
    color: white;
    text-decoration: none;
    font-size: 60px;
}

.box li a i:hover,
.box-ang li a i:hover,
.box2 li a i:hover
{
    color: rgba(71.4,200.4,242.9,1);
}

.box li a img,
.box-ang li a img,
.box2 li a img
{
    color: white;
    width: 85px;
    height: 85px;
}

.hidden{
    opacity: 0;
    filter:blur(5px);
    transition: all 1s;
}

.show{
    opacity: 1;
    filter: blur(0);
}

</style>