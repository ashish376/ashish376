//This is a code of project
// html part
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tom&jerry Game  </title>
    <link rel= "Stylesheet" href="C:\Users\Ashish\Desktop\style.css">
    <script src="C:\Users\Ashish\.vscode\script.js"></script>

</head>
<body>
   <div class="gamecontainer">
       <div class="gameOver">Game Over</div>
       <div class="Jerry"></div>
       <div id="scorecount">Your score: 0</div>
       <div class="obstacle obstacleAni">
       
       </div>

       </div>

</body>
</html>

//CSS Part
*{
    margin:0;
    padding:0;
}
body{
    background-color: red;
    overflow: hidden;

}
.gamecontainer{
    background-image:url(13179.jpg);
    background-repeat: no-repeat;
    background-size: 200vw 100vh;
    width:200%;
    height:200vh;
}
.Jerry{
    background-image:url(jerry.png);
    background-repeat: no-repeat;
    background-size: cover;
    width:333px;
    height: 600px;
    position: absolute;
    bottom:0;
    left:550px;
}
.obstacle{
    width:266px;
    height: 300px;
    background-image: url(tom.png);
    background-size: cover;
    position: absolute;
    bottom:0;
    left :1vw;
}
.animateJerry{
    animation: Jerry 0.6s linear;

}
.obstacleAni{
    animation: obstacleAni 5s linear infinite;
}
.gameOver{
    visibility:hidden;
}
@keyframes Jerry{
    0%{
        bottom:0;
    
    }
    50%{
        bottom:422px;
    }
    100%{
        bottom:0%;
    }
}
@keyframes obstacleAni{
    0%{
        left:200vw;
    
    }
    100%{
        bottom:-1vw;
    }
}

//Javascript part
document.onkeydown = function(e){
    console.log("key code is:",e.keyCode)
    if(e.keyCode==38){
        Jerry= document.querySelector('.Jerry');
        Jerry.classList.add('animateJerry');
        setTimeout(() => {
            Jerry.classList.remove('animateJerry')
        }, 700);
        
        }
        if(e.keyCode==39){
            Jerry = documentquerySelector('.Jerry');
            JerryX = parseInt((window.getComputedStyle(Jerry,null).getPropertyValue('left'));
            Jerry.style.left = JerryX + 112 + "px";
    
    }
}
setInterval(() => {
    Jerry = document.querrySelector('.Jerry');
    gameOver = document.querySelector('.gameOver');
    obstacle = doccument.querySelector('.obstacle');
   
    dx = parseInt(window.getComputedStyle(Jerry,null).getPropertyValue('left'));
    dx =parseInt( window.getComputedStyle(Jerry,null).getPropertyValue('top'));

    ox =parseInt( window.getComputedStyle(obstacle,null).getPropertyValue('left'));
    ox = parseInt(window.getComputedStyle(obstacle,null).getPropertyValue('top'));

    offsetX = Math.abs(ds-ox);
    offsetY = Math.abs(dy-oy);
    console.log(offsetX, offsetY)
    if(offsetX< 93 && offsetY<52){
        gsmeOver.style.visibility ='viisible';
        obstacle.classList.remove('obstacleAni')
        obstacle.classList.remove('obstacleAni')
    }
}, 100);
