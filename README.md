<!DOCTYPE html>
<html>
	<head>
		<title>Inifinity(JS)</title>
		<META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=UTF-8"> 
		
	</head>
	<body>
		<p id="demo"></p>
		<script>
			function takesTwoParams(){
				//arguments is an array-like variable that is automatically created
				//arguments.length works greats
				alert("you gave me " + arguments.length + "arguments");
				for(i = 0; i < arguments.length;i++){
					console.log("parameter " + i + " = " + arguments[i]);
				}
				// Array.from(arguments) method to convert arguments to a real Array; 
				var arr = Array.from(arguments);
				console.log(arr[0]);
			}
			<!-- takesTwoParams("one","two","three"); -->
			function myConcat(seperator){
				var args = Array.prototype.slice.call(arguments,1);
				return args.join(seperator);
			}
			<!-- console.log(myConcat(', ','red','orange','blue')); -->
			<!-- console.log(myConcat('; ','elephant','giraffe','lion','cheetah')); -->
			<!-- console.log(myConcat('. ','sage','basil','oregano','pepper','parsley')); -->
			
			function list(type){
				var result = '<' + type + 'l><li>';
				var args = Array.prototype.slice.call(arguments,1);
				result += args.join('</li><li>');
				result += '</li></' + type + 'l>';
				
				return result;
			}
			
			<!-- var listHTML = list('u','One','Two','Three'); -->
			<!-- document.getElementById("demo").innerHTML = listHTML; -->
			
			function func(a){
				arguments[0] = 99; //updating arguments[0] also updates a.
				console.log(a);
			}
			
			function func123(a = 55){
				a = 99;
				console.log(arguments[0]);
			}
		</script>
		
	</body>
</html>
