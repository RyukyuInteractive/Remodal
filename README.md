# Remodal
Cách sử dụng REMODAL + mCustomScrollbar.
1. Cách sử dụng remodal không cho re-open khi click vào nút BACK trên trình duyệt.

        <script>
          $('[data-remodal-id=modal]').remodal({
            hashTracking:false,
          });
        </script>

Trong thẻ <a> ta dùng data-remodal-target=“modal" thay cho href=“#”

2. Remodal với custom modifier
	<script>
		$('[data-remodal-id=modal]').remodal({
			modifier: 'name-class',
		});
	</script>

‘name-class’ là tên class bạn muốn định nghĩa lại.

3. Remodal và mCustomeScrollbar.
	$(window).load(function(){
		$(".remodal-content").mCustomScrollbar({
			theme:"minimal",
		});
	});

Tham khảo các theme khác http://manos.malihu.gr/repository/custom-scrollbar/demo/examples/complete_examples.html

4. Cài đặt khoá màn hình không cho scroll document(đặc biệt trên IOS).
Không cho touchMove trên IOS
	$(document).on('opening', '.remodal', function () {
		document.ontouchmove = function(e){ e.preventDefault(); }
	});

	$(document).on('closing', '.remodal', function (e) {
		document.ontouchmove = function(e){ return true; }
	});
Khoá luôn trong mCustomScrollbar
	$(window).load(function(){
		$(".remodal-content").mCustomScrollbar({
			documentTouchScroll: false,
		});
	});
