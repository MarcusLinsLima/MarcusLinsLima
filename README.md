<!DOCTYPE html>
<html lang="pt-BR">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        body {
            font: normal 25pt Arial;
            background-color: black;
            color: rgb(28, 36, 191);
            text-align: center;
            line-height: 100px;
        }

        input#botao {
            color: red;
            background-color: black;
        }
    </style>
</head>

<body>
    <input id="botao" type="button" value="CLIQUE AQUI PARA SABER O DIA DA SEMANA E A HORA EXATA" onclick="momento()"
        onmouseenter="entrar()" onmouseout="sair()">

    <div id="semana">
        Dia da semana
    </div>
    <div id="time">
        Hora exata
    </div>
    <div id="novoResultado"></div>

    <script>
        var novo = document.getElementById('novoResultado')
        var b = document.getElementById('botao')
        function entrar() {
            if (momento == true && diaSem == true && entrar == true) {
                b.style.color = 'black'
            }

        }

        var feira = new Date()
        var diaSem = feira.getDay()
        var agora = new Date()
        var hora = agora.getHours()
        var minutos = agora.getMinutes()
        var txt = document.getElementById('time')
        var txt02 = document.getElementById('semana')
        function momento() {
            b.style.backgroundColor = 'black'
            b.style.color = 'black'

            switch (diaSem) {
                case 0:
                    txt02.innerHTML = '<strong>DOMINGO</strong>'
                    break;
                case 1:
                    txt02.innerHTML = '<strong>SEGUNDA-FEIRA</strong>'
                    break;
                case 2:
                    txt02.innerHTML = '<strong>TERÇA-FEIRTA</strong>'
                    break;
                case 3:
                    txt02.innerHTML = '<strong>QUARTA-FEIRA</strong>'
                    break;
                case 4:
                    txt02.innerHTML = '<strong>QUINTA-FEIRA</strong>'
                    break;
                case 5:
                    txt02.innerHTML = '<strong>SEXTA-FEIRA</strong>'
                    break;
                case 6:
                    txt02.innerHTML = '<strong>SÁBADO-FEIRA</strong>'
                    break
            }

            if (hora >= 0 && hora < 12) {
                txt.innerHTML = (` ${hora} horas e ${minutos} minutos<br><strong> BOM DIA!</strong>`)
            }
            else if (hora < 18) {
                txt.innerHTML = (`${hora} horas e ${minutos} minutos,<strong> BOA TARDE!</strong>`)
            } else {
                txt.innerHTML = (`${hora} horas e ${minutos} minutos,<strong>BOA NOITE!</strong>`)
            }

            novo.innerHTML = 'Para um novo resultado digite (F5)'
        }

    </script>
</body>

</html>
