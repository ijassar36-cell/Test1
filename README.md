    <!doctype html>
<html lang="ar">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Present Perfect vs Simple Past Quiz</title>
<style>
body {margin:0;font-family:system-ui,-apple-system,"Segoe UI",Roboto,"Noto Sans Arabic";background:#f0f4f8;direction:ltr;}
.container {max-width:1000px;margin:30px auto;padding:20px;}
h1 {font-size:2.2rem;color:#34495e;margin-bottom:15px;text-align:center;}
.lead {text-align:center;margin-bottom:25px;color:#2c3e50;font-size:1.25rem;}
.info {text-align:center;margin-bottom:30px;color:#2c3e50;font-weight:600;line-height:1.6;font-size:1.1rem;}
.card {background:#fff;padding:25px;border-radius:20px;box-shadow:0 12px 30px rgba(0,0,0,.08);margin-bottom:22px;position:relative;transition:transform .25s, box-shadow .25s;}
.card:hover {transform:translateY(-4px); box-shadow:0 18px 35px rgba(0,0,0,.12);}
.q-head {display:flex;align-items:center;gap:14px;}
.q-num {background:linear-gradient(135deg,#6a11cb,#2575fc);color:#fff;padding:10px 20px;border-radius:16px;font-weight:700;font-size:1.1rem;}
.sentence {margin:16px 0 18px;font-size:1.35rem;color:#2c3e50;}
.choices {display:flex;gap:15px;flex-wrap:wrap;}
.choice {flex:1 1 220px;padding:14px 16px;border-radius:14px;border:1px solid #dce6f1;background:#dfe6e9;cursor:pointer;transition:.3s all;user-select:none;font-size:1.12rem;text-align:center;}
.choice:hover {transform:translateY(-5px) scale(1.03); box-shadow:0 8px 22px rgba(0,0,0,.08);}
.choice.correct {background:linear-gradient(90deg,#2ecc71,#27ae60);color:#fff;font-weight:700;animation:glow 1s ease-in-out;}
.choice.wrong {background:linear-gradient(90deg,#e74c3c,#c0392b);color:#fff;font-weight:700;animation:shake 0.5s;}
.choice.disabled {cursor:default; opacity:.85; box-shadow:none; transform:none;}
@keyframes shake {0%,100%{transform:translateX(0);}25%{transform:translateX(-6px);}50%{transform:translateX(6px);}75%{transform:translateX(-4px);}}
@keyframes glow {0%,100%{box-shadow:0 0 10px rgba(0,0,0,.2);}50%{box-shadow:0 0 22px rgba(255,255,255,.6);}}
.popover {position:relative;background:#fff;border:1px solid #cfd8dc;border-radius:16px;padding:18px 20px;margin-top:14px;font-size:1.1rem;color:#2c3e50;box-shadow:0 12px 28px rgba(0,0,0,.08);width:100%;line-height:1.6;direction:rtl;text-align:right;opacity:0;transform:translateY(-10px);animation:popfade 0.5s forwards;}
@keyframes popfade {to {opacity:1; transform:translateY(0);}}
.popover .eng-example {margin-top:8px;padding-top:6px;border-top:1px solid #ddd;font-family:"Segoe UI",sans-serif;direction:ltr;text-align:left;font-weight:600;}
#showResultBtn {display:block;margin:25px auto;padding:14px 28px;font-size:1.2rem;background:#ff6b81;color:#fff;border:none;border-radius:16px;cursor:pointer;transition:.3s;}
#showResultBtn:hover {background:#ee5253; transform:scale(1.05);}
#result {text-align:center;font-size:1.25rem;margin-top:22px;color:#2c3e50;font-weight:700;}
.credit {text-align:center;margin-top:35px;font-size:1rem;color:#555;padding:12px 0;}
input#studentName {padding:10px 14px; font-size:1.15rem; border-radius:10px; border:1px solid #ccc; width:60%; margin:0 auto; display:block;}
label {display:block;text-align:center;margin-top:18px;font-size:1.2rem;color:#2c3e50;}
</style>
</head>
<body>
<div class="container">

<div class="info">
تنفيذ معلم مادة اللغة الإنجليزية: الأستاذ / فهد نغيمش الخالدي<br>
مدرسة: سعيد بن العاص المتوسطة<br>
الصف: الثالث المتوسط
</div>

<h1>Present Perfect vs Simple Past Quiz</h1>
<p class="lead">اختر الإجابة الصحيحة. بعد الانتهاء، ادخل اسمك واضغط على "عرض النتيجة" لحفظ نتيجتك.</p>

<label>اسم الطالب: <input type="text" id="studentName" placeholder="اكتب اسمك هنا" /></label>

<div id="quiz"></div>
<button id="showResultBtn">عرض النتيجة</button>
<div id="result"></div>

<div class="credit">إعداد: المعلم فهد نغيمش الخالدي</div>
</div>

<script>
const questions = [
  { sentence:"I _____ (visit) London three times in my life.", choices:["visited","have visited"], correct:1, explanation:"نستخدم Present Perfect للتجارب الحياتية بدون ذكر وقت محدد.", example:"I have visited London three times." },
  { sentence:"She _____ (finish) her homework yesterday.", choices:["has finished","finished"], correct:1, explanation:"كلمة yesterday تحدد وقتًا منتهيًا → Simple Past.", example:"She finished her homework yesterday." },
  { sentence:"We _____ (live) here since 2018.", choices:["lived","have lived"], correct:1, explanation:"استخدام since يدل على فعل بدأ في الماضي ومازال مستمرًا.", example:"We have lived here since 2018." },
  { sentence:"He _____ (break) his leg last winter.", choices:["broke","has broken"], correct:0, explanation:"last winter يحدد وقتًا من الماضي فقط → Simple Past.", example:"He broke his leg last winter." },
  { sentence:"She _____ gone to the store.", choices:["have","has"], correct:1, explanation:"في Present Perfect نستخدم has مع She/He/It لأن الفاعل مفرد.", example:"She has gone to the store." },
  { sentence:"They _____ already finished the project.", choices:["have","has"], correct:0, explanation:"مع they نستخدم have لأن الفاعل جمع.", example:"They have already finished the project." },
  { sentence:"He _____ not done his work yet.", choices:["have","has"], correct:1, explanation:"الفعل المفرد He يأخذ has في Present Perfect.", example:"He has not done his work yet." },
  { sentence:"I _____ ate sushi before.", choices:["have eaten","ate"], correct:0, explanation:"عند الحديث عن تجربة بدون وقت محدد نستخدم Present Perfect.", example:"I have eaten sushi before." },
  { sentence:"She _____ never seen snow.", choices:["has","have"], correct:0, explanation:"الفاعل She مفرد → has + التصريف الثالث للفعل.", example:"She has never seen snow." },
  { sentence:"We _____ finished the exam two hours ago.", choices:["have","finished"], correct:1, explanation:"وجود ago يدل على وقت من الماضي المنتهي → Simple Past.", example:"We finished the exam two hours ago." },
  { sentence:"I _____ (meet) him in 2020.", choices:["met","have met"], correct:0, explanation:"2020 وقت محدد في الماضي → Simple Past.", example:"I met him in 2020." },
  { sentence:"I _____ (meet) him before.", choices:["met","have met"], correct:1, explanation:"before يدل على تجربة بدون وقت → Present Perfect.", example:"I have met him before." },
  { sentence:"They _____ (be) friends since childhood.", choices:["have been","were"], correct:0, explanation:"العلاقة مستمرة حتى الآن → Present Perfect.", example:"They have been friends since childhood." },
  { sentence:"She _____ (go) to Paris last month.", choices:["went","has gone"], correct:0, explanation:"last month وقت منتهي → Simple Past.", example:"She went to Paris last month." },
  { sentence:"He _____ (lose) his keys — he can’t find them.", choices:["lost","has lost"], correct:1, explanation:"النتيجة مازالت مستمرة → Present Perfect.", example:"He has lost his keys." },
  { sentence:"I _____ just finished my homework.", choices:["have","has"], correct:0, explanation:"مع I نستخدم have + التصريف الثالث → Present Perfect.", example:"I have just finished my homework." },
  { sentence:"They _____ (see) that movie yesterday.", choices:["have seen","saw"], correct:1, explanation:"yesterday يدل على زمن محدد → Simple Past.", example:"They saw that movie yesterday." },
  { sentence:"She _____ (write) three emails so far.", choices:["has written","wrote"], correct:0, explanation:"so far تشير إلى تجربة مستمرة → Present Perfect.", example:"She has written three emails so far." },
  { sentence:"We _____ (eat) lunch an hour ago.", choices:["have eaten","ate"], correct:1, explanation:"an hour ago يدل على وقت محدد → Simple Past.", example:"We ate lunch an hour ago." },
  { sentence:"He _____ (never/try) sushi before.", choices:["has never tried","never tried"], correct:0, explanation:"قبل الآن → Present Perfect للتجربة.", example:"He has never tried sushi before." }
];

const quiz=document.getElementById("quiz");
let userAnswers=[];

function createCard(q,i){
  const card=document.createElement("div");
  card.className="card";
  card.innerHTML=`<div class="q-head"><div class="q-num">Q${i+1}</div></div>
  <div class="sentence">${q.sentence}</div><div class="choices"></div>`;
  const choicesDiv=card.querySelector(".choices");
  q.choices.forEach((choice,idx)=>{
    const btn=document.createElement("button");
    btn.className="choice"; btn.textContent=choice;
    btn.addEventListener("click",()=>{
      if(btn.classList.contains("disabled")) return;
      Array.from(choicesDiv.children).forEach(c=>c.classList.add("disabled"));
      userAnswers[i] = idx;
      if(idx === q.correct){ btn.classList.add("correct"); } 
      else { btn.classList.add("wrong"); choicesDiv.children[q.correct].classList.add("correct"); showPopover(card,q.explanation,q.example);}
    });
    choicesDiv.appendChild(btn);
  });
  return card;
}

function showPopover(card,arabic,example){
  const old=card.querySelector(".popover"); if(old) old.remove();
  const pop=document.createElement("div");
  pop.className="popover";
  pop.innerHTML=`<div><strong>الشرح:</strong> ${arabic}</div>
                 <div class="eng-example">${example}</div>`;
  card.appendChild(pop);
}

questions.forEach((q,i)=>quiz.appendChild(createCard(q,i)));

document.getElementById("showResultBtn").addEventListener("click",()=>{
  const name = document.getElementById("studentName").value.trim();
  if(name===""){ alert("يرجى إدخال اسمك"); return; }

  let correctCount = 0;
  questions.forEach((q,i)=>{ if(userAnswers[i]===q.correct) correctCount++; });
  const percent = Math.round((correctCount/questions.length)*100);

  document.getElementById("result").innerHTML=`${name}، نتيجتك: ${correctCount} من ${questions.length} (${percent}%)`;

  // إرسال البيانات إلى Google Sheet
  fetch("YOUR_WEB_APP_URL_HERE", {
    method:"POST",
    body: JSON.stringify({name: name, score: correctCount, percentage: percent})
  }).then(res=>res.json()).then(res=>console.log(res));
});
</script>
</body>
</html>
