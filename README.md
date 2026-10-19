<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>캐릭터 인터뷰</title>
<style>
:root{--bg:#f5f5f7;--card:#fff;--fg:#1d1d1f;--mute:#86868b;--line:rgba(0,0,0,.1);--glass:rgba(245,245,247,.72);--acc:#0071e3;--fold:#e5e5ea;--shadow:0 8px 24px rgba(0,0,0,.08);box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){--bg:#000;--card:#1c1c1e;--fg:#f5f5f7;--mute:#98989d;--line:rgba(255,255,255,.14);--glass:rgba(28,28,30,.72);--acc:#2997ff;--fold:#3a3a3c;--shadow:0 8px 24px rgba(0,0,0,.5)}}
:root[data-theme="dark"]{--bg:#000;--card:#1c1c1e;--fg:#f5f5f7;--mute:#98989d;--line:rgba(255,255,255,.14);--glass:rgba(28,28,30,.72);--acc:#2997ff;--fold:#3a3a3c;--shadow:0 8px 24px rgba(0,0,0,.5)}
html{scroll-padding-top:calc(env(safe-area-inset-top,0px) + 120px);scroll-behavior:smooth}
body{margin:0;background:var(--bg);color:var(--fg);font-family:-apple-system,BlinkMacSystemFont,"SF Pro Text","Apple SD Gothic Neo","Noto Sans KR",sans-serif;line-height:1.55;-webkit-font-smoothing:antialiased;transition:background .3s,color .3s}
.top{position:sticky;top:env(safe-area-inset-top,0px);z-index:10;background:var(--glass);backdrop-filter:saturate(180%) blur(20px);-webkit-backdrop-filter:saturate(180%) blur(20px);border-bottom:1px solid var(--line)}
.top>div{max-width:760px;margin:0 auto;padding:10px 20px;display:flex;align-items:center;gap:10px}
.top .t{font-weight:600;flex:1;font-size:17px}
.btn{font:inherit;font-size:14px;border:0;border-radius:980px;padding:7px 14px;background:transparent;color:var(--acc);cursor:pointer;transition:opacity .2s,background .2s}
.btn:hover{background:var(--line)}
.btn.fill{background:var(--acc);color:#fff}.btn.fill:hover{opacity:.85;background:var(--acc)}
.btn.red{color:#ff453a}
.icon{width:36px;height:36px;padding:0;display:grid;place-items:center;font-size:17px}
main{max-width:760px;margin:0 auto;padding:28px 20px 90px}
h1{font-size:34px;letter-spacing:-.02em;margin:8px 0 4px}
.sub{color:var(--mute);margin:0 0 28px}
.grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(130px,1fr));gap:22px 14px}
.tile{background:none;border:0;font:inherit;color:inherit;cursor:pointer;text-align:center;padding:10px 4px;border-radius:16px;transition:transform .2s,background .2s}
.tile:hover{background:var(--line);transform:translateY(-2px)}
.tile svg{width:76px;height:96px;filter:drop-shadow(0 6px 10px rgba(0,0,0,.18))}
.tile b{display:block;font-size:14px;font-weight:600;margin-top:6px;overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
.tile small{color:var(--mute);font-size:12px}
.add svg{filter:none}
.view{display:none}.view.on{display:block;animation:in .35s ease}
@keyframes in{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:none}}
.name{width:100%;box-sizing:border-box;font:inherit;font-size:30px;font-weight:700;letter-spacing:-.02em;background:transparent;border:0;color:var(--fg);padding:4px 0;outline:none}
.prog{height:4px;border-radius:2px;background:var(--line);margin:10px 0 6px;overflow:hidden}
.prog i{display:block;height:100%;width:0;background:var(--acc);transition:width .4s}
.meta{display:flex;justify-content:space-between;color:var(--mute);font-size:13px}
.chips{display:flex;gap:8px;overflow-x:auto;padding:16px 0 4px;scrollbar-width:none}
.chips a{flex:none;font-size:13px;color:var(--fg);background:var(--card);border:1px solid var(--line);padding:6px 14px;border-radius:980px;text-decoration:none}
.chips a:hover{border-color:var(--acc);color:var(--acc)}
h2{font-size:22px;letter-spacing:-.01em;margin:40px 0 12px}
.q{background:var(--card);border-radius:18px;padding:18px 18px 14px;margin:12px 0;box-shadow:var(--shadow);border:1px solid var(--line)}
.q label{display:block;font-weight:600;font-size:15px}
.q label span{color:var(--acc);margin-right:8px}
textarea{width:100%;box-sizing:border-box;margin-top:10px;min-height:70px;padding:12px;border:1px solid var(--line);border-radius:12px;background:var(--bg);color:var(--fg);font:inherit;font-size:15px;resize:vertical;transition:border-color .2s,box-shadow .2s}
textarea:focus{outline:0;border-color:var(--acc);box-shadow:0 0 0 4px color-mix(in srgb,var(--acc) 25%,transparent)}
.empty{color:var(--mute);text-align:center;padding:30px 0}
</style>
</head>
<body>
<div class="top"><div>
 <button class="btn" id="back" style="display:none">‹ 보관함</button>
 <span class="t" id="ttl">캐릭터 인터뷰</span>
 <span class="meta" id="st"></span>
 <button class="btn icon" id="th" title="화면 모드 전환">🌙</button>
</div></div>
<main>
<section class="view on" id="home">
 <h1>보관함</h1>
 <p class="sub">캐릭터마다 파일이 하나씩 만들어져요. 파일을 눌러 인터뷰를 이어가세요.</p>
 <div class="grid" id="grid"></div>
</section>
<section class="view" id="edit">
 <input class="name" id="nm" placeholder="캐릭터 이름" maxlength="40">
 <div class="prog"><i id="pg"></i></div>
 <div class="meta"><span id="cnt">0 / 100</span><span><button class="btn" id="ex">내보내기</button><button class="btn red" id="del">삭제</button></span></div>
 <div class="chips" id="chips"></div>
 <div id="qs"></div>
</section>
</main>
<script>
const S=[
["기본 정보",["이름이 무엇인가요? (풀네임, 성, 이름 모두)","이름의 뜻이나 유래가 있나요?","별명이나 애칭이 있나요? 누가 그렇게 부르나요?","나이는 몇 살인가요?","생일은 언제인가요?","별자리나 혈액형이 있다면 무엇인가요?","성별과 성 정체성은 어떻게 되나요?","출신지나 태어난 곳은 어디인가요?","현재 어디에 살고 있나요?","직업이나 신분은 무엇인가요?","종족이나 소속(국가, 단체 등)이 있나요?"]],
["외형",["키와 몸무게는 어느 정도인가요?","체형은 어떤 편인가요?","머리카락의 색과 길이, 스타일은 어떤가요?","눈동자의 색과 눈매는 어떤가요?","피부색이나 피부 상태는 어떤가요?","얼굴형과 이목구비 중 가장 특징적인 부분은 어디인가요?","흉터, 점, 문신 등 눈에 띄는 특징이 있나요?","평소 즐겨 입는 옷 스타일은 무엇인가요?","항상 지니고 다니는 소지품이나 액세서리가 있나요?","자신의 외모 중 가장 마음에 드는 부분은 어디인가요?","자신의 외모 중 가장 콤플렉스인 부분은 어디인가요?","처음 만난 사람들은 당신의 첫인상을 어떻게 말하나요?","목소리는 어떤가요? 말투나 말버릇이 있나요?","걸음걸이나 자세, 습관적인 몸짓이 있나요?"]],
["성격",["스스로 생각하는 자신의 성격은 어떤가요?","주변 사람들이 말하는 당신의 성격은 어떤가요?","스스로 생각하는 장점은 무엇인가요?","스스로 생각하는 단점은 무엇인가요?","가장 화가 나는 순간은 언제인가요?","화가 나면 어떻게 행동하나요?","기쁠 때나 슬플 때 어떻게 표현하나요?","눈물을 자주 흘리는 편인가요? 마지막으로 운 건 언제인가요?","내향적인가요, 외향적인가요?","계획형인가요, 즉흥형인가요?","낙천적인가요, 비관적인가요?","거짓말을 해본 적이 있나요? 가장 최근에 한 거짓말은 무엇인가요?","비밀이 있나요? 누가 알고 있나요?","어떤 상황에서 가장 당황하거나 약해지나요?","인생에서 가장 중요하게 여기는 가치관은 무엇인가요?"]],
["취향과 일상",["좋아하는 음식과 싫어하는 음식은 무엇인가요?","좋아하는 색과 싫어하는 색이 있나요?","좋아하는 계절과 날씨는 무엇인가요?","취미나 특기는 무엇인가요?","못하는 것이나 서툰 것은 무엇인가요?","하루 일과는 어떻게 흘러가나요?","아침형 인간인가요, 저녁형 인간인가요?","잠버릇이나 자기 전 습관이 있나요?","평소 시간이 나면 무엇을 하나요?","무서워하는 것이나 공포증이 있나요?","절대 못 먹거나 못 하는 것이 있나요?","술이나 기호식품은 어떤가요?","돈을 쓸 때 가장 아깝지 않은 곳은 어디인가요?","기분이 안 좋을 때 하는 행동이 있나요?"]],
["과거와 가족",["어린 시절은 어떤 환경에서 보냈나요?","가족 구성원은 어떻게 되나요?","부모님은 어떤 분들이며, 관계는 어땠나요?","형제자매나 가까운 친척이 있나요?","어린 시절 가장 행복했던 기억은 무엇인가요?","어린 시절 가장 힘들었던 기억은 무엇인가요?","학창 시절은 어땠나요? 어떤 학생이었나요?","인생을 바꾼 결정적인 사건이 있다면 무엇인가요?","가장 후회하는 일은 무엇인가요?","되돌릴 수 있다면 바꾸고 싶은 순간이 있나요?","과거에서 아직 해결하지 못한 일이 있나요?","잊고 싶은데 잊히지 않는 기억이 있나요?"]],
["인간관계",["가장 친한 사람은 누구인가요? 어떻게 만났나요?","가장 믿고 의지하는 사람은 누구인가요?","가장 싫어하거나 껄끄러운 사람이 있나요?","지금 사랑하는 사람이나 짝사랑하는 사람이 있나요?","이상형은 어떤 사람인가요?","연애 경험이 있나요? 연애할 때 어떤 편인가요?","처음 만난 사람과 친해지는 데 얼마나 걸리나요?","누군가에게 상처받은 적이 있나요? 용서했나요?","누군가에게 상처를 준 적이 있나요?","가장 소중한 사람을 위해 무엇까지 할 수 있나요?","동물이나 반려동물을 좋아하나요?"]],
["능력과 신념",["가장 자신 있는 능력이나 재능은 무엇인가요?","특별한 힘이나 기술이 있나요? 어떻게 얻었나요?","종교나 신념, 믿고 있는 것이 있나요?","절대 넘지 않는 선이나 지키는 신조가 있나요?","살면서 가장 큰 영향을 준 사람은 누구인가요?","존경하는 사람이나 닮고 싶은 사람이 있나요?","자신에게 '강함'이란 무엇인가요?"]],
["꿈과 미래",["지금 가장 이루고 싶은 목표는 무엇인가요?","어릴 때의 꿈은 무엇이었나요? 지금도 그대로인가요?","인생에서 가장 두려운 일은 무엇인가요?","10년 후의 자신은 어떤 모습이길 바라나요?","하루만 다른 사람이 될 수 있다면 누가 되고 싶나요?","소원이 하나 이루어진다면 무엇을 빌고 싶나요?","죽기 전에 꼭 해보고 싶은 일이 있나요?","자신의 삶을 한 문장으로 표현한다면 무엇인가요?","사람들이 당신을 어떻게 기억해 주길 바라나요?","당신에게 '행복'이란 무엇인가요?","지금 이 인터뷰를 하면서 어떤 기분이 드나요?","지금의 당신을 어린 시절의 당신이 본다면 뭐라고 말할 것 같나요?","가장 아끼는 물건이나 추억이 담긴 물건이 있나요? 그 이유는 무엇인가요?","지금 살고 있는 세상에서 가장 바꾸고 싶은 점이 있다면 무엇인가요?","이 인터뷰에서 숨기고 싶었던 질문이 있었나요?","마지막으로 하고 싶은 말이 있나요?"]]
];
const $=id=>document.getElementById(id);
const LK="ci-v2",OLD="char-interview-answers",TK="ci-theme";
let D={chars:{}},ref=null,cur=null,timer=null,dirty=false;
/* theme */
const root=document.documentElement;
function theme(t){root.dataset.theme=t;$("th").textContent=t==="dark"?"☀️":"🌙";try{localStorage.setItem(TK,t)}catch(e){}}
let t0=null;try{t0=localStorage.getItem(TK)}catch(e){}
theme(t0||(matchMedia("(prefers-color-scheme:dark)").matches?"dark":"light"));
$("th").onclick=()=>theme(root.dataset.theme==="dark"?"light":"dark");
/* build questions */
let n=0;const qs=$("qs"),chips=$("chips");
S.forEach(([t,a],i)=>{
 const h=document.createElement("h2");h.textContent=t;h.id="s"+i;qs.appendChild(h);
 const c=document.createElement("a");c.href="#s"+i;c.textContent=t;chips.appendChild(c);
 a.forEach(q=>{n++;const k="q"+n,d=document.createElement("div");d.className="q";
  const l=document.createElement("label");l.htmlFor=k;const s=document.createElement("span");s.textContent=n;l.append(s,q);
  const ta=document.createElement("textarea");ta.id=k;ta.placeholder="답변을 적어주세요";
  ta.oninput=()=>{if(!cur)return;D.chars[cur].a[k]=ta.value;D.chars[cur].u=Date.now();prog();queue()};
  d.append(l,ta);qs.appendChild(d)})
});
const cnt=c=>Object.values(c.a).filter(v=>v&&v.trim()).length;
function prog(){const c=cnt(D.chars[cur]);$("cnt").textContent=c+" / 100";$("pg").style.width=c+"%"}
/* storage */
function queue(){dirty=true;$("st").textContent="저장 중…";clearTimeout(timer);timer=setTimeout(save,900)}
async function save(){
 clearTimeout(timer);
 try{localStorage.setItem(LK,JSON.stringify(D.chars))}catch(e){}
 if(ref){try{await ref.set({chars:D.chars,updated:Date.now()});$("st").textContent="저장됨";dirty=false;return}catch(e){console.error(e)}}
 $("st").textContent="이 기기에 저장됨";dirty=false}
function lload(){try{const o=JSON.parse(localStorage.getItem(LK)||"null");if(o)return o;
 const old=JSON.parse(localStorage.getItem(OLD)||"null");if(old&&Object.keys(old).length)return{c0:{id:"c0",name:"내 캐릭터",a:old,u:Date.now()}}}catch(e){}return{}}
/* home */
const COL=["#0071e3","#bf5af2","#ff375f","#ff9f0a","#30b0c7","#34c759"];
function icon(name,p,col,plus){
 const ini=plus?"+":(name.trim()[0]||"?");
 return `<svg viewBox="0 0 76 96"><path d="M6 10a8 8 0 0 1 8-8h34l22 22v62a8 8 0 0 1-8 8H14a8 8 0 0 1-8-8z" fill="${plus?"none":"#fff"}" stroke="${plus?"var(--mute)":"rgba(0,0,0,.12)"}" ${plus?'stroke-dasharray="4 4" stroke-width="2"':""}/>${plus?"":`<path d="M48 2v16a6 6 0 0 0 6 6h16z" fill="#e5e5ea"/><rect x="6" y="84" width="${64*p/100}" height="6" fill="${col}"/><rect x="6" y="84" width="64" height="6" fill="${col}" opacity=".18"/>`}<text x="38" y="${plus?58:62}" text-anchor="middle" font-size="${plus?34:30}" font-weight="600" fill="${plus?"var(--mute)":col}" font-family="-apple-system,sans-serif">${ini.replace(/[<&]/g,"")}</text></svg>`}
function home(){
 cur=null;$("back").style.display="none";$("ttl").textContent="캐릭터 인터뷰";
 $("edit").classList.remove("on");$("home").classList.add("on");
 const g=$("grid");g.textContent="";
 Object.values(D.chars).sort((a,b)=>b.u-a.u).forEach((c,i)=>{
  const b=document.createElement("button");b.className="tile";const p=cnt(c);
  b.innerHTML=icon(c.name,p,COL[i%COL.length]);
  const nm=document.createElement("b");nm.textContent=c.name||"이름 없음";
  const sm=document.createElement("small");sm.textContent=p+"/100 완료";
  b.append(nm,sm);b.onclick=()=>open(c.id);g.appendChild(b)});
 const a=document.createElement("button");a.className="tile add";a.innerHTML=icon("",0,"",true)+"<b>새 캐릭터</b>";
 a.onclick=()=>{const id="c"+Date.now().toString(36);D.chars[id]={id,name:"",a:{},u:Date.now()};open(id);queue()};
 g.appendChild(a)}
function open(id){
 cur=id;const c=D.chars[id];
 $("home").classList.remove("on");$("edit").classList.add("on");$("back").style.display="";$("ttl").textContent="";
 $("nm").value=c.name;
 for(let i=1;i<=100;i++)$("q"+i).value=c.a["q"+i]||"";
 prog();scrollTo(0,0);if(!c.name)$("nm").focus()}
$("nm").oninput=e=>{if(cur){D.chars[cur].name=e.target.value;D.chars[cur].u=Date.now();queue()}};
$("back").onclick=async()=>{if(cur&&!D.chars[cur].name.trim()&&!cnt(D.chars[cur]))delete D.chars[cur];await save();home()};
let dt=null;
$("del").onclick=async e=>{
 if(!dt){e.target.textContent="정말 삭제할까요?";dt=setTimeout(()=>{dt=null;e.target.textContent="삭제"},3000);return}
 clearTimeout(dt);dt=null;e.target.textContent="삭제";delete D.chars[cur];await save();home()};
$("ex").onclick=async()=>{
 const c=D.chars[cur];let k=0,txt=(c.name||"캐릭터")+" 인터뷰\n\n";
 S.forEach(([t,a])=>{txt+="■ "+t+"\n\n";a.forEach(q=>{k++;txt+=k+". "+q+"\n"+(c.a["q"+k]||"(미답변)")+"\n\n"})});
 try{const d=await claude.use("downloads");if(d){await d.save({filename:(c.name||"character")+"-interview.txt",data:txt});return}}catch(e){if(e&&e.code==="declined")return}
 const u=URL.createObjectURL(new Blob([txt],{type:"text/plain"})),a=document.createElement("a");a.href=u;a.download=(c.name||"character")+".txt";a.click()};
/* init */
D.chars=lload();home();
(async()=>{try{
 const cl=window.claude;if(!cl)return;
 const user=await cl.use("user"),db=await cl.use("db");if(!user||!db)return;
 const id=await user.id();ref=db.doc("data/users/"+id+"/interview");
 const s=await ref.get();
 if(dirty){await save();return}
 if(s.exists){const d=s.data()||{};
  if(d.chars)D.chars=d.chars;
  else if(d.answers)D.chars={c0:{id:"c0",name:"내 캐릭터",a:d.answers,u:d.updated||Date.now()}};
  if(!cur)home()}
 else if(Object.keys(D.chars).length)await save();
}catch(e){console.error(e)}})();
</script>
</body>
</html>
