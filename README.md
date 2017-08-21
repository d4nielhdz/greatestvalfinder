# Adding Visual and Interactive Features to Phylogenetic Trees
  This tutorial was designed for Ubuntu users and it assumes you already have a phylogenetic tree stored in the Newick format.
## Saving a Tree as XML/PhyloXML (in case it is not in any of these formats)  

In order to make your tree a little more appealing to the eye, it must be in an XML format. To change its format from Newick,     go to the following website:
https://phyd3.bits.vib.be/view.php?id=71d752e8b21452c2dcd8267f94a58bb7.xml&f=xml
  		  Once you have opened your tree, choose the option: "Download as 
### Download the necessary libraries
      The following libraries will be used to make your tree look better:
      Raphael (js library): https://raw.githubusercontent.com/DmitryBaranovskiy/raphael/master/raphael.min.js
      jsPhyloSVG: https://github.com/guyleonard/jsPhyloSVG/blob/master/jsphylosvg-min.js
      jQuery 1.4.2: http://code.jquery.com/jquery-1.4.2.min.js
         Create a text file with the following code:
           
	   `<html>
    <head>
    	<script type="text/javascript" src="/js/jquery/jquery-1.4.2.min.js" ></script> 
	    <script type="text/javascript" src="/js/raphael/raphael-min.js" ></script> 
      <   script type="text/javascript" src="/js/jsphylosvg-min.js"></script> 
	
    	<script type="text/javascript">
	      $(document).ready(function(){
		$.get("/trees/2-coffee.xml", function(data) {
			var dataObject = {
				xml: data,
				fileSource: true
			};		
			phylocanvas = new Smits.PhyloCanvas(
				dataObject,
				'svgCanvas', 
				800, 800,
				'circular'
			);
		});
	});
	</script>

</head>
<body>
	  <div id="svgCanvas"> </div>
</body>
</html>`
