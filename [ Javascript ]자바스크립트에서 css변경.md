# jquery 방식
```
$('.top_keyword').css('max-height', '193px');
```
# 한 지정값에 여러개의 css를 지정해야 하는 경우
```
$('.top_keyword').css({'max-height':'193px',
                        'z-index': '999'});
```


# 마우스hover 예시.
```
$('#ingi').hover(
function(){
  $('.top_keyword').css('max-height', '193px');
  $('#depth_areat').show();

})
```
