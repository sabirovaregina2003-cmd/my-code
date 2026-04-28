[my code.html](https://github.com/user-attachments/files/27154451/my.code.html)
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Интерактивный рабочий лист: Несовместные события | 8 класс</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background: #eef2fa;
            font-family: 'Segoe UI', 'Roboto', 'Helvetica Neue', sans-serif;
            padding: 30px 20px;
            color: #1a2c3e;
        }

        .worksheet {
            max-width: 1100px;
            margin: 0 auto;
            background: white;
            border-radius: 44px;
            box-shadow: 0 25px 45px -12px rgba(0, 0, 0, 0.2);
            overflow: hidden;
            padding: 26px 32px 42px;
        }

        h1 {
            font-size: 2rem;
            margin-bottom: 5px;
            color: #0b3b4f;
            display: flex;
            align-items: center;
            flex-wrap: wrap;
            gap: 12px;
        }

        .grade-badge {
            background: #ffaa44;
            font-size: 1rem;
            padding: 4px 16px;
            border-radius: 60px;
            font-weight: 500;
        }

        .subhead {
            border-left: 5px solid #2c7a6e;
            padding-left: 20px;
            margin: 15px 0 28px 0;
            font-weight: 500;
            color: #2c6979;
        }

        .student-info {
            background: #f3fafe;
            border-radius: 36px;
            padding: 18px 26px;
            margin-bottom: 28px;
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            align-items: center;
            border: 1px solid #cde0ec;
        }
        .student-field {
            flex: 1;
            min-width: 180px;
        }
        .student-field label {
            font-weight: 600;
            display: block;
            margin-bottom: 6px;
            color: #1f6392;
        }
        .student-field input {
            width: 100%;
            padding: 10px 14px;
            border-radius: 40px;
            border: 1px solid #b9d0e0;
            font-size: 0.95rem;
        }

        .task {
            background: #ffffff;
            border-radius: 32px;
            margin-bottom: 34px;
            border: 1px solid #e2edf5;
        }

        .task-header {
            background: #f3f8fe;
            padding: 16px 26px;
            border-radius: 32px 32px 0 0;
            font-weight: 700;
            font-size: 1.3rem;
            border-bottom: 2px solid #cde0ec;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .task-num {
            background: #1f6392;
            color: white;
            width: 36px;
            height: 36px;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            border-radius: 40px;
        }

        .task-body {
            padding: 22px 28px 28px;
        }

        .quiz-item {
            background: #fefcf7;
            margin: 18px 0;
            padding: 12px 20px;
            border-radius: 24px;
            border-left: 6px solid #89b9d3;
        }

        .truefalse-row {
            display: flex;
            gap: 28px;
            margin-top: 12px;
            flex-wrap: wrap;
        }

        .tf-option {
            display: flex;
            align-items: center;
            gap: 8px;
            cursor: pointer;
            font-weight: 500;
        }

        button, .check-task {
            background: #1f6392;
            border: none;
            color: white;
            padding: 8px 20px;
            border-radius: 40px;
            font-weight: 600;
            font-size: 0.85rem;
            cursor: pointer;
            margin-top: 18px;
            margin-right: 14px;
            transition: 0.1s;
        }

        button:hover, .check-task:hover {
            background: #0f4d72;
            transform: translateY(-1px);
        }

        .feedback {
            margin-top: 14px;
            padding: 10px 18px;
            border-radius: 28px;
            background: #f0f4f9;
            font-size: 0.9rem;
            border-left: 5px solid #9aaebf;
        }

        .feedback.correct {
            background: #e0f2e9;
            border-left-color: #2b7a4b;
            color: #145c33;
        }

        .feedback.wrong {
            background: #ffe8e6;
            border-left-color: #c7362b;
            color: #9b2c1f;
        }

        .event-select-row {
            background: #fafafc;
            border-radius: 60px;
            padding: 10px 15px;
            margin: 10px 0;
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: space-between;
            gap: 12px;
        }

        select {
            padding: 8px 12px;
            border-radius: 60px;
            border: 1px solid #c0d4e4;
        }

        .matching-row {
            background: #faf9ff;
            padding: 12px 18px;
            border-radius: 60px;
            margin: 12px 0;
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            gap: 15px;
        }

        .formula-input {
            font-family: monospace;
            font-size: 1rem;
            padding: 8px 14px;
            width: 130px;
            border-radius: 48px;
            border: 1px solid #b9cfdf;
            text-align: center;
        }

        .venn-hotspot {
            background: #f0f6fb;
            border-radius: 36px;
            padding: 20px;
            text-align: center;
            cursor: pointer;
        }

        svg {
            max-width: 100%;
            cursor: pointer;
        }

        textarea {
            width: 100%;
            border-radius: 28px;
            padding: 14px 18px;
            border: 1px solid #cbdbe6;
            font-family: inherit;
            margin: 12px 0;
        }

        .score-panel {
            background: #e9f2f9;
            border-radius: 60px;
            padding: 12px 24px;
            display: inline-block;
            margin-bottom: 28px;
            font-weight: 700;
        }

        .email-btn {
            background: #c7512e;
            margin-left: 12px;
        }
        .email-btn:hover {
            background: #9e3e20;
        }

        footer {
            text-align: center;
            margin-top: 36px;
            font-size: 0.75rem;
            color: #627e92;
        }
        .action-buttons {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            margin-top: 16px;
        }
    </style>
</head>
<body>
<div class="worksheet">
    <h1>📐 Интерактивный рабочий лист <span class="grade-badge">8 класс</span></h1>
    <div class="subhead">🎲 Тема: Несовместные события. Формула сложения вероятностей P(A∪B) = P(A) + P(B)</div>

    <!-- Блок с ФИО ученика -->
    <div class="student-info">
        <div class="student-field">
            <label>📌 Фамилия</label>
            <input type="text" id="studentSurname" placeholder="Иванов">
        </div>
        <div class="student-field">
            <label>📌 Имя</label>
            <input type="text" id="studentName" placeholder="Алексей">
        </div>
        <div class="student-field">
            <label>📌 Класс</label>
            <input type="text" id="studentClass" placeholder="8А">
        </div>
    </div>

    <div id="globalScoreArea" class="score-panel">🏆 Набрано баллов: 0 / 22</div>

    <!-- ЗАДАНИЕ 1 -->
    <div class="task" id="task1">
        <div class="task-header"><span class="task-num">1</span> Разминка: «Верно или неверно?»</div>
        <div class="task-body">
            <div class="quiz-item">
                <p><strong>1.</strong> Если два события не могут произойти одновременно в одном испытании, они называются несовместными.</p>
                <div class="truefalse-row"><label class="tf-option"><input type="radio" name="tfQ1" value="true"> Верно</label><label class="tf-option"><input type="radio" name="tfQ1" value="false"> Неверно</label></div>
                <div id="fbT1" class="feedback"></div>
            </div>
            <div class="quiz-item">
                <p><strong>2.</strong> События «выпал орёл» и «выпала решка» при одном подбрасывании монеты являются совместными.</p>
                <div class="truefalse-row"><label class="tf-option"><input type="radio" name="tfQ2" value="true"> Верно</label><label class="tf-option"><input type="radio" name="tfQ2" value="false"> Неверно</label></div>
                <div id="fbT2" class="feedback"></div>
            </div>
            <div class="quiz-item">
                <p><strong>3.</strong> Для любых двух несовместных событий P(A∪B) = P(A) + P(B).</p>
                <div class="truefalse-row"><label class="tf-option"><input type="radio" name="tfQ3" value="true"> Верно</label><label class="tf-option"><input type="radio" name="tfQ3" value="false"> Неверно</label></div>
                <div id="fbT3" class="feedback"></div>
            </div>
            <div class="quiz-item">
                <p><strong>4.</strong> Если события несовместны, то P(A∩B) = 1.</p>
                <div class="truefalse-row"><label class="tf-option"><input type="radio" name="tfQ4" value="true"> Верно</label><label class="tf-option"><input type="radio" name="tfQ4" value="false"> Неверно</label></div>
                <div id="fbT4" class="feedback"></div>
            </div>
            <button class="check-task" data-task="1">✅ Проверить задание 1</button>
        </div>
    </div>

    <!-- ЗАДАНИЕ 2 -->
    <div class="task" id="task2">
        <div class="task-header"><span class="task-num">2</span> Классификация: Совместные или несовместные?</div>
        <div class="task-body">
            <div id="groupEvents">
                <div class="event-select-row"><span>🎲 A = «чётное число» (2,4,6) , B = «число 4»</span><select class="classifySelect"><option value="">--Выбрать--</option><option value="joint">Совместные</option><option value="disjoint">Несовместные</option></select></div>
                <div class="event-select-row"><span>🎲 A = «выпала единица» , B = «выпала двойка»</span><select class="classifySelect"><option value="">--Выбрать--</option><option value="joint">Совместные</option><option value="disjoint">Несовместные</option></select></div>
                <div class="event-select-row"><span>🎫 Лотерейный билет: A = «выигрыш 100 руб», B = «выигрыш 500 руб»</span><select class="classifySelect"><option value="">--Выбрать--</option><option value="joint">Совместные</option><option value="disjoint">Несовместные</option></select></div>
                <div class="event-select-row"><span>🪙 Монета: A = «орёл», B = «решка»</span><select class="classifySelect"><option value="">--Выбрать--</option><option value="joint">Совместные</option><option value="disjoint">Несовместные</option></select></div>
                <div class="event-select-row"><span>🎲 A = «число меньше 3» (1,2) , B = «нечётное число» (1,3,5)</span><select class="classifySelect"><option value="">--Выбрать--</option><option value="joint">Совместные</option><option value="disjoint">Несовместные</option></select></div>
            </div>
            <button class="check-task" data-task="2">🔍 Проверить задание 2</button>
            <div id="fbTask2" class="feedback"></div>
        </div>
    </div>

    <!-- ЗАДАНИЕ 3 -->
    <div class="task" id="task3">
        <div class="task-header"><span class="task-num">3</span> Соедини формулировки</div>
        <div class="task-body">
            <div class="matching-row">1. Если A и B – несовместные события, то... <select id="matchOption1"><option value="">Выбери</option><option value="A">А. ... P(A∩B) = 0</option><option value="B">Б. ... сумма вероятностей противоположных событий равна 1</option><option value="C">В. ... P(A∪B) = P(A)+P(B)</option></select></div>
            <div class="matching-row">2. Для любых двух несовместных событий... <select id="matchOption2"><option value="">Выбери</option><option value="A">А. ... P(A∩B) = 0</option><option value="B">Б. ... сумма вероятностей противоположных событий равна 1</option><option value="C">В. ... P(A∪B) = P(A)+P(B)</option></select></div>
            <div class="matching-row">3. Для противоположных событий... <select id="matchOption3"><option value="">Выбери</option><option value="A">А. ... P(A∩B) = 0</option><option value="B">Б. ... сумма вероятностей противоположных событий равна 1</option><option value="C">В. ... P(A∪B) = P(A)+P(B)</option></select></div>
            <button class="check-task" data-task="3">🔗 Проверить задание 3</button>
            <div id="fbTask3" class="feedback"></div>
        </div>
    </div>

    <!-- ЗАДАНИЕ 4 -->
    <div class="task" id="task4">
        <div class="task-header"><span class="task-num">4</span> Вычисли вероятность</div>
        <div class="task-body">
            <p><strong>📌 Задача 1.</strong> В лотерее 20 билетов: 5 – выигрыш 50 руб, 3 – выигрыш 100 руб. Вероятность выигрыша?</p>
            <input type="text" id="probAnswer1" placeholder="введи число" class="formula-input">
            <p><strong>✍️ Задача 2.</strong> P(плохо)=0.08, P(хорошо)=0.92. P(хорошо ИЛИ плохо)=?</p>
            <input type="text" id="probAnswer2" placeholder="число" class="formula-input">
            <button class="check-task" data-task="4">🧮 Проверить задание 4</button>
            <div id="fbTask4" class="feedback"></div>
        </div>
    </div>

    <!-- ЗАДАНИЕ 5 Hotspot -->
    <div class="task" id="task5">
        <div class="task-header"><span class="task-num">5</span> Диаграмма: кликни на объединение</div>
        <div class="task-body">
            <div class="venn-hotspot" id="vennClickArea">
                <svg width="280" height="160" viewBox="0 0 300 160" style="display: block; margin: 0 auto;">
                    <circle cx="95" cy="75" r="52" fill="#c2e0ff" stroke="#15607a" stroke-width="2.5" />
                    <circle cx="195" cy="75" r="52" fill="#ffd9b0" stroke="#15607a" stroke-width="2.5" />
                    <text x="72" y="82" font-size="15" fill="#1f4e6e" font-weight="bold">A</text>
                    <text x="208" y="82" font-size="15" fill="#1f4e6e" font-weight="bold">B</text>
                    <text x="100" y="145" font-size="12" fill="#2c6075">∪ (оба круга)</text>
                </svg>
            </div>
            <div id="hotspotFeed" class="feedback"></div>
            <button id="resetHotspotBtn">🔄 Сбросить клик</button>
        </div>
    </div>

    <!-- ЗАДАНИЕ 6 Открытый ответ -->
    <div class="task" id="task6">
        <div class="task-header"><span class="task-num">6</span> Найди ошибку</div>
        <div class="task-body">
            <p><strong>Ученик решил:</strong> «В ящике 10 шаров: 3 красных, 2 синих, 5 зелёных. Вынимают один шар. Вероятность красный или синий = 3/10+2/10 = 0,5. Всё верно».</p>
            <textarea id="openAnswerField" rows="3" placeholder="Верно ли решение? Напиши свой ответ (например: 'Верно, ошибок нет')"></textarea>
            <button id="checkOpenAnswer">📋 Проверить</button>
            <div id="fbTask6" class="feedback"></div>
        </div>
    </div>

    <div class="action-buttons">
        <button id="finalScoreBtn" class="btn-final">✨ Показать итоговый результат</button>
        <button id="sendEmailBtn" class="email-btn">📧 Отправить результат учителю (sabirovaregina2003@mail.ru)</button>
    </div>
    <footer>💡 После проверки заданий нажмите «Отправить результат» — письмо с баллами и ответами придёт на почту учителя.</footer>
</div>

<script>
    // --- Баллы и логика заданий (как в предыдущей версии) ---
    let earnedPoints = {1:0, 2:0, 3:0, 4:0, 5:0, 6:0};
    const maxPoints = {1:4, 2:5, 3:3, 4:2, 5:2, 6:2};
    let hotspotDone = false;

    function updateScoreUI() {
        let total = 0;
        for(let i=1;i<=6;i++) total += earnedPoints[i];
        let maxTot = Object.values(maxPoints).reduce((a,b)=>a+b,0);
        document.getElementById('globalScoreArea').innerHTML = `🏆 Набрано баллов: ${total} / ${maxTot}`;
    }

    // Задание 1
    document.querySelector('.check-task[data-task="1"]').addEventListener('click', function(){
        let getVal = (name) => { let r = document.querySelector(`input[name="${name}"]:checked`); return r ? r.value : null; };
        let a1=getVal('tfQ1'), a2=getVal('tfQ2'), a3=getVal('tfQ3'), a4=getVal('tfQ4');
        let correct = {1:'true',2:'false',3:'true',4:'false'};
        let score=0;
        let f1=document.getElementById('fbT1'), f2=document.getElementById('fbT2'), f3=document.getElementById('fbT3'), f4=document.getElementById('fbT4');
        if(a1===correct[1]){ f1.innerHTML='✓ Верно'; f1.className='feedback correct'; score++; } else { f1.innerHTML='✗ Неверно'; f1.className='feedback wrong';}
        if(a2===correct[2]){ f2.innerHTML='✓ Верно (несовместны)'; f2.className='feedback correct'; score++; } else { f2.innerHTML='✗ Орёл и решка несовместны'; f2.className='feedback wrong';}
        if(a3===correct[3]){ f3.innerHTML='✓ Верно'; f3.className='feedback correct'; score++; } else { f3.innerHTML='✗ Формула верна'; f3.className='feedback wrong';}
        if(a4===correct[4]){ f4.innerHTML='✓ Верно, P=0'; f4.className='feedback correct'; score++; } else { f4.innerHTML='✗ Несовместные: пересечение 0'; f4.className='feedback wrong';}
        earnedPoints[1]=score; updateScoreUI();
    });

    document.querySelector('.check-task[data-task="2"]').addEventListener('click', function(){
        let selects = document.querySelectorAll('#groupEvents .classifySelect');
        let expected = ['joint','disjoint','disjoint','disjoint','joint'];
        let correctCount=0;
        selects.forEach((s,i)=> { if(s.value===expected[i]) correctCount++; });
        let fb=document.getElementById('fbTask2');
        if(correctCount===5){ fb.innerHTML='🎉 Отлично!'; fb.className='feedback correct'; earnedPoints[2]=maxPoints[2]; }
        else { fb.innerHTML=`⚠️ Правильно ${correctCount}/5`; fb.className='feedback wrong'; earnedPoints[2]=correctCount>=4?4:(correctCount>=3?2:0); }
        updateScoreUI();
    });

    document.querySelector('.check-task[data-task="3"]').addEventListener('click', function(){
        let m1=document.getElementById('matchOption1').value, m2=document.getElementById('matchOption2').value, m3=document.getElementById('matchOption3').value;
        let ok=0; if(m1==='A') ok++; if(m2==='C') ok++; if(m3==='B') ok++;
        let fb=document.getElementById('fbTask3');
        if(ok===3){ fb.innerHTML='✔️ Верно!'; fb.className='feedback correct'; earnedPoints[3]=maxPoints[3]; }
        else { fb.innerHTML=`❌ Правильно ${ok}/3`; fb.className='feedback wrong'; earnedPoints[3]=ok; }
        updateScoreUI();
    });

    document.querySelector('.check-task[data-task="4"]').addEventListener('click', function(){
        let a1=document.getElementById('probAnswer1').value.trim().replace(',','.');
        let a2=document.getElementById('probAnswer2').value.trim();
        let ok1=(a1==='2/5'||a1==='8/20'||parseFloat(a1)===0.4);
        let ok2=(a2==='1'||a2==='1.0');
        let score= (ok1?1:0)+(ok2?1:0);
        let fb=document.getElementById('fbTask4');
        if(score===2){ fb.innerHTML='✅ Верно!'; fb.className='feedback correct'; earnedPoints[4]=maxPoints[4]; }
        else if(score===1){ fb.innerHTML='⚠️ Один ответ неверен'; fb.className='feedback wrong'; earnedPoints[4]=1; }
        else { fb.innerHTML='❌ Оба ответа неверны'; fb.className='feedback wrong'; earnedPoints[4]=0; }
        updateScoreUI();
    });

    const vennDiv = document.getElementById('vennClickArea');
    const hotspotFeed = document.getElementById('hotspotFeed');
    vennDiv.addEventListener('click', ()=>{
        if(!hotspotDone){ hotspotFeed.innerHTML='🎯 Верно! A∪B – оба круга.'; hotspotFeed.className='feedback correct'; earnedPoints[5]=maxPoints[5]; hotspotDone=true; updateScoreUI();}
        else { hotspotFeed.innerHTML='Уже засчитано.'; hotspotFeed.className='feedback correct';}
    });
    document.getElementById('resetHotspotBtn').addEventListener('click', ()=>{ hotspotDone=false; earnedPoints[5]=0; hotspotFeed.innerHTML='Кликни по области объединения'; hotspotFeed.className='feedback'; updateScoreUI();});

    document.getElementById('checkOpenAnswer').addEventListener('click', ()=>{
        let text = document.getElementById('openAnswerField').value.toLowerCase();
        let fb6=document.getElementById('fbTask6');
        if(text.includes('верно')||text.includes('правильно')||text.includes('ошибок нет')){ fb6.innerHTML='✅ Верно, решение ученика правильное.'; fb6.className='feedback correct'; earnedPoints[6]=maxPoints[6];}
        else if(text.trim()===''){ fb6.innerHTML='✏️ Напишите ответ (решение верное)'; fb6.className='feedback wrong'; earnedPoints[6]=0;}
        else { fb6.innerHTML='⚠️ Внимание: ошибки нет. Решение верно!'; fb6.className='feedback wrong'; earnedPoints[6]=0;}
        updateScoreUI();
    });

    document.getElementById('finalScoreBtn').addEventListener('click', ()=>{
        let total = Object.values(earnedPoints).reduce((a,b)=>a+b,0);
        alert(`Ваш результат: ${total}/${Object.values(maxPoints).reduce((a,b)=>a+b,0)}`);
    });

    // --- ОТПРАВКА НА ПОЧТУ (через FormSubmit) ---
    document.getElementById('sendEmailBtn').addEventListener('click', function(e){
        let surname = document.getElementById('studentSurname').value.trim();
        let name = document.getElementById('studentName').value.trim();
        let klass = document.getElementById('studentClass').value.trim();
        if(surname === "" || name === ""){
            alert("Пожалуйста, заполните фамилию и имя ученика перед отправкой!");
            return;
        }
        let totalPoints = Object.values(earnedPoints).reduce((a,b)=>a+b,0);
        let maxTotal = Object.values(maxPoints).reduce((a,b)=>a+b,0);
        
        // Собираем детальные ответы для отчёта
        let report = `📊 РЕЗУЛЬТАТ РАБОЧЕГО ЛИСТА\n`;
        report += `👤 Ученик: ${surname} ${name} ${klass ? `(${klass})` : ''}\n`;
        report += `🏆 Баллы: ${totalPoints} из ${maxTotal}\n\n`;
        report += `📌 Задание 1 (Верно/Неверно): ${earnedPoints[1]}/4\n`;
        report += `📌 Задание 2 (Классификация): ${earnedPoints[2]}/5\n`;
        report += `📌 Задание 3 (Соединить): ${earnedPoints[3]}/3\n`;
        report += `📌 Задание 4 (Расчёт): ${earnedPoints[4]}/2\n`;
        report += `📌 Задание 5 (Диаграмма): ${earnedPoints[5]}/2\n`;
        report += `📌 Задание 6 (Открытый ответ): ${earnedPoints[6]}/2\n`;
        report += `\n✏️ Ответ на задание 6: "${document.getElementById('openAnswerField').value}"\n`;
        report += `\n--- Отправлено с интерактивного листа ---`;

        // Используем FormSubmit (бесплатный сервис, без сервера). Адрес получателя жёстко задан.
        const form = document.createElement('form');
        form.method = 'POST';
        form.action = 'https://formsubmit.co/sabirovaregina2003@mail.ru';
        form.style.display = 'none';
        
        const emailField = document.createElement('input');
        emailField.name = 'email';
        emailField.value = 'sabirovaregina2003@mail.ru';
        form.appendChild(emailField);
        
        const subjectField = document.createElement('input');
        subjectField.name = '_subject';
        subjectField.value = `Результат теста: ${surname} ${name}`;
        form.appendChild(subjectField);
        
        const messageField = document.createElement('textarea');
        messageField.name = 'message';
        messageField.value = report;
        form.appendChild(messageField);
        
        // Доп. параметры: отключаем капчу, редирект на страницу "спасибо"
        const redirectField = document.createElement('input');
        redirectField.name = '_next';
        redirectField.value = 'https://example.com/thankyou'; // можно заменить на пустой или свою страницу, но работает и так
        form.appendChild(redirectField);
        
        document.body.appendChild(form);
        form.submit();
        document.body.removeChild(form);
        
        alert(`Отчёт отправлен на почту учителя (sabirovaregina2003@mail.ru).\nУченик: ${surname} ${name}\nБаллы: ${totalPoints}/${maxTotal}`);
    });
    updateScoreUI();
</script>
</body>
</html>
