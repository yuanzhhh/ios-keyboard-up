# ios-keyboard-up
ios软键盘弹起解决输入框被遮挡和或顶部栏消失问题

fixed定位

1.ios下fixed元素容易定位出错，软键盘弹出时，影响fixed元素定位
2.android下fixed表现要比iOS更好，软键盘弹出时，不会影响fixed元素定位
3.ios4下不支持position:fixed

解决方案：使用[Iscroll](http://cubiq.org/iscroll-5)，如：
  <div id="wrapper">
          <ul><li></li></ul>
  </div>
  <script src="iscroll.js"></script>
  <script>
      var myscroll;
      function loaded(){
          myscroll=new iScroll("wrapper");
      }
      window.addEventListener("DOMContentLoaded",loaded,false);
  </script>

position定位

Android下弹出软键盘弹出时，影响absolute元素定位

解决方案:

 <script>
    var ua = navigator.userAgent.indexOf('Android');
    if(ua>-1){
        $('.ipt').on('focus', function(){
            $('.css').css({'visibility':'hidden'})
        }).on('blur', function(){
            $('.css').css({'visibility':'visible'})
        })
    }
  </script>
