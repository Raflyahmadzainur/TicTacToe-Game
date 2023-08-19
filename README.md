<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kotak</title>
</head>
<body style="background-size: cover; background-color: slategray;" >
    <div style="background-color: silver; width: 400px; height: auto; text-align: center; margin: auto; margin-top: 100px;">
        <br><h1>TIC TAC TOE</h1>
        <table border="1" style="margin: auto;"><br>
            <tr>
                <td id="k0" onclick="choose(0)" style="height: 50px; width: 50px;"></td>
                <td id="k1" onclick="choose(1)" style="height: ;50px width: 50px;"></td>
                <td id="k2" onclick="choose(2)" style="height: 50px; width: 50px;"></td>
            </tr>
            <tr>
                <td id="k3" onclick="choose(3)" style="height: 50px; width: 50px;"></td>
                <td id="k4" onclick="choose(4)" style="height: 50px; width: 50px;"></td>
                <td id="k5" onclick="choose(5)" style="height: 50px; width: 50px;"></td>
            </tr>
            <tr>
                <td id="k6" onclick="choose(6)" style="height: 50px; width: 50px;"></td>
                <td id="k7" onclick="choose(7)" style="height: 50px; width: 50px;"></td>
                <td id="k8" onclick="choose(8)" style="height: 50px; width: 50px;"></td>
            </tr>
        </table><br><p style="margin: auto;">CURRENT PLAYER : <span id="player"></span> </p>
        <br><br>
    </div>
    <script>
    var player = 0
    var namaplayer = ['X', 'O']
    var arr = ['', '', '', '', '', '', '', '', '']
    function choose(box){
        elem = document.getElementById('k'+box)
        if (elem.textContent != ""){
            alert("Already Filled")
            return
        }
        if (player == 0 ){
            elem.textContent = "X"
            player = 1
            arr[box] = "X"
        }
        else
        {
            elem.textContent = "O"
            player = 0
            arr[box] = "O"
        }

        var win = [[0,1,2],[3,4,5],[6,7,8],[0,3,6],[1,4,7],[2,5,8],[1,4,8],[2,4,6]]
        for(let x of win){
            if (arr[x[0]]=="X"&&arr[x[1]]=="X"&&arr[x[2]]=="X"){
            alert("Player 1 Win")
        }if (arr[x[0]]=="O"&&arr[x[1]]=="O"&&arr[x[2]]=="O"){
            alert("Player 2 Win")
        }
    }
    document.getElementById('player').textContent = namaplayer[player]
    }
    </script>
</body>
</html>
