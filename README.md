# Button-Telefonica-FIWARE
<html>
    <head>
    	<style>
    		input[type=checkbox] {
                visibility: hidden;
            }
			.container{
                
            }
            /* ROUNDED ONE */
            .redLed {
                width: 68px;
                height: 68px;
                background: #fcfff4;
                background: -webkit-linear-gradient(top, #fcfff4 0%, #dfe5d7 40%, #b3bead 100%);
                background: -moz-linear-gradient(top, #fcfff4 0%, #dfe5d7 40%, #b3bead 100%);
                background: -o-linear-gradient(top, #fcfff4 0%, #dfe5d7 40%, #b3bead 100%);
                background: -ms-linear-gradient(top, #fcfff4 0%, #dfe5d7 40%, #b3bead 100%);
                background: linear-gradient(top, #fcfff4 0%, #dfe5d7 40%, #b3bead 100%); 
                filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#fcfff4', endColorstr='#b3bead',GradientType=0 );
                margin: 20px auto;
                -webkit-border-radius: 50px;
                -moz-border-radius: 50px;
                border-radius: 50px;
                
                position: relative;
            }
            .redLed label {
                cursor: pointer;
                position: absolute;
                width: 60px;
                height: 60px;
                -webkit-border-radius: 50px;
                -moz-border-radius: 50px;
                border-radius: 50px;
                left: 4px;
                top: 4px;
                
                background: -webkit-linear-gradient(top, #222 0%, #45484d 100%);
                background: -moz-linear-gradient(top, #222 0%, #45484d 100%);
                background: -o-linear-gradient(top, #222 0%, #45484d 100%);
                background: -ms-linear-gradient(top, #222 0%, #45484d 100%);
                background: linear-gradient(top, #222 0%, #45484d 100%);
                filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#222', endColorstr='#45484d',GradientType=0 );
            }
            .redLed label:after {
                -ms-filter: "progid:DXImageTransform.Microsoft.Alpha(Opacity=0)";
                filter: alpha(opacity=0);
                opacity: 0;
                content: '';
                position: absolute;
                width: 56px;
                height: 56px;
                background: #00bf00;
                background: -webkit-linear-gradient(top, #bf0000 0%, #940000 100%);
                background: -moz-linear-gradient(top, #bf0000 0%, #940000 100%);
                background: -o-linear-gradient(top, #bf0000 0%, #940000 100%);
                background: -ms-linear-gradient(top, #bf0000 0%, #940000 100%);
                background: linear-gradient(top, #bf0000 0%, #940000 100%);
                -webkit-border-radius: 50px;
                -moz-border-radius: 50px;
                border-radius: 50px;
                top: 2px;
                left: 2px;
                
            }
            .redLed label:hover::after {
                -ms-filter: "progid:DXImageTransform.Microsoft.Alpha(Opacity=30)";
                filter: alpha(opacity=30);
                opacity: 0.3;
            }
            .redLed input[type=checkbox]:checked + label:after {
                -ms-filter: "progid:DXImageTransform.Microsoft.Alpha(Opacity=100)";
                filter: alpha(opacity=100);
                opacity: 1;
            }
    	</style>

    	<script>
			var x=false;
			Boolean(x);

        function buttonScript(){
            
            if (x==true){
                $.ajax({
                type: 'POST',
                url: 'https://thingproxy.freeboard.io/fetch/http://hackathon.ttcloud.net:10026/v1/contextEntities/ZMHBSU/attributes/color',
                crossDomain: true,
                data: '{"value":"0,0,0"}',
                dataType: 'json',
                headers: {'content-type': 'application/json',
                'accept': 'application/json',
                'fiware-service': 'todosincluidos',
                'fiware-servicepath': '/iot'
                }                    
                }
                );
            }
            
            if (x==false){
                $.ajax({
                type: 'POST',
                url: 'https://thingproxy.freeboard.io/fetch/http://hackathon.ttcloud.net:10026/v1/contextEntities/ZMHBSU/attributes/color',
                crossDomain: true,
                data: '{"value":"0,1,0"}',
                dataType: 'json',
                headers: {'content-type': 'application/json',
                'accept': 'application/json',
                'fiware-service': 'todosincluidos',
                'fiware-servicepath': '/iot'
            	}                    
            	}
        		);
            }
            
            x=!x;                
            	
        }
            
        </script>
	</head>

	<body>
            <div align="center" vertical-align="middle" style="transform: translateY(50%)">
     			<div class="redLed">
                	<input type="checkbox" value="None" id="redled" name="check" onclick="buttonScript()">
                    <label for="redled"></label>
				</div>
			</div>
	</body>
