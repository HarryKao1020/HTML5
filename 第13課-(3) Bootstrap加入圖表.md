# 第13課-(3) Bootstrap加入圖表


##### 執行結果:
![GitHub Logo](/imgs/results12-3.jpg)


### 檔案放置方式:
```
   | 
   |___<css>
   |     |___ style.css 
   |     |___ main.css  
   |   
   |___<js>
   |     |___ Chart.bundle.js
   |     |___ my.Chart.bundle.js   
   |   
   |___ index.html 
```



### 檔案名稱: js/Chart.bundle.js
```
在<下載>中下載Chart.bundle.js.zip, 下載後解壓縮
```


### 檔案名稱: js/my.Chart.bundle.js (可參考 http://tobiasahlin.com/blog/chartjs-charts-to-get-you-started/)
```js
var ctx = document.getElementById("myChart").getContext('2d');
var myChart = new Chart(ctx, {
    type: 'bar',
    data: {
        labels: ["一月", "二月", "三月", "四月", "五月", "六月"],
        datasets: [{
            label: '上半年度入館人次(萬人)',
            data: [12, 19, 3, 5, 2, 3],
            backgroundColor: [
                'rgba(255, 99, 132, 0.7)',
                'rgba(54, 162, 235, 0.7)',
                'rgba(255, 206, 86, 0.7)',
                'rgba(75, 192, 192, 0.7)',
                'rgba(153, 102, 255, 0.7)',
                'rgba(255, 159, 64, 0.7)'
            ],
            borderColor: [
                'rgba(255,99,132,1)',
                'rgba(54, 162, 235, 1)',
                'rgba(255, 206, 86, 1)',
                'rgba(75, 192, 192, 1)',
                'rgba(153, 102, 255, 1)',
                'rgba(255, 159, 64, 1)'
            ],
            borderWidth: 1
        }]
    },
    options: {
        scales: {
            yAxes: [{
                ticks: {
                    beginAtZero:true
                }
            }]
        }
    }
});
```


### 檔案名稱: css/style.css
```css
/*==========================================*/
/* 客製化導覽列                              */
/*==========================================*/

/*---------------------------*/
/* 導覽列的商標標顏色           */
/*---------------------------*/
.navbar-custom .navbar-brand{
    color:#FFC;	
}

.navbar-custom .navbar-brand:hover{
    color:#FF0;	
}


/*---------------------------*/
/* 導覽列的背景顏色           */
/*---------------------------*/
.navbar-custom{
    background:#550000;	
}

/*---------------------------*/
/* 導覽列的文字顏色           */
/*---------------------------*/
.navbar-custom ul li a{
    color:#ccc;		
}


/*-----------------------------------*/
/* 導覽列的已被點擊過的項目文字顏色     */
/*-----------------------------------*/
.navbar-custom ul.navbar-nav li a:visited{
    color:#ccc;
}

.navbar-custom ul.dropdown-menu li a:visited{
    color:#000;	
}

/*---------------------------*/
/* 目前所在項目設定           */
/*---------------------------*/
.navbar-custom ul.navbar-nav li.active a{
    background:#000;
    color:#ccc;
}

/*---------------------------*/
/* 目前所在項目滑鼠移          */
/*---------------------------*/
.navbar-custom ul.navbar-nav li.active a:hover{
    background:#000;
    color:#fff;
}

/*---------------------------*/
/* 導覽列的項目滑鼠移入時      */
/*---------------------------*/
.navbar-custom ul.navbar-nav li a:hover{
    background:#801515;
    color:#fff;	
}

/*---------------------------*/
/* 導覽列的項目滑鼠點擊時      */
/*---------------------------*/
.navbar-custom ul.navbar-nav li a:focus{
    background:#801515;
    color:#fff;
}

/*------------------------------*/
/* 導覽列的下拉式項目滑鼠移入時    */
/*------------------------------*/
.navbar-custom ul.navbar-nav li.dropdown a:hover{
    background:#801515;
    color:#fff;
}

/*------------------------------*/
/* 導覽列的下拉式項目滑鼠點擊時    */
/*------------------------------*/
.navbar-custom ul.navbar-nav li.dropdown a:focus{
    background:#801515;
    color:#fff;
}

/*---------------------------*/
/* 下拉式選單背景色           */
/*---------------------------*/
.navbar-custom ul.dropdown-menu{
    background:#FFaaaa;	
}

/*---------------------------*/
/* 下拉式選單文字色           */
/*---------------------------*/
.navbar-custom ul.dropdown-menu li a{
    color:#000;	
}

/*------------------------------*/
/* 下拉式選單滑鼠移入時文字色      */
/*------------------------------*/
.navbar-custom ul.dropdown-menu li a:hover{
    color:#ddd;	
}
```




### 檔案名稱: css/main.css

```css
@charset "utf-8";

/*---------------------------*/
/* 引用思源中文               */
/*---------------------------*/
@import url(http://fonts.googleapis.com/earlyaccess/notosanstc.css);

/*---------------------------*/
/* 定義網頁                   */
/*---------------------------*/
html, body{
    /*設定思源中文*/
    font-family: 'Noto Sans TC', sans-serif;
}
```




### 檔案名稱: index.html
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <title>過得像個人，才能看到美</title>

    <meta name="description" content="Source code generated using layoutit.com">
    <meta name="author" content="LayoutIt!">

    <link href="css/bootstrap.min.css" rel="stylesheet">
    <link href="css/style.css" rel="stylesheet">
    <link href="css/main.css" rel="stylesheet">
    
  </head>
  <body>

  <div class="container-fluid">

  <!-- ...................................................... -->
  <!-- 導覽列                                                 -->
  <!-- ...................................................... -->   
  <div class="row">
    <div class="col-md-12">
      <nav class="navbar navbar-default navbar-custom" role="navigation">

        <!-- ..... -->
        <div class="navbar-header">					 
          <button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1">
          <span class="sr-only">Toggle navigation</span><span class="icon-bar"></span><span class="icon-bar"></span><span class="icon-bar"></span>
          </button> <a class="navbar-brand" href="#">商標</a>
        </div>
        <!-- ..... -->
			
        <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">	
          <!-- ..... -->	
          <ul class="nav navbar-nav">
	
            <li class="active">
              <a href="#">連結1</a>
            </li>
	
            <li>
              <a href="#">連結2</a>
            </li>	
            
            <li class="dropdown">
              <a href="#" class="dropdown-toggle" data-toggle="dropdown">下拉式選單1<strong class="caret"></strong></a>
              <ul class="dropdown-menu">
                <li>
                  <a href="#">選單項目1-1</a>
                </li>
                <li>
                  <a href="#">選單項目1-2</a>
                </li>
                <li>
                  <a href="#">選單項目1-3</a>
                </li>
                <li class="divider">
                </li>
                <li>
                  <a href="#">選單項目1-4</a>
                </li>
                <li class="divider">
                </li>
                <li>
                  <a href="#">選單項目1-5</a>
                </li>
              </ul>
            </li>
	
          </ul>
          <!-- ..... -->	
	
	
          <!-- ..... -->	 
          <form class="navbar-form navbar-left" role="search">
            <div class="form-group">
              <input type="text" class="form-control">
            </div> 
	
            <button type="submit" class="btn btn-default">
              送出
            </button>
          </form>
          <!-- ..... -->	
	
	
          <!-- ..... -->	
          <ul class="nav navbar-nav navbar-right">
            <li>
              <a href="#">連結3</a>
            </li>

            <li class="dropdown">
              <a href="#" class="dropdown-toggle" data-toggle="dropdown">下拉式選單2<strong class="caret"></strong></a>
              <ul class="dropdown-menu">
                <li>
                  <a href="#">選單項目2-1</a>
                </li>
                <li>
                  <a href="#">選單項目2-2</a>
                </li>
                <li>
                  <a href="#">選單項目2-3</a>
                </li>
                <li class="divider">
                </li>
                <li>
                  <a href="#">選單項目2-4</a>
                </li>
              </ul>
            </li>
          </ul>
          <!-- ..... -->	
	
        </div>				
      </nav>
    </div>
  </div>        
  <!-- ...................................................... -->
  <!-- 導覽列結束                                              -->
  <!-- ...................................................... --> 
    
       
        


  <!-- ...................................................... -->
  <!-- 巨無霸標題                                              -->
  <!-- ...................................................... -->           
  <div class="row">
    <div class="col-md-12">            
      <div class="jumbotron">
        <h2>
          蔣勳：過得像個人，才能看到美
        </h2>
        
        <p>
          蔣勳曾說自己是用佈道的心情傳播對美的感動，現在他已經可說是美的宗教家。近幾年來，蔣勳走遍竹科與各地演講，到場的聽眾們彷彿都期待受到「開釋」，除了在席間對於充滿抑揚頓挫的感性分析頻頻點頭，發問的許多也都是已超乎美學的人生之問。
        </p>
      </div>
    </div>
  </div>
  <!-- ...................................................... -->
  <!-- 巨無霸標題結束                                           -->
  <!-- ...................................................... -->
        
    


    
  <!-- ...................................................... -->
  <!-- 新聞列                                                 -->
  <!-- ...................................................... -->
  <div class="row">    
    <!--..................-->    
    <div class="col-md-4">
      <div class="thumbnail">
        <img alt="Bootstrap Thumbnail First" src="http://lorempixel.com/output/people-q-c-600-200-1.jpg" />
        <div class="caption">
          <h3>
            真正的美，作假不得
          </h3>
          <p>
            我原來希望的藝術是能恢復人的品味和人的感覺，但他們接觸了這些東西卻沒有感覺，像有些企業會固定舉辦一些音樂會，但他們卻沒有辦法進入那個世界。所以我現在希望向大家說的是「人的原點」，當我們失去了人的原點，談所有的美都是假的。
          </p>
          <p>
            <a class="btn btn-primary" href="#">Action</a>
          </p>
        </div>
      </div>
    </div>
    <!--..................-->  
        

    <!--..................-->   	
    <div class="col-md-4">
      <div class="thumbnail">
        <img alt="Bootstrap Thumbnail Second" src="http://lorempixel.com/output/city-q-c-600-200-1.jpg" />
        <div class="caption">
          <h3>
            找回人與人之間的感覺
          </h3>
          <p>
            我現在不問工程師有沒有去聽音樂、看展覽，反而是問他們：「你們在這裡工作5年了，有沒有人可以告訴我公司門口那一排是什麼樹？」但很少人能夠回答的出來。事實上，他們公司門口那排小葉欖仁的葉子漂亮得不得了，綠色會在陽光裡發亮。
          </p>
          <p>
            <a class="btn btn-primary" href="#">Action</a>
          </p>
        </div>
      </div>
    </div>
    <!--..................-->  
        

    <!--..................-->  
    <div class="col-md-4">
      <div class="thumbnail">
        <img alt="Bootstrap Thumbnail Third" src="http://lorempixel.com/output/sports-q-c-600-200-1.jpg" />
        <div class="caption">
          <h3>
            週休二日，回來做自己
          </h3>
          <p>
            現在台灣過週休二日，好像非要全家去吃一個餐廳、到哪裡去看薰衣草、喝咖啡，全部整套，然後全部的人塞車塞到一肚子氣。我們對休閒的定義是滿僵化的，好像一定要別人服務我們才算是休閒。
          </p>
          <p>
            <a class="btn btn-primary" href="#">Action</a>
          </p>
        </div>
      </div>
    </div>
    <!--..................-->  
  
  </div>
  <!-- ...................................................... -->
  <!-- 新聞列結束                                              -->
  <!-- ...................................................... -->



  <!-- ...................................................... -->
  <!-- 圖表                                                    -->
  <!-- ...................................................... -->
  <div class="row">
    <div class="col-md-8">
      <!-- 圖表位置 ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->		
        <canvas id="myChart" width="100" height="40">
        </canvas>
      <!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->	        
    </div>
        
    <div class="col-md-4">
      <p class="text-left">
        Lorem ipsum dolor sit amet, <strong>consectetur adipiscing elit</strong>. Aliquam eget sapien sapien. Curabitur in metus urna. In hac habitasse platea dictumst. Phasellus eu sem sapien, sed vestibulum velit. Nam purus nibh, lacinia non faucibus et, pharetra in dolor. Sed iaculis posuere diam ut cursus. <em>Morbi commodo sodales nisi id sodales. Proin consectetur, nisi id commodo imperdiet, metus nunc consequat lectus, id bibendum diam velit et dui.</em> Proin massa magna, vulputate nec bibendum nec, posuere nec lacus. <small>Aliquam mi erat, aliquam vel luctus eu, pharetra quis elit. Nulla euismod ultrices massa, et feugiat ipsum consequat eu.</small>
      </p>
    </div>
  </div>
  <!-- ...................................................... -->
  <!-- 圖表結束                                                -->
  <!-- ...................................................... -->    
 </div>


 <script src="js/jquery.min.js"></script>
 <script src="js/bootstrap.min.js"></script>
 
 <script src="js/Chart.bundle.js"></script>    
 <script src="js/my.Chart.bundle.js"></script>  
     
 <script src="js/scripts.js"></script>


</body>
</html>
```
