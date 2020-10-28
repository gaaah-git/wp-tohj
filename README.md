# 웹 응용 프로그래밍 5주차

## css
```c
css파일 만들고 이 안에 style.css폴더 만들기
<head>에
<link rel="stylesheet" href="css/style.css">
```
전 시간에는 <head> --> <style> 에서 했던 일을 style.css폴더에서 할 것임
  
## 바탕화면
```c
css에서
body 
{
  background-image: url('../image/05.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  }
  ```
  바탕화면에 이미지를 넣을 때 반복없이 넣을 수 있음 사진이 바탕화면 보다 크면 잘라쓰고 작으면 확대해서 씀  
  ./image/05.jpg ---> ../image/05.jpg 에 주목!
  
  ## 즐겨찾기 바 만들기
  #### !css에서!
  ```c
  header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  display: flex;
  box-sizing: border-box;
  height: 60px;
  border-bottom: 1px solid black;
  align-items: center;
  background-color: rgb(209, 135, 135);
  box-shadow: 0 1px 4px rgba(0, 0, 0, 0.4);
  z-index: 10;
  opacity: 0.8
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
  background-color: black;
  border-radius: 1.5px;
  margin: 3px auto;
}

#side-menu {
  position: fixed;
  display: flex;
  justify-content: space-around;
  top: 60px; /* header의 높이 다음에 나올 수 있도록 */
  left: 0;
  bottom: 0;
  border-right: 1px soli black;
  background-color:rgb(128, 41, 41);
  width: 180px;
  padding: 10px 20px;
  box-shadow: 1px 0 2px rgba(0, 0, 0, 0.4);
  transition-duration: 500ms;
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
color:white;
}

#side-menu > ul > li > a:hover {
  font-weight: bold;
  color: #222;
}
```
#### !html에서!  
```c
<header>
            <button id="menu-button">
              <div class="bar"></div>
              <div class="bar"></div>
              <div class="bar"></div>
            </button>
            <h4>왼쪽 버튼을 누르렴</h4>
          </header>
        
          <nav id="side-menu" class="hidden text2">
            <ul>
              <li><a href="./page1.html">편지</a></li>
            </div>
              <br>
              <li><a href="./page2.html">사진</a></li>
              <br>
              <li><a href="./index.html">home</a></li>
              
            </ul>
          </nav>
         
        
          <script>
            // javascript 코드(다음 주 강의부터 다루게 됨)
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
            });
          </script>
```

