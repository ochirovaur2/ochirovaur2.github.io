
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Project</title>
	<link rel="stylesheet" href="jquery-ui-1.12.1/jquery-ui.min.css">
	<link rel="stylesheet" type="text/css" href="style.css">
	<script src="jquery-ui-1.12.1/external/jquery/jquery.js"></script>
	<script src="jquery-ui-1.12.1/jquery-ui.min.js"></script>


	<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.6.1/css/all.css">

</head>
<body>
	<header>
		<div id="Logo">
			<i class="far fa-keyboard"> CodePlayer</i>
			<p id="textLogo">Code your program!</p>
			
		</div>
		
   		
		<div id="buttonContainer">

			<div class="toggleButton active" id="html">HTML &#10155;</div>
			<div class="toggleButton" id="css">CSS &#10155;</div>
			<div class="toggleButton" id="javascript">JS &#10155;</div>
			<div class="toggleButton active" id="output">Output &#10004;</div>
		</div>
		<div id="switchOutput">
			<label for="Automatic" id="labelForAutomatic">Automatic</label>
			<input type="radio" name="r"  onchange="check()" id="Automatic" checked="checked"><br/> 
			<label for="OnClick" id="labelForOnClick">OnClick</label>
			<input type="radio" name="r"  onchange="check()" id="OnClick"><br/>
		
		</div>
		
	</header>
	<main>
		<div id="accordion">
			<h3>HTML</h3>
			<div class="box">
			<textarea id="htmlPanel" class="panel" placeholder="строка">
				
			</textarea>
			</div>
			<h3>CSS</h3>
			<div><textarea id="cssPanel" class="panel" placeholder="строка">
				
			</textarea>
			</div>
			<h3>JavaScript</h3>
			<div>
			<textarea id="javascriptPanel" class="panel" placeholder="строка">
				
			</textarea>
			</div>
		</div>
		<div class="clear">
			
		</div>
		<iframe id="outputPanel"></iframe>
	</main>
	<script type="text/javascript">
		
		
		$(function() {
			$("#accordion").accordion();
		});
		$("textarea").on("change keyup paste", function(){
					updateOutput();
					});
					
			        function updateOutput() {
						$("iframe").contents().find("html").html("<html><head><style type='text/css'>" + $("#cssPanel").val() +"</style></head><body>" +  $("#htmlPanel").val() + "</body></html>");
						document.getElementById("outputPanel").contentWindow.eval($("#javascriptPanel").val());
					};
		 function check(){
			  var rarr=document.getElementsByName("r");
			  if(rarr[0].checked){
				  	$("textarea").on("change keyup paste", function(){
					updateOutput();
					});
					
			        function updateOutput() {
						$("iframe").contents().find("html").html("<html><head><style type='text/css'>" + $("#cssPanel").val() +"</style></head><body>" +  $("#htmlPanel").val() + "</body></html>");
						document.getElementById("outputPanel").contentWindow.eval($("#javascriptPanel").val());
					};
			  } if(rarr[1].checked) {
			  		
					
			      
						$("textarea").on("change keyup paste", function(){
						$("iframe").contents().find("html").html("<html><head><style type='text/css'>div { position: absolute;left: 0%;top:0%;background-color: #4B4A45; width: 100%; height: 100%; text-align:center;}p{position: absolute;left: 50%;top:50%;transform: translate(-50%,-50%);color:  white;transition: 0.8s;text-align: center; }span{font-size: 200%; transition: 0.2s;}</style></head><body><div><p>Editing process in progress</p></div></body></html>");
							
						});
					
			  		
			  		$("#output").click(function() {
						$("iframe").contents().find("html").html("<html><head><style type='text/css'>" + $("#cssPanel").val() +"</style></head><body>" +  $("#htmlPanel").val() + "</body></html>");
						document.getElementById("outputPanel").contentWindow.eval($("#javascriptPanel").val());
					});
			  }
		 };
		
/*	
		function check()
		{
		    var inp = document.getElementsByName('switchOutputOf');
		    for (var i = 0; i < inp.length; i++) {
		        if (inp[i].type == "radio" && inp[i].checked) {
		            function updateOutput() {
						$("iframe").contents().find("html").html("<html><head><style type='text/css'>" + $("#cssPanel").val() +"</style></head><body>" +  $("#htmlPanel").val() + "</body></html>");
						document.getElementById("outputPanel").contentWindow.eval($("#javascriptPanel").val());
					};
		        } else {
					$("#output").click(function() {
						$("iframe").contents().find("html").html("<html><head><style type='text/css'>" + $("#cssPanel").val() +"</style></head><body>" +  $("#htmlPanel").val() + "</body></html>");
						document.getElementById("outputPanel").contentWindow.eval($("#javascriptPanel").val());
					});
				};
		    }
		}
		
	
		if (document.getElementById('textareaUpdate').checked) {
			function updateOutput() {
			$("iframe").contents().find("html").html("<html><head><style type='text/css'>" + $("#cssPanel").val() +"</style></head><body>" +  $("#htmlPanel").val() + "</body></html>");
			document.getElementById("outputPanel").contentWindow.eval($("#javascriptPanel").val());
		};
	} else if (document.getElementById('textareaUpdate').checked == "false") {
		$("#output").click(function() {
			$("iframe").contents().find("html").html("<html><head><style type='text/css'>" + $("#cssPanel").val() +"</style></head><body>" +  $("#htmlPanel").val() + "</body></html>");
			document.getElementById("outputPanel").contentWindow.eval($("#javascriptPanel").val());
		});
	};
		*/
	</script>
	
</body>
</html>


