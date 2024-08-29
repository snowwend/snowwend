<!DOCTYPE html>
<html>
<header>
  <title>AimHead Mafioso</title>
        <link rel="manifest" href="manifest.json">
  <meta name="viewport" content="width=device-width,initial-scale=1.0,user-scalable=no" />
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
  <link rel="stylesheet" href="https://unpkg.com/element-ui@2.15.7/lib/theme-chalk/index.css">
  <script src="https://cdn.jsdelivr.net/npm/vue@2.6/dist/vue.min.js"></script>
  <script src="https://unpkg.com/element-ui@2.15.7/lib/index.js"></script>

  <style>
    * {
      padding: 0;
      margin: 0;
      color:#fff;
      font-weight: bold;
    }
          body {
            margin: 0;
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-image: url('images/IMG-0484.jpg');
            background-size: cover;
            background-position: center;
            overflow: hidden;
        }

    .ayimgui {
      position: fixed;
      width: 360px;
      height: 320px;
      top: calc(50% - 180px);
      left: calc(50% - 180px);
      z-index: 999;
      background-color: #1C1C1C;
      /* border-radius: 8px; */
      overflow: hidden;
      -webkit-user-select: none;
      -moz-user-select: none;
      -ms-user-select: none;
      user-select: none;
    }

    .onlyTitle {
      height: 22px !important;
    }

    .ayimgui .aytitle {
      padding: 0 5px;
      font-size: 18px;
      background-color: #000;
      border-bottom: 2px solid rgb(200, 217, 233);
    }

    .ayimgui .aytitle .titleClose {
      position: absolute;
      top: 3px;
      right: 6px;
      color: #fff;
    }

    .ayimgui .aytitle .titleClose:hover {
      color: #fff;
    }

    .ayimgui .aybody {
      padding: 15px;
      height: calc(100% - 21px - 15px - 15px);
      /*减去标题高度，减去上线padding高度*/
      overflow: auto;
      font-size: 14px;
    }


    .aytext {
      width: 100%;
      margin-bottom: 10px;
      display: flex;
      flex-direction: column;
      justify-content: space-around;
      color: #000;
    }

    input[type=checkbox]{
 visibility: hidden;
 vertical-align:middle; margin-bottom:1px;
 cursor: pointer;
 position: relative;
 width: 26px;
 height:30px;



}
input[type=checkbox]::after{
 position: absolute;
 top: 0;
 margin-top:1px;
 width: 25px; height: 25px;
 border: 1px solid #fff;
 border-radius: 10px;
 background-color:#000;
 display: inline-block;
 visibility: visible;
 text-align: center;
 content: ' '



}

/* Sửa tất cả các màu thành màu ngẫu nhiên */
input[type=checkbox]:checked::after {
    content: "✓";
    color:#fff;
    border-color: #fff;
    background-color: #000;
    font-size: 20px;
    font-weight: bold;


}



    .onlySelect {
      background-color: rgb(254, 254, 254);
      border: none;
    }

    .onlySelect .el-select-dropdown__item {
      color: #000;

    }

    .onlySelect .el-select-dropdown__item.hover,
    .el-select-dropdown__item:hover:hover {
      background-color: transparent;
    }

    .onlySelect .popper__arrow {
      border-bottom-color: rgb(254, 254, 254) !important;
    }

    .onlySelect.el-popper[x-placement^=bottom] .popper__arrow::after {
      border-bottom-color: rgb(8254, 254, 254) !important;
    }

    .select {
      width: 100%;
    }

    .select .input {
      background-color: rgb(254, 254, 254);
    }

    .select .input__suffix {
      background-color: rgb(160, 196, 243);
      color: #000;
      right: 0;
    }

    .select .select__caret {
      color: #000;
    }

    .select .input__inner {
      background-color: transparent;
      border: none;
      color: #000;
    }

    .select .input .select__caret {
      color: #000;
    }

    /* 解决ios下拉需要点两次 */
    .el-scrollbar .el-scrollbar__bar {
      opacity: 1 !important;
    }



    button {
    width:120px;
    height: 25px;
    background-color: #84848450;
    display: inline-block;
    cursor: pointer;
    text-align: center;
    text-decoration: none;
    outline: none;
    border: none;
    border-radius: 8px;
    margin-right:15px;
    margin-top:10px;
    margin-left:5px;
}

button:active {
     transform: translateY(5px);
}



    buttonl {
    width:55px;
    height: 30px;
    background-color: #84848450;
    display: inline-block;
    cursor: pointer;
    text-align: center;
    text-decoration: none;
    outline: none;
    border: none;
    border-radius: 8px;
    margin-right:15px;
    margin-top:10px;
    margin-left:5px;
    font-size:10px;
}

buttonl:active {
     transform: translateY(5px);
}

        .aycollapse {
      width: 100%;
      font-size: 14px;
      background-color: rgb(177, 206, 240);
      color: #000;
    }


        .aytab {
      width: 10%;
      height: 20px;
      display: flex;

    }





    .aytab span {
      margin-top:10px;
      height: 100%;
      margin-right:10px;


      background-color: rgb(189, 199, 208);
      color: #fff;
      font-size: 14px;

    }

    .el-input input {
      background-color: rgb(254, 254, 254);
      border: none;
      border-radius: 0px;
    }




    .menubox {
            width: 130px;;
            height: 60px;
            line-height: 30px; /*height和line-height设置一样即可文字垂直居中*/
            text-align:center;
            background-color:black;
              border-radius:10px;
              border: 2px solid #fff;
              margin-top:8px;



    }
    .menubox.current {
        background-color: black;
        border: 2px solid #08e6ff;
        border-radius:10px;




    }

    .menuview {
        display:none;
             font-size:20px;
      border-left: 2px solid rgb(200, 217, 233);



    }


    .menuview.current {
        display:block;
    overflow-x: hidden;
        overflow-y: scroll;
        height: 100%;

    }

    .typing-effect {
      white-space: pre;
      font-family: monospace;
      color:#fff;
    }

#colorSelect {
  padding: 10px;
  width:120px;
  font-size: 16px;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #616161;
  color: #000;
}

#colorSelect option {
  padding: 10px;
  background-color: #616161;
  color: #000;
}

#colorSelect option:hover {
  background-color: #ccc;
}
      #cpuInfo {
      font-size: 17px;
      color: #de3a8c;
    }

  #fps {
   font-size: 18px;
   color:  #fc7b03;
  }

      .colorcc {
      animation: color-change 5s infinite;
    }

    @keyframes color-change {
      0%, 100% {
        color: #ff7675;
      }
      25% {
        color: #74b9ff;
      }
      50% {
        color: #55efc4;
      }
      75% {
        color: #ffeaa7;
      }

    #timeWrapper {
      display: flex;
      align-items: center;
    }
    #currentTime,
    #currentSession {
      margin-right: 10px;
    }


  </style>
</header>


<script src="https://apps.bdimg.com/libs/jquery/2.1.4/jquery.min.js"></script>
<script>



$(document).ready(function(){

    $("div.menubox").click(function(){
        $("div.menubox").removeClass("current");
        $("div.menuview").removeClass("current");
        $(this).addClass("current");

        var menuid = $(this).attr("menu");
        $("div#"+menuid).addClass("current");

    });

});

window.onload = function() {
  var elements = document.getElementsByClassName('colorcc');
  var index = 0;

  setInterval(function() {
    for (var i = 0; i < elements.length; i++) {
      elements[i].style.color = getRandomColor();
    }
  }, 2000);

  function getRandomColor() {
    var letters = '0123456789ABCDEF';
    var color = '#';
    for (var i = 0; i < 6; i++) {
      color += letters[Math.floor(Math.random() * 16)];
    }
    return color;
  }

  if ('getBattery' in navigator) {
    navigator.getBattery().then(function (battery) {
      updateBatteryLevel(battery.level * 100);
      battery.addEventListener('levelchange', function () {
        updateBatteryLevel(battery.level * 100);
      });
    });
  }

  function updateCurrentTime() {
       var days = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'];
      var now = new Date();
      var hour = now.getHours();
      var minute = now.getMinutes();
      var second = now.getSeconds();
      var dayOfWeek = days[now.getDay()];

      var timeString = hour + ":" + (minute < 10 ? "0" + minute : minute) + ":" + (second < 10 ? "0" + second : second);
      var colors = ['#ff0000', '#ff4000', '#ff8000', '#ffbf00', '#ffff00', '#bfff00', '#80ff00', '#40ff00', '#00ff00', '#00ff40', '#00ff80', '#00ffbf', '#00ffff', '#00bfff', '#0080ff', '#0040ff', '#0000ff', '#4000ff', '#8000ff', '#bf00ff', '#ff00ff', '#ff00bf', '#ff0080', '#ff0040', '#ff8080', '#ff944d', '#ffaa80', '#ffd480', '#fff4cc', '#ffd8d8', '#f7bdbd', '#ff6666', '#ff4d4d', '#ffcccc', '#ffb3b3', '#ff9999', '#ff3333', '#ff1a1a', '#bf3030', '#804040', '#ff9966', '#ff8533', '#cc6600', '#ffbb33', '#ffcc00', '#ffcc99', '#ffbf80', '#ffad60', '#ff944d'];

      var colorIndex = second % colors.length; 
      document.getElementById("currentTime").innerText = timeString;
      document.getElementById("currentTime").style.color = colors[colorIndex];
      document.getElementById("currentDay").innerText = dayOfWeek;
      document.getElementById("currentDay").style.color = colors[colorIndex];
    }

  setInterval(updateCurrentTime, 1000);

  var cpuCount = window.navigator.hardwareConcurrency; 
  var cpuInfoElement = document.getElementById("cpuInfo");
  cpuInfoElement.innerText =  cpuCount;

  var frameCount = 0;
  var fps = 0;
  var hue = 0;


  function calculateFPS() {
    requestAnimationFrame(function() {
      frameCount++;
      calculateFPS();
    });
  }

  function updateFPS() {
    setTimeout(function() {
      fps = frameCount;
      frameCount = 0;
      document.getElementById("fps").textContent =  fps;
      updateFPS();
    }, 1000);
  }

  calculateFPS();
  updateFPS();
}

        function openLink(url) {
            window.open(url, "_blank");
        }

function changeMenuColor() {
  var colorMap = {
    dark: {
      menuBgColor: "#1C1C1C",
      titleBgColor: "#000000"
    },
    blue: {
      menuBgColor: "#0000FF",
      titleBgColor: "#87CEEB",

    },
    green: {
      menuBgColor: "#008000",
      titleBgColor: "#90EE90"
  },

    pink: {
      menuBgColor: "#b52b9e",
      titleBgColor: "#ff08d6"
    },
    transparent: {
      menuBgColor: "rgba(255, 0, 0, 0.0)",
      titleBgColor: "rgba(255, 0, 0, 0.03)"
    },    

  };

  var selectedColor = document.getElementById("colorSelect").value;
  var menu = document.querySelector('.ayimgui');
  var menuTitle = document.querySelector('.aytitle');

  menu.style.backgroundColor = colorMap[selectedColor].menuBgColor;
  menuTitle.style.backgroundColor = colorMap[selectedColor].titleBgColor;
}

    function runSpeedTest() {
      var imageAddr = "https://www.google.com/images/phd/px.gif"; 
      var downloadSize = 5000000; 

      var download = new Image();
      var startTime = 0;

      setInterval(function() {
        startTime = new Date().getTime();

        download.onload = function() {
          var endTime = new Date().getTime();
          var duration = (endTime - startTime) / 1000; 
          var bitsLoaded = downloadSize * 8;
          var speedBps = (bitsLoaded / duration).toFixed(2);
          var speedMbps = (speedBps / 1000000).toFixed(2);

          document.getElementById("speedResult").innerText = speedMbps + "Ms";
        };
        download.src = imageAddr + "?n=" + Math.random(); 
      }, 1000); 
    }

    runSpeedTest();


</script>
  <script>
    document.addEventListener('DOMContentLoaded', function(){
      const texts = [' Painel Silva, Conde E klay 😈', 'Painel Silva, Conde E klay 😈', 'Painel Silva, Conde E klay 😈','Painel Silva, Conde E klay 😈', ' Painel Silva, Conde E klay 😈', 'Painel Silva, Conde E klay 😈', 'Painel Silva, Conde E klay 😈']; 
      let i = 0;
      let j = 0;
      let isDeleting = false;

      function typeWriter() {
        const currentText = texts[j];
        if(!isDeleting && i <= currentText.length) {
          document.querySelector('.typing-effect').textContent = currentText.substring(0, i);
          i++;
          setTimeout(typeWriter, 140);
          if (i > currentText.length) {
            isDeleting = true;
          }
        } else if (isDeleting && i >= 0) {
          document.querySelector('.typing-effect').textContent = currentText.substring(0, i);
          i--;
          setTimeout(typeWriter, 140);
          if (i === 0) {
            isDeleting = false;
            j = (j + 1) % texts.length; 
          }
        }
      }

      typeWriter();
    });

    </script>
</head>
  <div id="app">
    <div :class="!ifshow?'onlyTitle ayimgui':'ayimgui'" ref="menuMain">
      <div class="aytitle" @touchstart="titleTouchStart" @touchmove="titleTouchMove">
        <i :class="ifshow?'el-icon-caret-bottom':'el-icon-caret-top'" @click="ifshow = !ifshow"></i>
        <span class="colorcc" style="margin-left:77px;font-size:15px;">AimHead @MAFIOSOXITER<img src="https://github.com/WeansHHN/weanshhn.github.io/blob/main/img/gif/gifwaifu.gif?raw=true" alt="weanshhn" width="25" height="25" /> </span>
        <i class="titleClose el-icon el-icon-close" @click="closeimgui"></i>
        </div>


<table id="bodyView" width="100%" style="table-layout:fixed;height: calc(100% - 30px) ;">




<tr>

   <td width="31%" style="vertical-align:top;">

    <div>
    <div class="menubox current"  
 menu="menu1"style="font-size:20px;  font-weight: bold;"></p>Início</div>
    <div class="menubox" menu="menu2"style="font-size:20px;  font-weight: bold;"></p>Funções</div>
    <div class="menubox" menu="menu3"style="font-size:20px;  font-weight: bold;"></p>Breve</div>

        <buttonl onclick="openLink('https://www.tiktok.com/@mafiosoxiter?_t=8owOAlugyY9&_r=1')"style="margin-right:10px;">TIK TOK MEU</buttonl>





    </td>
    </div>
<td style="vertical-align:top" class="scrollbar">
<div id="menu1" class="menuview current">
<span class="typing-effect"></span></p>
Status: <div style="color: #04ff00; display:inline;">Sem Jailbreak!</div><br>
Key: <div class="colorcc" style="display:inline;">MAFIOSO</div><br>
HSD: <div class="colorcc" style="display:inline;">30 Dias</div><br>
 <div id="time">
  <div style="color:#e60e0e;"> Data: 
    <span id="currentDay" class="coloreffect"></span> <span id="currentTime" class="coloreffect"></span></span>

  </div>


    <div style="color:#9f22e3;"> Cpu: 
   <h id="cpuInfo"></h>
   </div>

 <div style="color:#e33522;"> Fps Game:
  <h id="fps"><span></span>0</h>
  </div>
  <div style="color:#d4de14;"> Ping: 
  <span id="speedResult"></span> 
  </div>
  <hr>
  <div style="margin-top:5px;margin-left:5px;">
 Version:1.105.1</div>
</div>
</div>
<div id="menu2" class="menuview">
  <input onclick="fs1(this)" name="radio-group1" type="checkbox" id="checkbox1" />
    <label for="checkbox1" class="checkbox-label" style="margin-right: 20px;">AimHead        </label>

    <input onclick="fs2(this)" name="radio-group2" type="checkbox" id="checkbox2" />
    <label for="checkbox2" class="checkbox-label" style="margin-right: 0px;">AimFov</label><br>

       <input onclick="fs12(this)" name="radio-group12" type="checkbox" id="checkbox12" />
    <label for="checkbox12" class="checkbox-label"style="margin-right: 48px;">AimLock</label>


   <input onclick="fs4(this)" name="radio-group4" type="checkbox" id="checkbox4" />
    <label for="checkbox4" class="checkbox-label"style="margin-right: 0px;">MoveShot</label><p>

 <input onclick="fs5(this)" name="radio-group5" type="checkbox" id="checkbox5" />
  <label for="checkbox5" class="checkbox-label" style="margin-right: 68px;">AimRun</label>

    <input onclick="fs11(this)" name="radio-group11" type="checkbox" id="checkbox11" />
    <label for="checkbox11" class="checkbox-label"style="margin-right: 0px;">AimAssist</label>
    <br>
       <input onclick="fs6(this)" name="radio-group6" type="checkbox" id="checkbox6" />
    <label for="checkbox6" class="checkbox-label"style="margin-right: 35px;">Precision</label>


   <input onclick="fs7(this)" name="radio-group7" type="checkbox" id="checkbox7" />
    <label for="checkbox7" class="checkbox-label"style="margin-right: 0px;">Scope</label><br>

    <input onclick="fs13(this)" name="radio-group13" type="checkbox" id="checkbox13" />
    <label for="checkbox13" class="checkbox-label"style="margin-right: 46px;">Recoil</label>


   <input onclick="fs17(this)" name="radio-group6" type="checkbox" id="checkbox6" />
    <label for="checkbox6" class="checkbox-label"style="margin-right: 0px;">String</label><br>


   <input onclick="fs18(this)" name="radio-group7" type="checkbox" id="checkbox7" />
    <label for="checkbox7" class="checkbox-label"style="margin-right: 48px;">Fix X</label>

       <input onclick="fs19(this)" name="radio-group13" type="checkbox" id="checkbox13" />
    <label for="checkbox19" class="checkbox-label"style="margin-right: 0px;">Fix Y</label>

    </div>


<div id="menu3" class="menuview">



  <button onclick="hn2(this)" class="checkbox-
 button" id="button1"style="color:red;">Aimlock: Off</button>
  <button onclick="hn4(this)" class="checkbox-
 button" id="button2"style="color:red;">Câmera Hack: Off</button><p>

  <button onclick="hn9(this)" class="checkbox-
 button" id="button4"style="color:red;">Duas Armas: Off</button>

  <button onclick="hn10(this)" class="checkbox-
 button" id="button5"style="color:red;">Esp: Off</button>
  <button onclick="hn3(this)" class="checkbox-
 button" id="button6"style="color:red;">Bala Mágica: Off</button>
   <button onclick="hn7(this)" class="checkbox-
 button" id="button7"style="color:red;">Recarga Rápida: Off</button>
  <button onclick="hn1(this)" class="checkbox-
 button" id="button9"style="color:red;">Aimlock: Off</button>


 <div style="color:#04ff00;font-size:15px;margin-left:5px;">Ativar Em Partida As Funções Abaixo 👇 </div>

    <button onclick="hn6(this)" class="checkbox-
 button" id="button11"style="color:red;">Ghost : Off</button>

  <button onclick="hn11(this)" class="checkbox-
 button" id="button12"style="color:red;">Tele Kill: Off</button>
    <p>
  <button onclick="hn8(this)" class="checkbox-
 button" id="button13"style="color:red;">Speed 2x: Off</button>
  <button onclick="hn5(this)" class="checkbox-
 button" id="button14"style="color:red;">Reset Guest: Off</button>
</div>
</div>

    </div>
  </div>



<script>
    var app = new Vue({
      el: "#app",
      data() {
        return {
          ifshow: true,
          checked: false,
          radio: '1',
          activeSelect: '',
          selectOption: [{

          }],
          input: "",
          showOption: false,
          tabValue: "one",
        }
      },
      mounted() {
        this.setRect(360, 320);


        setWindowDrag(0, 0, 0, 0);

        var layout = function()
        {

          if(window.lastorientation==window.orientation) return;
          window.lastorientation=window.orientation;


          if(Math.abs(window.orientation)==90) {

            setWindowRect(0,0,window.screen.height,window.screen.width);
          } else {

            setWindowRect(0,0,window.screen.width,window.screen.height);
          }
        }

        layout(); 
        window.addEventListener("orientationchange", layout, false);

        setButtonAction(function () {
          var menu = document.querySelector("#app");
          if (menu.style.display == 'none') {
            menu.style.display = 'block';

            setWindowTouch(true);
          } else {
            menu.style.display = 'none';

            setWindowTouch(false);
          }
        });
      },

      methods: {
        setRect(w, h, x = -1, y = -1) {
          var boxW = w;
          var boxH = h;

          var ayMenu = this.$refs.menuMain;
          ayMenu.style.width = `${boxW}px`;
          ayMenu.style.height = `${boxH}px`;
          if (x == -1) ayMenu.style.left = `calc(50% - ${boxW / 2}px)`;
          if (y == -1) ayMenu.style.top = `calc(50% - ${boxH / 2}px)`;

  ayMenu.style.width= "470px";
  ayMenu.style.height= "310px";

    ayMenu.style.borderBottomLeftRadius = "10px";
    ayMenu.style.borderBottomRightRadius = "10px";
    ayMenu.style.borderTopLeftRadius = "10px";
    ayMenu.style.borderTopRightRadius = "10px";              
        },
        titleTouchStart(event) {
          this.touchStartX = parseInt(event.touches[0].clientX);
          this.touchStartY = parseInt(event.touches[0].clientY);

          var ayMenu = this.$refs.menuMain;
          this.menuLastX = ayMenu.offsetLeft;
          this.menuLastY = ayMenu.offsetTop;
        },
        titleTouchMove(event) {
          event.preventDefault();
          var distanceX = event.touches[0].clientX - this.touchStartX;
          var distanceY = event.touches[0].clientY - this.touchStartY;

          var ayMenu = this.$refs.menuMain;
          ayMenu.style.left = this.menuLastX + distanceX + "px";
          ayMenu.style.top = this.menuLastY + distanceY + "px";
        },

        changeTab(v) {
          this.tabValue = v;
        },
        closeimgui() {
               var menu = 
document.querySelector("#app");
        menu.style.display='none';


        setWindowTouch(false);

        }
      }
    });
  </script>
  </td>

</tr>

</table>
</body>

</html>