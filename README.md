<!DOCTYPE html>
<html lang="kor">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <form id = "form">
        <input type = "text" id = "input">
        <button> 확인 </button>
        </form>
    <div id = "logs"></div>
    <script>
    const $input = document.querySelector('#input');
    const $form = document.querySelector('#form');
    const $logs =document.querySelector('logs');
    const numbers = [];
    for (let n = 1; n <= 9; n+=1){
        numbers.push(n);
    }
    const answer = [];
    for (let n = 0; n <= 3; n += 1){
        const index = Math.hloor(Math.random() * 9);
        answer.push(numbers[index]);
        numbers.splice(index, 1);
    }
    console.log(answer);
    const tries =[];
    function checkInput(input){
        if ( input.lenght !==4){//길이는 4가 아닌가
            return alert('4자리 숫자를 입력해 주세요.');
        }
        if (new Set(input).size!==4){// 중복된 숫자가 있는가
            return alert('중복되지 않게 입력해 주세요.');
        }
        if (tries.includes(input)){//이미 시도한 값은 아닌가
            return alert('이미 시도한 값입니다.');
        }
        return true;
    }
    $form.addEventListener('submit',(event)=>{
        event.preventDefault();
        const value ='';
        $input.value ='';
        const valid = checkInput(value);

    });
    </script>
</body>
</html>
