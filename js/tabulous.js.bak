(function($){
	$.fn.extend({
		//插件名字
		tabs: function(options){
			//参数和默认值
			var defaults = {
				effect: 'scale'
			},
			options = $.extend(defaults,options);
			init();

			var o = options,
				obj = $(this),
				items = $('li a',obj);
			items.click(function(){
				var alldivs = $('#tabs').find('#tabs_container div'),
					thisform = $(this).closest('#tabs'),
					thislink = $(this).attr('href'),
					firstdiv = $('#tabs_container');	
				firstdiv.addClass('transition');
				$('#tabs ul li a').removeClass('tabulous_active');
				$(this).addClass('tabulous_active');
				var thisdivheight = thisform.find('div'+thislink).height()
				alldivs.removeClass('showscale').addClass('make_transist hidescale')
				thisform.find('div'+thislink).addClass('make_transist showscale')
				firstdiv.css('height',thisdivheight+'px');
			});
		},
		tabsBg: function(options){
			//参数和默认值
			var defaults = {
				background: '#f5f5f5'
			},
			options = $.extend(defaults,options);

			return this.each(function(){
				var o = options,
					obj = $(this);
				obj.click(function(){
					obj.closest('html').toggleClass('f5');
					obj.next().find('li a').toggleClass('f5');
				})
			});
		}
	});
	$.fn[tabs] = function ( options ) {
        return this.each(function () {
            new tabs( this, options );
        });
    };
})(jQuery);
function init(){
	var firstchild = $('#tabs ul').find('li:first-child').find('a'),
		lastchild = $('#tabs ul').find('li:last-child').after('<span class="tabulousclear"></span>');
	$('#tabs_container div').not(':first').not(':nth-child(1)').addClass('hidescale');
	var	firstdiv = $('#tabs_container'),
		firstdivheight = firstdiv.find('div:first').height(),		
		alldivs = $('#tabs').find('#tabs_container div');
	alldivs.css({'position': 'absolute','top':'40px'});
	firstdiv.css('height',firstdivheight+'px');
	firstchild.addClass('tabulous_active');
}
//使用插件
$(function() {
    $("#tabs").tabs({ effect: 'scale' });
	$("#tabs2").tabsBg({ background: '#655c89' });	
});

