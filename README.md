<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Analog-Watch-Project</title>
</head>
<style>
    
    *{
        margin: 0;
        padding: 0;
        list-style: none;
        text-decoration: none;
        outline: none;
        scroll-behavior: smooth;
        color: inherit;
    }

    section {
        position: relative;
        height: 100vh;
        width: 100%;
        overflow: hidden;
        background-size: cover;
    }

    .clock {
        position: absolute;
        top: 10%;
        left: 27%;
        height: 500px;
        width: 500px;
        border-radius: 50%;
        border: 1px solid black;
    }

    .clock img {
        height: 100%;
        width: 100%;
    }

    .needles {
        position: absolute;
        height: 0.5px;
        width: 35%;
        top: 49%;
        transform-origin: 100%;
        left: 14%;
        z-index: 1;
    }

   

    .sec{
        background-color: red;
        height: 3px;
    }

    .min{
        background-color: grey;
        height: 5px;
    }

    .hour{
        background-color: black;
        height: 1vh;
    }

    span{
        position: absolute;
        height: 4vh;
        width: 2vw;
        background-color: red;
        left: 47.5%;
        top: 47.5%;
        border-radius: 50%;
        z-index: 2;
    }

    ul{
        position: absolute;
        top: 54%;
        left: 26%;
        list-style: none;
        display: flex;
        align-items: center;
        justify-content: space-evenly;
        height: 10vh;
        width: 20vw;
        border-radius: 3px;
        background-color: #323232;
    }

    ul li{
        height: 100%;
        width: 100%;
        color: white;
        text-align: center;
        line-height: 60px;
        text-transform: uppercase;
        border-radius: 10px;
        font-size: 2.3rem;
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    }

</style>

<body>

    <section>

        <div class="clock">

            
          <img src="https://w7.pngwing.com/pngs/980/515/png-transparent-clock-face-analog-clock-without-hands-angle-white-text-thumbnail.png" alt="its a clock pic">      

            <span></span>
            
            <div class="needles sec"></div>
            <div class="needles min"></div>
            <div class="needles hour"></div>

            <ul>

                <li></li>

            </ul>

        </div>

    </section>
    

</body>
<script>

    setInterval(time, 1)

    function time() {
        var date = new Date()
        var m_sec_n = document.querySelector(".ms");
        var sec_n = document.querySelector(".sec");
        var sec = date.getSeconds();
        var new_sec = ((sec / 60) * 360 + 90);
        sec_n.style.transform = `rotate(${new_sec}deg)`;
        var min_n = document.querySelector(".min");
        var min = date.getMinutes();
        var new_min = ((min / 60) * 360 + 90);
        min_n.style.transform = `rotate(${new_min}deg)`;
        var hour_n = document.querySelector(".hour");
        var hour = date.getHours();
        var new_hour = ((hour / 12) * 360 + 90 + (0.5 * min));
        hour_n.style.transform = `rotate(${new_hour}deg)`;
        var clock_date=document.querySelector("li");
        var din=date.toDateString();
        clock_date.innerHTML=`${din} `
    }

</script>

</html>
