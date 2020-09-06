# Sublinear-time-graph-coloring
this is the repo for my re implementation of the sub-linear tile graph coloring algorithm. When i wrote the original  implementation i get wrapped up in following the paper exactly so i included a bunch of stuff that wasn't actually needed.

The algorithm is even simper than i thought. It is based on the property of deg + 1 colourings that any correct partial coloring can be extended into a full coloring. Graph colouring is fundamentally the process of splitting a graph into a number of independent sub-graphs. 

With that in mind the algorithim works like this:

while there are uncoloured vertexes:

	assign a random colour to each uncoloured vertex
	
	add each uncoloured vertex to their respective colour list
	
	search each colour list for edges
	
	remove one end each found edge

this should run log n times
