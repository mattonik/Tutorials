##Základná HTML šablóna

	<!-- index.html -->
	
	<!doctype html>
	<html>
	<head>
	    <meta charset="utf-8">
	    <title>Ractive</title>
	
	    <!-- CSS -->
	    <link rel="stylesheet" href="bower_components/bootstrap/dist/css/bootstrap.min.css">
	</head>
	<body>
	    <!-- navigation bar -->
	    <nav class="navbar navbar-default">
	        <div class="container-fluid">
	            <a class="navbar-brand"><i class="glyphicon glyphicon-bullhorn"></i> Ractive Events Bulletin Board</a>
	        </div>
	    </nav>
	
	    <!-- main body of our application -->
	    <div class="container" id="events">
	       
	    </div>
	    
	    <script id="template" type="text/ractive">
	         <!-- add an event form -->
	        <div class="col-sm-6">
	            <div class="panel panel-default">
	                <div class="panel-heading">
	                    <h3>Pridať udalosť</h3>
	                </div>
	                <div class="panel-body">
	
	                </div>
	
	            </div>
	        </div>
	
	        <!-- show the events -->
	        <div class="col-sm-6">
	            <div class="list-group">
	
	            </div>
	        </div>
	    </script>
	
	    <!-- JS -->
	    <script src="bower_components/ractive/ractive.min.js"></script>
	    <script src="bower_components/ractive-events-tap/dist/ractive-events-tap.js"></script>
	    <script src="app.js"></script>
	</body>
	</html>
	
##Vytvorenie Ractive inštancie

	var Events = new Ractive({
		el: '#events',
		template: '#template'
	});
	
