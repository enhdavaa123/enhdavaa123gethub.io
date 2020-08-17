# enhdavaa123gethub.io
<!DOCTYPE html>
<html>
    <head>
        <title>timer</title>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <style>
            body{
                margin: 10px;
                padding: 10px;
            }
            .container{
                width: 300px;
                height: 150px;
                background-color: rgb(168, 245, 226);
                border-radius: 10px;
                margin: 100px auto 0 auto;
                padding: 100px;
            }
            .container input{
                margin: 50px 0 0 30px;
                padding: 0;
                width: 50px;
                height: 20px;
                float: left;
            }
            .container p{
                float: left;
                margin: 50px 10px 0 20px;
                padding: 0em;
            }
            .container button{
                margin: 50px 0 0 20px;
            }
            .container div{
                width: 100px;
                margin: 20px auto 0 auto;
                text-align: center;
            }
        </style>
        <body>
            <div class="container">
                <input type="text" name="" id="myinput">
                <p>seconds</p>
                <button onclick="counting()" id="mybutton">Start</button>
                <div id="container"></div>
            </div>
            <script>
                let seconds;
                let remseconds;
                let minutes;
                let container = document.getElementById("container");
                let myinput = document.getElementById("myinput");
                let myid;
                /*var mybutton = document.getElementById("mybutton");*/
                var disabled = document.createAttribute("disabled");
                function Countdown(){
                    if(seconds >= 0){
                        remseconds = seconds % 60;
                        minuts = Math.floor(seconds / 60);
                        if(remseconds < 10){
                            remseconds = "0" + remseconds;
                        }
                        if(minuts < 10){
                            minuts = "0" + minuts;
                        }
                        container.innerHTML = minuts + " : " + remseconds;
                        if(seconds == 0)   
                        }
                        seconds--;
                        /*mybutton.setAttribute(disabled);*/
                        document.getElementById("mybutton").setAttribute("disabled", true);
                    }
                    else{
                        clearInterval(myid);
                        container.style.visibility = "hidden";
                        document.getElementById("mybutton").removeAttribute("disabled", true);
                    }
                }
                function counting(){
                    seconds = Number(myinput.value);
                    container.style.visibility = "visible";
                    if(myinput.value == ""){
                    }
                    else{
                        myinput.value = "";
                        myid = setInterval(Countdown, 1000);
                    }
                }
            </script>
        </body>
    </head>
</html>
