# Digital_Clock

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Digital_Clock</title>

    <style>
        .ids{
            width: 300px;
            height: 300px;
            border: 1px solid black;
            background-color: white;
            
            display: flex;
            align-items: center;
            justify-content: center;
            box-sizing: border-box;
            border-radius: 150px;
            font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
            transition: 0.2s;
        }
        .ids:hover{
            box-shadow: 0px 0px 25px;
            background-color: black;
            color: beige;
            
        }

        .m_d{
            box-sizing: border-box;
            text-align: center;
        
        }

        
        .maindivv{
            height: 500px;
            width: 100%;
            border: 2px solid black;
            display: flex;
            justify-content: space-around;
            align-items: center;
            flex-direction: column;
        }

        .date{
            transition: 0.2s;
        }
        .date:hover{
            color: yellow;
            transform: scale(1.1);
        }

        .time{
            transition: 0.2s;
        }
        .time:hover{
            color: yellow;
            transform: scale(1.1);
        }

        .day{
            transition: 0.2s;
        }

        .day:hover{
            color: yellow;
            transform: scale(1.1);
        }
      
        .head{
            font-family:'Gill Sans', 'Gill Sans MT', 'Trebuchet MS';
            text-decoration: underline;
            font-size: 25px;
        }
    </style>
</head>

<body>
    <div class="maindivv">
        <div class="head">
            <h1>-:Digital Clock:-</h1>
        </div>
        
       
        <div class="ids">
            <div class="m_d">    
                <div class="date">
                    <h1 id="date"></h1>
                    <h1 id="month"></h1>
                    <h1 id="year"></h1>
                </div>
                
                <div class="time">
                    <h1 id="hrs"></h1>
                    <h1 id="mins"></h1>
                    <h1 id="secs"></h1>
                    <h1 id="am_pm"></h1>
                </div>
                 
                <div class="day">
                    <h1 id="day"></h1>
                </div>
            </div>
        </div>
    </div>
        
        
    <script>

        function digital_clock(){

            let d = new Date()
            let date = d.getDate()
            let day_ = d.getDay()
            let month = d.getMonth() + 1
            let year = d.getFullYear()

            let hours = d.getHours()
            let minutes = d.getMinutes()
            let seconds = d.getSeconds()
            let am_pm = "AM"

            if(hours>=12){
                if(hours>12){
                    hours -= 12
                    am_pm = "PM"
                }
            }

            else if(hours == 12){
                am_pm = "AM"
            }

            month = month<10 ? "0" + month:month   
            hours = hours<10 ? "0" + hours:hours   
            minutes = minutes<10 ? "0" + minutes:minutes   
            seconds = seconds<10 ? "0" + seconds:seconds   

            const fdate = (`${date}:${month}:${year}`)
            const ftime = (`${hours}:${minutes}:${seconds} ${am_pm}`)

            document.getElementById("date").innerHTML = fdate
            document.getElementById("hrs").innerHTML = ftime

            let days = ['Sunday','Monday','Tuesday','Wednesday','Thursday','Friday','Saturday']
            let t_day = days[day_]
            document.getElementById("day").innerHTML = t_day

        }   
        setInterval(digital_clock, 1000)
        digital_clock()

        
        // let a = setTimeout(function(){
        //     alert ("This is showing Time and Date")
        // },5000)
        // let b = prompt("Do you want to run setime out again?, Y/N")
        // if(b == "n" || b == "N")
        // {
        //     clearTimeout(a)
        // }

        </script>

</body>

</html>
