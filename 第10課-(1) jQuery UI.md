# 第10課 jQuery UI


## (1) 改背景色及位置 

##### 執行結果:
![GitHub Logo](/imgs/results10-1.jpg)


##### 檔案放置方式:
```
   | 
   |___<css>
   |     |___ main.css
   |
   |___<js>
   |     |___ scripts.js   
   | 
   |___index.html   
```


##### 檔案名稱: index.html 
```html
<!doctype html>
<html>
<head>
<meta charset="utf-8">
<title>測試網頁</title>
<!--*********-->
<!-- 加入css -->
<!--*********-->
<link rel="stylesheet" href="http://code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
<link href="css/main.css" rel="stylesheet" type="text/css" />
</head>
<body>
    <!-- *** 容器區塊 *** -->
    <div class="container">     
        <!-- 表頭 -->
        <div class="header">
            過得像個人，才能看到美
        </div>


        <!-- 內文 --> 
        <div class="content">              
            <!--###############################--> 
            <div class="itemRow">              
                <!--(1)-->   
                <a href="#">   
                    <div class="item">
                        <h3>真正的美，作假不得 </h3>    
                        <p>我原來希望的藝術是能恢復人的品味和人的感覺，但他們接觸了這些東西卻沒有感覺，像有些企業會固定舉辦一些音樂會，但他們卻沒有辦法進入那個世界。所以我現在希望向大家說的是「人的原點」，當我們失去了人的原點，談所有的美都是假的。我有一個朋友，住在信義路上億元的豪宅，找了日本最有名的設計師來裝潢，但有一次我去他家，發現他住了2年.....</p>
                    </div>
                </a>  

                <!--(2)-->  
                <a href="#">
                    <div class="item">
                        <h3>找回人與人之間的感覺 </h3>    
                        <p>我現在不問工程師有沒有去聽音樂、看展覽，反而是問他們：「你們在這裡工作5年了，有沒有人可以告訴我公司門口那一排是什麼樹？」但很少人能夠回答的出來。事實上，他們公司門口那排小葉欖仁的葉子漂亮得不得了，綠色會在陽光裡發亮。後來我再去，就有一個員工和我說，「謝謝你告訴我這件事，我現在下班時會先看看小葉欖仁再回家 ，所以比較不會..... </p>
                    </div>
                </a>

                <!--(3)-->  
                <a href="#">
                    <div class="item">
                        <h3>週休二日，回來做自己 </h3>    
                        <p>現在台灣過週休二日，好像非要全家去吃一個餐廳、到哪裡去看薰衣草、喝咖啡，全部整套，然後全部的人塞車塞到一肚子氣。我們對休閒的定義是滿僵化的，好像一定要別人服務我們才算是休閒。我自己假日的時候喜歡自己一個人做4菜1湯，因為我覺得做菜好快樂。我也很喜歡在週休二日洗我自己最喜歡的純棉的、純麻的襯衫，絕不丟給洗衣機，因為我覺得.....</p>
                    </div>
                </a>
                
                <div class="clear"></div>                                
            </div>
            <!--###############################-->             
        </div>


        <!-- 表尾 -->
        <div class="footer">
            NTUB imd, 2017.    
        </div>        
    </div>
    <!--*********-->
    <!-- 載入js  -->
    <!--*********-->
    <script src="https://code.jquery.com/jquery-1.12.4.js"></script>
    <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>      
    <script src="js/scripts.js"></script>
</body>
</html>
```


##### 檔案名稱: css/main.css
```css
@charset "utf-8";

/*---------------------------*/
/* 引用思源中文                */
/*---------------------------*/
@import url(http://fonts.googleapis.com/earlyaccess/notosanstc.css);


/*---------------------------*/
/* 定義網頁                   */
/*---------------------------*/
html, body{
    font-size:17px;
    /*設定思源中文*/
    font-family: 'Noto Sans TC', sans-serif;
    font-weight: 280;   
    background:#444;    
}


div.clear{
    clear:both;
}


/*---------------------------*/
/* 定義容器                   */
/*---------------------------*/
div.container{
    width:800px;
    border:1px solid #666;  
    margin:10px auto 10px auto;   
    background:#fff;
    box-shadow:0px 0px 10px 0px #000;
}


/*---------------------------*/
/* 定義標題                   */
/*---------------------------*/
div.header{
    height:150px;
    background:#CCC;
    font-size:40px;
    text-align:center;
    line-height:150px;
    letter-spacing:7px;
}


/*---------------------------*/
/* 定義內容                   */
/*---------------------------*/
div.content{       
    padding:0px 25px 20px 25px;
}

div.content div.itemRow{
    width:100%;
    margin-top:25px;
    margin-bottom:25px; 
}

div.itemRow div.item{       
    width:230px;
    height:440px;
    box-sizing:border-box;
    float:left; 
    overflow:hidden;    
    border:1px solid #000;
    box-shadow:0px 0px 2px 0px #000;       
}

/* 第1, 2個元素 */
div.itemRow a:nth-child(1) div.item,
div.itemRow a:nth-child(2) div.item{
    margin-right:30px;
}

div.item h3{
    padding:0 12px;
    color:#000;
}

div.item p{
    padding:0px 12px 15px 12px;     
    text-align:justify;
    color:#000;
}


/*---------------------------*/
/* 定義表尾                   */
/*---------------------------*/
div.footer{
    height:100px;
    line-height:100px;
    background:#CCC;
    font-size:13px;
    text-align:center;
    letter-spacing:3px;
}
```



##### 檔案名稱: js/scripts.js
```js
// Easing函數使用: easings.net/zh-tw

$(function(){
    // 滑鼠移入	
    $('.item').mouseenter(function(){
        //---------------------
        $(this).stop().animate(
            {
                marginTop:-10,
                backgroundColor:'#ffc'
            }, 
            {
                duration:300,
                easing:'easeOutBounce'
            }
        ); 
        //---------------------
    });	

    // 滑鼠移出	
    $('.item').mouseleave(function(){
        //---------------------
        $(this).stop().animate(
            {
                marginTop:0,
                backgroundColor:'#fff'
            }, 
            {
                duration:50
            }
        );
        //---------------------        
    });		
});
```


