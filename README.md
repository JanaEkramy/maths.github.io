

<head>
    <title>calc test</title>
</head>
<body>
    <h1>مرحبا بك في مشروع رياضيات 6<br> الخاص بي </h1>
    <p> طول متجه الوحدة باستعمال متجه الوحدة</p>
    <button id="btn1" onclick="lengthOfUnitVector()">اضغط هنا</button>
    <p>ضرب المتجهات</p>
    <button id="btn2" onclick="multiplyUnitVector()">اضغط هنا</button>
    <p>ايجاد طول المتجه باستعمال نقطة البداية والنهاية</p>
    <button id="btn3" onclick="lengthoOfUnitVectorXY()">اضغط هنا</button>
    <p>ايجاد الصورة الاحداثية لمتجه</p>
    <button id="btn4" onclick="componentForm()">اضغط هنا</button>
    <p>ايجادالصورة القطبية للعدد المركب</p>
    <button id="btn5" onclick="polarFormOfComplexNumber()">اضغط هنا</button> <!--function not completed-->
    <p>ايجاد القيمة المطلقة للعدد المركب</p>
    <button id="btn6" onclick="absComplexNumber()">اضغط هنا</button>
    <p>التحويل من احداثيات قطبية الى ديكارتية</p>
    <button id="btn7" onclick="polarToRectangle()">اضغط هنا</button> 
    <p>التحويلات من احداثيات ديكارتية الى قطبية</p>
    <button id="btn8" onclick="rectangleToPolar()">اضغط هنا</button> 
    <p>المتوسط والتباين والانحراف المعياري للتوزيع ذو الحدين</p>
    <button id="btn9" onclick="averageContrastStandardDeviation()">اضغط هنا</button>
    <p>كتابة متجه على صورة توافق خطي لمتجه الوحدة</p>
    <button id="btn10" onclick="linearCombination()">اضغط هنا</button>


    
    <div id="box"> 
        <p id="txt">ستظهر الاجابة هنا</p>
        <p id="space"></p>
    </div>
    
    
</body>
<script>
    window.onload
        function lengthOfUnitVector(){
            var a = parseInt(prompt('ادخل a'))
            var b = parseInt(prompt('ادخل b'))
            var num = a**2+b**2;
            var res = Math.sqrt(num)
            var space = document.getElementById('space');
            space.innerHTML=res
        }
        function multiplyUnitVector(){
            var a = parseInt(prompt('ادخل a'));
            var b = parseInt(prompt('ادخل b'));
            var c = parseInt(prompt('ادخل المعامل'))
            var res = (c*a +','+c*b);
            var space = document.getElementById('space');
            space.innerHTML=res;
        }
        function lengthoOfUnitVectorXY(){
            var x1=parseInt(prompt('ادخل x1'));
            var x2=parseInt(prompt('ادخل x2'));
            var y1=parseInt(prompt('ادخل y1'));
            var y2=parseInt(prompt('ادخل y2'));
            var num= (x2-x1)**2 + (y2-y1)**2;
            var res= Math.sqrt(num);
            var space = document.getElementById('space');
            space.innerHTML=res;
        }
        function componentForm(){
            var x1=parseInt(prompt('ادخل x1'));
            var x2=parseInt(prompt('ادخل x2'));
            var y1=parseInt(prompt('ادخل y1'));
            var y2=parseInt(prompt('ادخل y2'));
            var res=('('+(x2-x1)+','+(y2-y1)+')');
            var space = document.getElementById('space');
            space.innerHTML=res;
        }
        function polarFormOfComplexNumber(){
            var a = parseFloat(prompt('ادخل a'));
            var b = parseFloat(prompt('ادخل b'));
            function radians_to_degrees(radians)
                {
                var pi = Math.PI;
                return radians * (180/pi);
                }
            function degrees_to_radians(degrees)
                {
                var pi = Math.PI;
                return degrees * (pi/180);
                }
            if(a>0){
                var num= ( Math.atan((b/a)));
                num = num.toFixed(3)
            }
            else if(a<0){
                var num= radians_to_degrees(Math.atan(degrees_to_radians(b/a)))+Math.pi //returns wrong numbers
            }
            else if(a==0){
                if(b>0){
                    var num=90
                }
                else if(b<0){
                    var num=-90
                }
            }
            var r = ((a**2)+(b**2));
            r = Math.sqrt(r);
            var res= r+'(cos'+num+'+ i sin'+num+')'
            var space = document.getElementById('space');
            space.innerHTML=res;
        }
        function absComplexNumber(){
            var a = parseInt(prompt('ادخل a'));
            var b = parseInt(prompt('ادخل b'));
            var num= (a**2)+(b**2);
            var res= Math.sqrt(num);
            var space = document.getElementById('space');
            space.innerHTML=res;
        }
        function polarToRectangle(){
            function degrees_to_radians(degrees)
            {
            var pi = Math.PI;
            return degrees * (pi/180);
            }
            var r = parseFloat(prompt('ادخل r'));
            var theta=parseInt(prompt('ادخل theta'));
            var x= r*(Math.cos(degrees_to_radians(theta)));
            var y= r*(Math.sin(degrees_to_radians(theta)));
            var res= ('('+x+','+y+')')
            var space = document.getElementById('space');
            space.innerHTML=res;
        }
        function rectangleToPolar(){
            function radians_to_degrees(radians)
                {
                var pi = Math.PI;
                return radians * (180/pi);
                }
            var x= parseInt(prompt('ادخل x'));
            var y = parseFloat(prompt('ادخل y'));
            if (x>0){
                var theta= radians_to_degrees(Math.atan(y/x));
                var r = ((x**2)+(y**2));
                r= Math.sqrt(r);
            }
            else if (x<0){
                var theta= radians_to_degrees(Math.atan(y/x))+180;
                var r = ((x**2)+(y**2));
                var r = Math.sqrt(r);
            }
            else if (x==0){
                if (y>0){
                    var r=y;
                    var theta=90;
                }
                else if(y<0){
                    var r=y;
                    var theta=-90;
                }
            }
            var res= (r+','+theta);
            var space = document.getElementById('space');
            space.innerHTML=res;
            }

    function averageContrastStandardDeviation(){
        var n=parseInt(prompt('ادخل n'));
        var p=parseFloat(prompt('ادخل p'));
        var q=parseFloat(prompt('ادخل q'));
        var avr= n*p;
        var contrast=n*p*q;
        var standardDeviation=Math.sqrt(contrast);
        var out1= 'المتوسط =' +avr+'\n';
        var out2= 'التباين =' +contrast +'\n';
        var out3= 'الانحراف المعياري ='+standardDeviation+'\n';
        var res = out1+'\n'+out2+'\n'+out3 //still worth trying
        var space = document.getElementById('space');
        space.innerHTML= res ;
    }
    function linearCombination(){
        var x1=parseInt(prompt('ادخل x1'));
        var x2=parseInt(prompt('ادخل x2'));
        var y1=parseInt(prompt('ادخل y1'));
        var y2=parseInt(prompt('ادخل y2'));
        var res= ('('+(x2-x1)+'i'+'+'+(y2-y1)+'j)')
        var space = document.getElementById('space');
        space.innerHTML= res ;
    }


</script>


<style>
    #box{
        height: 120px;
        width: 300px;
        background: coral;
    }
    p{
      font-size: larger;  
    }
    body{
        background-color: paleturquoise;
        text-align: right;
    }
    h1{
        color: palevioletred;
    }

</style>
