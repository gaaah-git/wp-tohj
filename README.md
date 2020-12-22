## 사이드 바 만들기(집어넣었다 뺐다 가능)
```c
*****html에*****

<link rel="stylesheet" href="css/style1.css">
</head>

<body>
    <header>
        <button id="menu-button">
            <div class="bar"></div>
            <div class="bar"></div>
            <div class="bar"></div>
        </button>
        <h5>Happy Birthday</h5>
    </header>

    <nav id="side-menu" class="hidden">
        <ul>

            <li><a href="./page1.html">photo</a></li>
            <li><a href="./page2.html">gift</a></li>

            <li><a href="./index.html">letter</a></li>



        </ul>
    </nav>

    <script>

        let hidden = true;
        const menuButton = document.getElementById('menu-button');
        const sideMenu = document.getElementById('side-menu');

        menuButton.addEventListener('click', () => {
            if (hidden) {
                sideMenu.classList.remove('hidden');
                hidden = false;
            } else {
                sideMenu.classList.add('hidden');
                hidden = true;
            }
        
    </script>
    
    *****style1.css에*****
    
    * {
  margin: 0;
  padding: 0;
}


  header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    display: flex;
    box-sizing: border-box;
    height: 60px;
    border-bottom: 1px solid rgb(112, 58, 58);
    align-items: center;
    background-color: rgb(124, 45, 45);
    box-shadow: 0 1px 4px rgba(0, 0, 0, 0.4);
    z-index: 10;
  }
  
  main {
    margin: 60px auto 0; 
    padding: 2em 4em;
  }
  main > p {
    margin-top: 2em;
    text-align: justify;
  }
  
  #menu-button {
    width: 40px;
    border: none;
    background-color: transparent;
    padding: 10px;
    cursor: pointer;
    margin-right: 2em;
  }
  
  #menu-button:focus {
    outline: none;
  }
  
  #menu-button > .bar {
    width: 100%;
    height: 3px;
    background-color: #333;
    border-radius: 1.5px;
    margin: 3px auto;
  }
  
  #side-menu {
    position: fixed;
    top: 60px; 
    left: 0;
    bottom: 0;
    border-right: 1px solid rgb(71, 44, 35);
    background-color: rgb(146, 110, 90);
    width: 200px;
    padding: 10px 20px;
    box-shadow: 0 1px 4px rgba(0, 0, 0, 0.4);
    transition-duration: 500ms;
    z-index: 1;
    
  }
  
  #side-menu.hidden {
    left: -100%;
  }
  
  #side-menu > ul {
    list-style: none;
  }
  
  #side-menu > ul > li {
    margin: 20px 0;
  }
  
  #side-menu > ul > li > a {
    text-decoration: none;
    color: black;
  }
  #side-menu > ul > li > a:hover {
    font-weight: bold;
    color: #222;
  }

```
### 이후에 Happy Birhday를 추가하니 사이드 바가 제대로 작동하지 않는 현상이 발생했음. 이 때, 사이드메뉴에 z-index: 1 을 걸어주니 해결되었음.

## 사진 
```c
<style>
        body {
            background-color: rgb(42, 71, 36);

        }
        * {
    margin: 0;
    padding: 0;
  }
  
  .container {
    display: grid;
    width: 1200px;
    grid-template-columns: repeat(4, 300px);
    grid-auto-rows: 400px;
    grid-auto-flow: row dense;
    margin: 20px auto;
  }
  
  
  img {
    width: 100%;
    height: 100%;
    opacity: 1;
  }
  
  img:hover {
    transform: scale(1.3);
    opacity: 1;
    z-index: 1;
}
.box{
  width: 1600px;
  height: 800px;
  margin-top: 100px;
  margin-left: 300px;
}
</style>
----------------------------------------
<body>
<div class="container box">
      <img src=./image/11.jpg>
      <img src=./image/12.jpg>
      <img src=./image/13.jpg>
      <img src=./image/14.jpg>
      <img src=./image/15.jpg>
      <img src=./image/16.jpg>
      <img src=./image/17.jpg>
      <img src=./image/18.jpg>
      
 </body>

```
### hover: 마우스를 갖다 대면,

## 키프레임
```c
<style>
       .container {
            width: 100%;
            height: 300px;

            background-position: center center;
            background-size: cover;
            background-blend-mode: overlay;
            position: relative;
            overflow: hidden;
        }

        .container1 {
            width: 100%;
            height: 300px;
            margin-left: 800px;
            margin-top: 50px;

            background-position: center center;
            background-size: cover;
            background-blend-mode: overlay;
            position: relative;
            overflow: hidden;
        }

        .container>* {
            position: absolute;
        }

        .container>h1 {
            top: 80px;
            left: 100px;
            color: white;
            font-size: 7rem;
            animation-name: banner-title;
            animation-duration: 2s;
            animation-timing-function: ease-out;
        }


        @keyframes banner-title {
            from {
                left: -50%;
            }

            to {
                left: 200px;
            }
        }



        .container1>p {
            top: 150px;
            left: 60px;
            width: 40%;
            color: rgb(255, 255, 255);
            animation-name: banner-content;
            animation-duration: 6s;
        }




        @keyframes banner-content {
            from {
                opacity: 0;
            }

            to {
                opacity: 1;
            }
        }
    </style>
    ----------------------------------------
    <div class="container">
    <h1>Happy Birthday</h1>
    </div>

    <div class="container1">
    <p>To. .....</p>
```

### @keyframes <이름주기> ---> css에서 animation-name: <아까 준 이름> 으로 사용
