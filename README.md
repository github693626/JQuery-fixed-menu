# JQuery-fixed-menu

##載入

      <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>


##HTML

      <header>Header</header>
      <div class="fixedWrap">
      	<nav class="nav fixedContent">
      		<a href="#">Item</a>
      		<a href="#">Item</a>
      		<a href="#">Item</a>
      		<a href="#">Item</a>
      		<a href="#">Item</a>
      		<a href="#">Item</a>
      	</nav>
      </div>
      <p>Text</p>


##CSS

      html,body{ margin: 0; padding: 0 }
      header{ height: 80px; background: #ccc; }
      .nav{ background: #eee; padding: 20px; }
      .scrollFixed{ width: 100%; position: fixed; top:0; left: 0; }
      .fixedWrap{ overflow: hidden; }


##JS

      $(function(){
      	var	$fixedWrap =$(".fixedWrap");
      	if($fixedWrap.length > 0){
      		$fixedWrap.each(function() {
      			var $this = $(this);
      			var $fixedContent = $this.find(".fixedContent");
      			var _top = $this.offset().top;
      			$this.css("min-height",$this.height()) 
      			$(window).scroll(function() {
      				if($(this).scrollTop() >= _top){
      					$fixedContent.addClass('scrollFixed');
      				}else{
      					$fixedContent.removeClass('scrollFixed');
      				}
      			});	
      		});	
      	}
      });


