# your-light-saber-colour
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>⚔ Lightsaber Forge</title>
<style>
*{box-sizing:border-box;margin:0;padding:0}
body{background:#000;display:flex;justify-content:center;align-items:center;min-height:100vh;font-family:Georgia,'Times New Roman',serif}
#swg{width:700px;background:#030b18;min-height:560px;position:relative;overflow:hidden;border-radius:10px;box-shadow:0 0 40px rgba(0,0,0,0.8)}
#sc{position:absolute;top:0;left:0;width:100%;height:100%;pointer-events:none;z-index:0}
#gh{display:flex;align-items:center;justify-content:center;position:relative;padding:20px 16px 13px;z-index:2;border-bottom:1px solid rgba(212,168,67,0.18)}
#gh-center{text-align:center;flex:1}
#gta{font-size:19px;letter-spacing:7px;color:#d4a843;text-transform:uppercase;font-weight:bold}
#gsb{font-size:10px;letter-spacing:5px;color:#4a5878;text-transform:uppercase;margin-top:5px;font-style:italic}
#lang-btns{position:absolute;right:16px;top:50%;transform:translateY(-50%);display:flex;gap:5px}
.lang-btn{padding:5px 9px;background:transparent;border:1px solid rgba(70,90,130,0.4);border-radius:4px;color:#5a6888;font-family:Georgia,serif;font-size:11px;letter-spacing:1px;cursor:pointer;transition:all 0.2s}
.lang-btn.active{border-color:#d4a843;color:#d4a843;background:rgba(212,168,67,0.1)}
.lang-btn:hover:not(.active){border-color:rgba(212,168,67,0.4);color:#a08030}
#gm{display:flex;align-items:flex-start;padding:18px 22px 20px;gap:22px;position:relative;z-index:2;min-height:460px}
#lcol{display:flex;flex-direction:column;align-items:center;flex-shrink:0;padding-top:4px}
#pdots{display:flex;gap:8px;margin-bottom:16px}
.pd{width:9px;height:9px;border-radius:50%;background:transparent;border:1px solid #283050;transition:all 0.5s}
.pd.done{background:#d4a843;border-color:#d4a843;box-shadow:0 0 6px #d4a84388}
#rcol{flex:1;padding-top:2px}
#qnum{font-size:10px;letter-spacing:4px;color:#d4a843;text-transform:uppercase;margin-bottom:12px}
#qtxt{font-size:15px;color:#bfcce0;line-height:1.7;margin-bottom:22px;min-height:58px}
.opt{display:block;width:100%;text-align:left;padding:11px 15px;margin-bottom:9px;background:rgba(255,255,255,0.025);border:1px solid rgba(70,90,130,0.35);border-radius:6px;color:#8898b8;font-size:13px;cursor:pointer;font-family:Georgia,serif;transition:background 0.2s,border-color 0.2s,color 0.2s;line-height:1.45}
.opt:hover{background:rgba(212,168,67,0.09);border-color:rgba(212,168,67,0.45);color:#e0cc78}
.opt:disabled{opacity:0.4;cursor:default}
.sp{opacity:0;transition:opacity 0.8s ease}
.sp.vis{opacity:1}
#blade-g{opacity:0;transition:opacity 1.4s ease}
#cname{font-size:17px;letter-spacing:4px;text-transform:uppercase;margin-bottom:7px;line-height:1.3}
#cpath{font-size:10px;letter-spacing:4px;color:#4a5878;text-transform:uppercase;margin-bottom:16px;font-style:italic}
#clore{font-size:13px;color:#6a7898;line-height:1.85;margin-bottom:22px}
#rfbtn{display:inline-block;padding:9px 24px;background:transparent;border:1px solid #d4a843;color:#d4a843;font-family:Georgia,serif;font-size:11px;letter-spacing:3px;text-transform:uppercase;cursor:pointer;border-radius:4px;transition:all 0.2s}
#rfbtn:hover{background:rgba(212,168,67,0.12)}
</style>
</head>
<body>
<canvas id="sc"></canvas>
<div id="swg">
<div id="gh">
  <div id="gh-center">
    <div id="gta">⚔ Lightsaber Forge</div>
    <div id="gsb">The crystal chooses the Jedi</div>
  </div>
  <div id="lang-btns">
    <button class="lang-btn active" onclick="setLang('en')">EN</button>
    <button class="lang-btn" onclick="setLang('mn')">МН</button>
  </div>
</div>
<div id="gm">
  <div id="lcol">
    <div id="pdots">
      <div class="pd" id="pd0"></div><div class="pd" id="pd1"></div>
      <div class="pd" id="pd2"></div><div class="pd" id="pd3"></div>
      <div class="pd" id="pd4"></div>
    </div>
    <svg id="lsv" viewBox="0 0 80 408" width="80" height="408" xmlns="http://www.w3.org/2000/svg">
      <g id="blade-g">
        <rect id="bglow" x="28" y="6" width="24" height="196" rx="12" fill="#ffffff" opacity="0.22"/>
        <rect id="bcore" x="33" y="6" width="14" height="196" rx="7" fill="#ffffff"/>
        <rect id="btip" x="35" y="6" width="10" height="10" rx="5" fill="#ffffff"/>
      </g>
      <g id="p-emitter" class="sp">
        <rect x="16" y="200" width="48" height="7" rx="2.5" fill="#506070"/>
        <rect x="20" y="203" width="40" height="3" rx="1.5" fill="#607080"/>
        <rect x="22" y="206" width="36" height="11" rx="2" fill="#354555"/>
        <rect x="28" y="208" width="24" height="7" rx="1.5" fill="#28384a"/>
        <rect x="22" y="209" width="8" height="7" rx="1" fill="#223040"/>
        <rect x="50" y="209" width="8" height="7" rx="1" fill="#223040"/>
        <line x1="20" y1="212" x2="60" y2="212" stroke="#607888" stroke-width="0.6"/>
      </g>
      <g id="p-ugrip" class="sp">
        <rect x="22" y="217" width="36" height="72" rx="4" fill="#182030"/>
        <rect x="22" y="220" width="36" height="5" rx="2" fill="#243250"/>
        <rect x="22" y="228" width="36" height="5" rx="2" fill="#243250"/>
        <rect x="22" y="236" width="36" height="5" rx="2" fill="#243250"/>
        <rect x="22" y="244" width="36" height="5" rx="2" fill="#243250"/>
        <rect x="22" y="252" width="36" height="5" rx="2" fill="#243250"/>
        <rect x="22" y="260" width="36" height="5" rx="2" fill="#243250"/>
        <rect x="22" y="268" width="36" height="5" rx="2" fill="#243250"/>
        <rect x="22" y="276" width="36" height="5" rx="2" fill="#243250"/>
        <rect x="17" y="246" width="9" height="13" rx="2.5" fill="#2a3a55"/>
        <rect id="abtn" x="18" y="248" width="7" height="9" rx="2" fill="#d4a843"/>
        <rect x="19" y="249" width="5" height="7" rx="1.5" fill="#ecc850"/>
      </g>
      <g id="p-lgrip" class="sp">
        <rect x="21" y="289" width="38" height="7" rx="2.5" fill="#2a3a50"/>
        <rect x="24" y="296" width="32" height="52" rx="4" fill="#12182a"/>
        <rect x="24" y="299" width="32" height="4" rx="1.5" fill="#1c2840"/>
        <rect x="24" y="306" width="32" height="4" rx="1.5" fill="#1c2840"/>
        <rect x="24" y="313" width="32" height="4" rx="1.5" fill="#1c2840"/>
        <rect x="24" y="320" width="32" height="4" rx="1.5" fill="#1c2840"/>
        <rect x="24" y="327" width="32" height="4" rx="1.5" fill="#1c2840"/>
        <rect x="24" y="334" width="32" height="4" rx="1.5" fill="#1c2840"/>
        <rect x="21" y="296" width="5" height="52" rx="2.5" fill="#1e2c44"/>
        <rect x="54" y="296" width="5" height="52" rx="2.5" fill="#1e2c44"/>
      </g>
      <g id="p-pommel" class="sp">
        <rect x="20" y="348" width="40" height="8" rx="3" fill="#283848"/>
        <rect x="23" y="356" width="34" height="30" rx="4" fill="#121e2e"/>
        <rect x="23" y="360" width="34" height="5" rx="1.5" fill="#1c2a3e"/>
        <rect x="23" y="370" width="34" height="5" rx="1.5" fill="#1c2a3e"/>
        <rect x="29" y="359" width="22" height="17" rx="3" fill="#08101c"/>
        <rect id="cwin" x="30" y="360" width="20" height="15" rx="2.5" fill="#141e30"/>
        <rect x="26" y="386" width="28" height="10" rx="4" fill="#0e1826"/>
        <rect x="29" y="388" width="22" height="6" rx="3" fill="#0a1320"/>
      </g>
    </svg>
  </div>
  <div id="rcol">
    <div id="qnum"></div>
    <div id="qtxt"></div>
    <div id="opts"></div>
  </div>
</div>
</div>

<script>
const STRINGS={
  en:{title:"⚔ Lightsaber Forge",subtitle:"The crystal chooses the Jedi",qLabel:function(i){return"Question "+(i+1)+" of 5"},forgeAgain:"⚔ Forge Again"},
  mn:{title:"⚔ Гэрлэн Илд Зоригжуулалт",subtitle:"Болор нь Жедайг сонгодог",qLabel:function(i){return(i+1)+"-р асуулт (5-аас)"},forgeAgain:"⚔ Дахин зэвсэглэх"}
};
const QS={
  en:[
    {q:"The galaxy is in chaos. What guides your hand?",opts:[{t:"Power is the only language chaos understands.",c:"red"},{t:"Those who suffer need someone strong enough to protect them.",c:"blue"},{t:"Only by understanding the root of chaos can it be healed.",c:"green"},{t:"I walk between order and freedom — even if I must choose alone.",c:"purple"}]},
    {q:"Your enemy stands defeated before you. What do you do?",opts:[{t:"End it. Mercy is a weakness they would never extend to you.",c:"red"},{t:"Offer mercy — every soul carries potential for redemption.",c:"green"},{t:"Deliver them to justice. The law must be upheld.",c:"yellow"},{t:"Step back. The Force will decide their fate.",c:"white"}]},
    {q:"A vision shows two paths: deep knowledge or decisive action. You choose…",opts:[{t:"Action. Hesitation is a form of surrender.",c:"red"},{t:"Knowledge. Wisdom prevents a thousand battles.",c:"green"},{t:"Action guided by wisdom — neither is complete alone.",c:"blue"},{t:"The hidden path between them. Neither extreme satisfies me.",c:"purple"}]},
    {q:"What is your deepest fear?",opts:[{t:"Being powerless when it matters most.",c:"red"},{t:"Failing the people who depend on me.",c:"blue"},{t:"Losing myself to the darkness of the Force.",c:"white"},{t:"A galaxy where no one remembers the light.",c:"yellow"}]},
    {q:"When your time comes, what legacy do you leave?",opts:[{t:"A new order forged entirely in my image.",c:"red"},{t:"Countless lives protected by my sacrifice.",c:"blue"},{t:"Ancient wisdom preserved for generations to come.",c:"green"},{t:"Peace built across old wounds and ancient hatred.",c:"purple"}]}
  ],
  mn:[
    {q:"Галактик эмх замбараагүй байна. Таны гарыг юу удирдах вэ?",opts:[{t:"Хүч бол эмх замбараагүй байдлын цорын ганц хэл.",c:"red"},{t:"Зовж буй хүмүүст тэднийг хамгаалах хүчтэй хүн хэрэгтэй.",c:"blue"},{t:"Эмх замбараагүй байдлын үндсийг ойлгосноор л эдгэрч болно.",c:"green"},{t:"Би дэг журам ба эрх чөлөөний хооронд явна — ганцаараа сонгох хэрэгтэй болсон ч.",c:"purple"}]},
    {q:"Дайсан тань ялагдан өмнө тань зогсож байна. Та юу хийх вэ?",opts:[{t:"Дуусга. Өршөөл бол тэд чамд хэзээ ч үзүүлэхгүй сул байдал.",c:"red"},{t:"Өршөөл санал болго — хүн бүрийн сэтгэлд аврагдах чадвар байдаг.",c:"green"},{t:"Тэднийг шударга ёсонд хүлээлгэ. Хууль сахигдах ёстой.",c:"yellow"},{t:"Хойш хазай. Хүч тэдний хувь заяаг шийдэх болно.",c:"white"}]},
    {q:"Хоёр зам харагдаж байна: гүн мэдлэг эсвэл шийдэмгий үйлдэл. Та юуг сонгох вэ?",opts:[{t:"Үйлдэл. Эргэлзэл бол бууж өгөлтийн нэг хэлбэр.",c:"red"},{t:"Мэдлэг. Мэргэн ухаан мянган тулаанаас сэргийлдэг.",c:"green"},{t:"Мэргэн ухааны удирдлага дор үйлдэл — хоёулаа дангаараа бүрэн биш.",c:"blue"},{t:"Хоёрын хоорондох нуугдсан зам. Аль ч туйлшрал надад хангалтгүй.",c:"purple"}]},
    {q:"Таны хамгийн гүн айдас юу вэ?",opts:[{t:"Хамгийн чухал үед хүчгүй байх.",c:"red"},{t:"Надаас хамааралтай хүмүүсийг урвах.",c:"blue"},{t:"Хүчний харанхуйд өөрийгөө алдах.",c:"white"},{t:"Гэрлийг хэн ч санахгүй галактик.",c:"yellow"}]},
    {q:"Цаг тань ирэхэд ямар өв залгамжлал үлдээх вэ?",opts:[{t:"Миний дүр төрхөөр бүрэн бүтээгдсэн шинэ дэг журам.",c:"red"},{t:"Миний золиосоор хамгаалагдсан тоо томшгүй амьдрал.",c:"blue"},{t:"Ирэх үеийнхэнд хадгалагдсан эртний мэргэн ухаан.",c:"green"},{t:"Хуучин шарх ба эртний дайсаглал дээр баригдсан энх тайван.",c:"purple"}]}
  ]
};
const CRYSTALS={
  en:{
    red:{name:"Red Kyber Crystal",path:"Path of the Sith",color:"#ff3030",glow:"#ff5a5a",win:"#ff1a1a",lore:"Your crystal has bled. Through passion, strength, and iron will, you bent the kyber to your desire. The red blade burns with ambition. You walk the path of the Sith — and the Force trembles at your name."},
    blue:{name:"Blue Kyber Crystal",path:"Path of the Jedi Guardian",color:"#1e72ff",glow:"#5098ff",win:"#1050e0",lore:"Your crystal resonates with courage and purpose. You are a shield for the weak and a sword against injustice. The blue blade has chosen a protector — one who acts when others hesitate. The Force stands behind you."},
    green:{name:"Green Kyber Crystal",path:"Path of the Jedi Consular",color:"#22d458",glow:"#44ff78",win:"#18b040",lore:"Wisdom flows through your crystal like light through ancient leaves. The green blade belongs to scholars and healers. You seek understanding before conflict. Knowledge, not power, is your greatest weapon."},
    purple:{name:"Purple Kyber Crystal",path:"Path of the Gray Jedi",color:"#9828f0",glow:"#c060ff",win:"#7818d0",lore:"Extraordinarily rare, your crystal reflects a spirit that forges its own path. Neither fully light nor fully dark, you embody a balance few ever achieve. The purple blade is proof of your unique connection to the Force."},
    yellow:{name:"Yellow Kyber Crystal",path:"Path of the Jedi Sentinel",color:"#ffd700",glow:"#ffe84a",win:"#e8c000",lore:"Your crystal pulses with discipline and vigilance. The yellow blade belongs to Jedi Sentinels — guardians of order who stand watch over the galaxy. Duty defines you, and the Force honors that calling."},
    white:{name:"White Kyber Crystal",path:"Path of the Purified",color:"#d0e8ff",glow:"#f8f8ff",win:"#b0ccf0",lore:"Purified of all darkness, your crystal radiates inner light all its own. The white blade represents total independence — beholden to no Order, no doctrine, only the Living Force itself. You are truly free."}
  },
  mn:{
    red:{name:"Улаан Кибер Болор",path:"Ситийн Зам",color:"#ff3030",glow:"#ff5a5a",win:"#ff1a1a",lore:"Таны болор цус гоожсон. Хүсэл тэмүүлэл, хүч, төмөр зориг дамжуулан та кибер боллорыг өөрийн хүслийн дагуу гнутгасан. Улаан ир шунал тачаалаар шатдаг. Та Ситийн замаар явдаг — Хүч таны нэрнээс чичирдэг."},
    blue:{name:"Цэнхэр Кибер Болор",path:"Жедай Сахиулын Зам",color:"#1e72ff",glow:"#5098ff",win:"#1050e0",lore:"Таны болор зориг ба зорилгоор дуугардаг. Та сул дорой хүмүүсийн бамбай, шударга бус байдлын эсрэг илд юм. Цэнхэр ир хамгаалагчийг сонгосон — бусад эргэлзэх үед үйлддэг хүнийг. Хүч таны ард зогсдог."},
    green:{name:"Ногоон Кибер Болор",path:"Жедай Зөвлөхийн Зам",color:"#22d458",glow:"#44ff78",win:"#18b040",lore:"Мэргэн ухаан эртний навчис дундуур гэрэл мэт таны боллороор урсдаг. Ногоон ир эрдэмтэд ба эдгэрүүлэгчдэд хамаарна. Та зөрчилдөөнөөс өмнө ойлголтыг эрдэг. Мэдлэг — хүч биш — таны хамгийн том зэвсэг юм."},
    purple:{name:"Нил Ягаан Кибер Болор",path:"Саарал Жедайн Зам",color:"#9828f0",glow:"#c060ff",win:"#7818d0",lore:"Маш ховор болор таны өөрийн замаа засдаг сэтгэлийг тусгадаг. Гэрлийн ч, харанхуйн ч бүрэн биш, та цөөхөн хүн хэзээ ч хүрч чадаагүй тэнцвэрийг агуулдаг. Нил ягаан ир таны Хүчтэй ганцгайн холбооны гэрч юм."},
    yellow:{name:"Шар Кибер Болор",path:"Жедай Харуулын Зам",color:"#ffd700",glow:"#ffe84a",win:"#e8c000",lore:"Таны болор сахилга бат ба ажиглалтаар цохилдог. Шар ир Жедай Харуулчдад хамаарна — дэг журам ба хуулийн сахиулагч, галактикийг хянадаг судлаачид. Үүрэг таныг тодорхойлдог бөгөөд Хүч тэр дуудлагыг хүндэтгэдэг."},
    white:{name:"Цагаан Кибер Болор",path:"Цэвэршсэний Зам",color:"#d0e8ff",glow:"#f8f8ff",win:"#b0ccf0",lore:"Бүх харанхуйгаас цэвэршсэн таны болор өөрийнхөө дотоод гэрлээр гэрэлтдэг. Цагаан ир бүрэн тусгаарлалтыг илэрхийлдэг — ямар ч Дэг журам, ямар ч сургаалд бус, зөвхөн Амьд Хүч өөрт захирагддаг. Та үнэхээр чөлөөтэй."}
  }
};

let lang='en',shuffled=[],cur=0,gameOver=false,lastWinner='blue';
const sc2={red:0,blue:0,green:0,purple:0,yellow:0,white:0};
const PARTS=['p-pommel','p-lgrip','p-ugrip','p-emitter'];

function buildShuffled(){shuffled=QS[lang].map(q=>({q:q.q,opts:[...q.opts].sort(()=>Math.random()-0.5)}));}

function setLang(l){
  lang=l;
  document.querySelectorAll('.lang-btn').forEach(b=>b.classList.toggle('active',b.textContent.trim()===(l==='en'?'EN':'МН')));
  document.getElementById('gta').textContent=STRINGS[lang].title;
  document.getElementById('gsb').textContent=STRINGS[lang].subtitle;
  if(gameOver){showResultContent();}else{buildShuffled();showQ(cur);}
}

(function initStars(){
  const cv=document.getElementById('sc');
  cv.width=700;cv.height=600;
  const ctx=cv.getContext('2d');
  const stars=Array.from({length:160},()=>({x:Math.random()*700,y:Math.random()*600,r:Math.random()*1.3+0.2,ph:Math.random()*Math.PI*2}));
  (function anim(){ctx.clearRect(0,0,700,600);const t=Date.now()/1800;stars.forEach(s=>{const a=0.2+0.65*((1+Math.sin(t+s.ph))/2);ctx.beginPath();ctx.arc(s.x,s.y,s.r,0,Math.PI*2);ctx.fillStyle='rgba(200,220,255,'+a.toFixed(2)+')';ctx.fill();});requestAnimationFrame(anim);})();
})();

function showQ(i){
  const d=shuffled[i];
  document.getElementById('qnum').textContent=STRINGS[lang].qLabel(i);
  document.getElementById('qtxt').textContent=d.q;
  const el=document.getElementById('opts');el.innerHTML='';
  d.opts.forEach(o=>{const b=document.createElement('button');b.className='opt';b.textContent=o.t;b.onclick=()=>pick(o.c);el.appendChild(b);});
}

function pick(color){
  document.querySelectorAll('.opt').forEach(b=>b.disabled=true);
  sc2[color]++;
  document.getElementById('pd'+cur).classList.add('done');
  if(cur<PARTS.length){setTimeout(()=>document.getElementById(PARTS[cur]).classList.add('vis'),180);}
  cur++;
  if(cur>=5){gameOver=true;setTimeout(igniteAndReveal,700);}
  else{setTimeout(()=>showQ(cur),320);}
}

function igniteAndReveal(){
  let winner='blue',mx=-1;
  for(const[k,v]of Object.entries(sc2)){if(v>mx){mx=v;winner=k;}}
  lastWinner=winner;
  const c=CRYSTALS[lang][winner];
  document.getElementById('bglow').setAttribute('fill',c.color);
  document.getElementById('bglow').setAttribute('opacity','0.3');
  document.getElementById('bcore').setAttribute('fill',c.color==='#d0e8ff'?'#f0f6ff':c.color);
  document.getElementById('btip').setAttribute('fill',c.glow);
  document.getElementById('cwin').setAttribute('fill',c.win);
  document.getElementById('abtn').setAttribute('fill',c.color==='#ffd700'?'#d4a843':c.color);
  document.getElementById('blade-g').style.opacity='1';
  setTimeout(showResultContent,900);
}

function showResultContent(){
  const c=CRYSTALS[lang][lastWinner];
  document.getElementById('rcol').innerHTML='<div id="cname" style="color:'+c.glow+'">'+c.name+'</div><div id="cpath">'+c.path+'</div><div id="clore">'+c.lore+'</div><button id="rfbtn" onclick="restart()">'+STRINGS[lang].forgeAgain+'</button>';
}

function restart(){
  gameOver=false;cur=0;Object.keys(sc2).forEach(k=>sc2[k]=0);
  PARTS.forEach(id=>document.getElementById(id).classList.remove('vis'));
  const bg=document.getElementById('blade-g');bg.style.transition='none';bg.style.opacity='0';
  setTimeout(()=>bg.style.transition='opacity 1.4s ease',50);
  document.getElementById('bglow').setAttribute('opacity','0');
  document.getElementById('bcore').setAttribute('fill','#ffffff');
  document.getElementById('cwin').setAttribute('fill','#141e30');
  for(let i=0;i<5;i++)document.getElementById('pd'+i).classList.remove('done');
  buildShuffled();
  document.getElementById('rcol').innerHTML='<div id="qnum"></div><div id="qtxt"></div><div id="opts"></div>';
  showQ(0);
}

buildShuffled();showQ(0);
</script>
</body>
</html>
