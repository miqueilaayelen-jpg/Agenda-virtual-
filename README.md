<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Coquette Beauty Book</title>

<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@500;700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">

<style>
body{
margin:0;
font-family:Poppins;
background:linear-gradient(120deg,#0b0b0b,#1a1a1a,#2a0f1f,#111827);
background-size:300% 300%;
animation:gradientMove 12s ease infinite;
color:white;
display:flex;
min-height:100vh;
}

@keyframes gradientMove{
0%{background-position:0% 50%}
50%{background-position:100% 50%}
100%{background-position:0% 50%}
}

/* SIDEBAR */
.sidebar{
width:220px;
background:rgba(255,255,255,0.05);
backdrop-filter: blur(12px);
padding:20px;
border-right:1px solid rgba(255,255,255,0.08);
}

.sidebar h2{
font-family:'Playfair Display';
color:#ffb6c1;
}

.sidebar button{
width:100%;
margin-bottom:10px;
padding:10px;
border:none;
border-radius:10px;
background:rgba(255,255,255,0.06);
color:white;
cursor:pointer;
}

.sidebar button:hover{
background:rgba(255,182,193,0.25);
}

/* MAIN */
.main{
flex:1;
padding:20px;
display:flex;
justify-content:center;
}

.container{
max-width:750px;
width:100%;
}

h1{
font-family:'Playfair Display';
color:#ffb6c1;
text-align:center;
letter-spacing:1px;
}

.section{display:none;}
.section.active{display:block;}

.card{
background:rgba(255,255,255,0.07);
padding:15px;
border-radius:18px;
margin-bottom:12px;
backdrop-filter: blur(8px);
}

.input{
width:100%;
padding:10px;
margin-top:8px;
border-radius:10px;
border:none;
background:rgba(0,0,0,0.4);
color:white;
outline:none;
}

.button{
width:100%;
padding:10px;
margin-top:8px;
border:none;
border-radius:12px;
background:linear-gradient(90deg,#ff69b4,#ffb6c1,#ffd1dc);
cursor:pointer;
font-weight:600;
}

.task{
display:flex;
justify-content:space-between;
padding:8px;
margin-top:6px;
background:rgba(255,255,255,0.05);
border-radius:10px;
}

/* FOOTER */
.footer{
margin-top:30px;
padding:20px;
text-align:center;
font-size:12px;
opacity:0.75;
line-height:1.8;
}

.quote{
margin:8px 0;
opacity:0.8;
}
.bigspace{
margin-top:20px;
}
</style>
</head>

<body>

<div class="sidebar">
<h2>💖 Beauty Book</h2>
<button onclick="show('home')">Inicio</button>
<button onclick="show('agenda')">Agenda</button>
<button onclick="show('finanzas')">Finanzas</button>
<button onclick="show('ideas')">Ideas</button>
<button onclick="show('notes')">Notas</button>
<button onclick="show('goals')">Objetivos</button>
</div>

<div class="main">
<div class="container">

<h1>Coquette Beauty Book</h1>

<!-- HOME -->
<div id="home" class="section active">
<div class="card">💖 Tu espacio de organización, creatividad y crecimiento</div>
<div class="card">✨ Todo lo que hacés hoy construye la versión que soñás</div>
<div class="card">💅 Tu negocio también merece orden y belleza</div>

<div class="footer">

<div class="quote">“No estás atrasada, estás construyendo algo tuyo.”</div>
<div class="quote">“La constancia crea resultados que la motivación no puede.”</div>
<div class="quote">“Pequeños pasos también cuentan.”</div>
<div class="quote">“Tu energía es tu mayor herramienta.”</div>
<div class="quote">“Cada idea puede convertirse en ingresos.”</div>

<div class="bigspace"></div>

<div class="quote">💖 Hoy es un buen día para crecer.</div>
<div class="quote">🌙 Confía en tu proceso.</div>
<div class="quote">✨ Estás más cerca de lo que crees.</div>
<div class="quote">💅 Hazlo con estilo, hazlo a tu manera.</div>

<div class="bigspace"></div>

<div class="quote">“Lo que organizas, lo multiplicas.”</div>
<div class="quote">“Tu disciplina vale más que la inspiración.”</div>
<div class="quote">“Crea, mejora, repite.”</div>
<div class="quote">“Tu negocio es tu arte.”</div>

</div>
</div>

<!-- AGENDA -->
<div id="agenda" class="section">
<div class="card">
📝 Tareas
<input id="taskInput" class="input">
<button class="button" onclick="addTask()">Agregar</button>
<div id="taskList"></div>
</div>
</div>

<!-- FINANZAS -->
<div id="finanzas" class="section">

<div class="card">
💰 Ingresos
<input id="incomeInput" class="input">
<button class="button" onclick="addIncome()">Agregar</button>
<div id="incomeList"></div>
<p id="totalIncome"></p>
</div>

<div class="card">
💸 Gastos
<input id="expenseInput" class="input">
<button class="button" onclick="addExpense()">Agregar</button>
<div id="expenseList"></div>
<p id="totalExpense"></p>
</div>

<div class="card">
💖 Ganancia
<p id="profit"></p>
</div>

<div class="card">
🧾 Ventas
<input id="saleInput" class="input">
<button class="button" onclick="addSale()">Agregar</button>
<div id="saleList"></div>
</div>

</div>

<!-- IDEAS -->
<div id="ideas" class="section">
<div class="card">
💡 Ideas
<input id="ideaInput" class="input">
<button class="button" onclick="addIdea()">Guardar</button>
<div id="ideaList"></div>
</div>
</div>

<!-- NOTAS -->
<div id="notes" class="section">
<div class="card">
📒 Notas
<input id="noteInput" class="input">
<button class="button" onclick="addNote()">Agregar</button>
<div id="noteList"></div>
</div>
</div>

<!-- OBJETIVOS -->
<div id="goals" class="section">
<div class="card">
⭐ Objetivos
<input id="goalInput" class="input">
<button class="button" onclick="addGoal()">Agregar</button>
<div id="goalList"></div>
</div>
</div>

</div>
</div>

<script>

/* NAV */
function show(id){
document.querySelectorAll('.section').forEach(s=>s.classList.remove('active'));
document.getElementById(id).classList.add('active');
}

/* DATA */
let tasks = JSON.parse(localStorage.getItem("tasks")) || [];
let income = JSON.parse(localStorage.getItem("income")) || [];
let expense = JSON.parse(localStorage.getItem("expense")) || [];
let sales = JSON.parse(localStorage.getItem("sales")) || [];
let ideas = JSON.parse(localStorage.getItem("ideas")) || [];
let notes = JSON.parse(localStorage.getItem("notes")) || [];
let goals = JSON.parse(localStorage.getItem("goals")) || [];

/* SAVE */
function save(){
localStorage.setItem("tasks",JSON.stringify(tasks));
localStorage.setItem("income",JSON.stringify(income));
localStorage.setItem("expense",JSON.stringify(expense));
localStorage.setItem("sales",JSON.stringify(sales));
localStorage.setItem("ideas",JSON.stringify(ideas));
localStorage.setItem("notes",JSON.stringify(notes));
localStorage.setItem("goals",JSON.stringify(goals));
}

/* RENDER */
function render(){
renderList("taskList",tasks,"📝 ");
renderList("incomeList",income,"+$");
renderList("expenseList",expense,"-$");
renderList("saleList",sales,"");
renderList("ideaList",ideas,"💡 ");
renderList("noteList",notes,"📒 ");
renderList("goalList",goals,"⭐ ");
calc();
}

function renderList(id,array,prefix){
let c=document.getElementById(id);
if(!c) return;
c.innerHTML="";
array.forEach((t,i)=>{
let div=document.createElement("div");
div.className="task";
div.innerHTML=`<span>${prefix}${t}</span>
<span onclick="removeItem('${id}',${i})">❌</span>`;
c.appendChild(div);
});
}

function removeItem(type,i){
if(type==="taskList") tasks.splice(i,1);
if(type==="incomeList") income.splice(i,1);
if(type==="expenseList") expense.splice(i,1);
if(type==="saleList") sales.splice(i,1);
if(type==="ideaList") ideas.splice(i,1);
if(type==="noteList") notes.splice(i,1);
if(type==="goalList") goals.splice(i,1);
save();
render();
}

/* FUNCTIONS */
function addTask(){let v=document.getElementById("taskInput").value;if(v){tasks.push(v);document.getElementById("taskInput").value="";save();render();}}
function addIncome(){let v=document.getElementById("incomeInput").value;if(v){income.push(v);document.getElementById("incomeInput").value="";save();render();}}
function addExpense(){let v=document.getElementById("expenseInput").value;if(v){expense.push(v);document.getElementById("expenseInput").value="";save();render();}}
function addSale(){let v=document.getElementById("saleInput").value;if(v){sales.push(v);document.getElementById("saleInput").value="";save();render();}}
function addIdea(){let v=document.getElementById("ideaInput").value;if(v){ideas.push(v);document.getElementById("ideaInput").value="";save();render();}}
function addNote(){let v=document.getElementById("noteInput").value;if(v){notes.push(v);document.getElementById("noteInput").value="";save();render();}}
function addGoal(){let v=document.getElementById("goalInput").value;if(v){goals.push(v);document.getElementById("goalInput").value="";save();render();}}

function calc(){
let totalI=income.reduce((a,b)=>a+parseFloat(b),0);
let totalE=expense.reduce((a,b)=>a+parseFloat(b),0);
let profit=totalI-totalE;

document.getElementById("totalIncome").innerText="Total: $"+totalI;
document.getElementById("totalExpense").innerText="Total: $"+totalE;
document.getElementById("profit").innerText="💖 Ganancia: $"+profit;
}

render();

</script>

</body>
</html>
