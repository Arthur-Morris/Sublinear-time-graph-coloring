# Sublinear-time-graph-coloring
this is the repo for my re implementation of the sub-linear tile graph coloring algorithm. When i wrote the original  implementation i get wrapped up in following the paper exactly so i included a bunch of stuff that wasn't actually needed.

The algorithm is even simper than i thought. It is based on the property of deg + 1 colourings that any correct partial coloring can be extended into a full coloring. Graph colouring is fundamentally the process of splitting a graph into a number of independent sub-graphs. 

With that in mind the algorithm works like this:


	while there are uncoloured vertexes:

		assign a random colour to each uncoloured vertex
	
		add each uncoloured vertex to their respective conflict set
	
		search each conflict set for edges
	
		remove one end of each found edge

This should run log n times

This is slightly different from the original algorithm which works like this:

	for each vertex:
	
		generate log n colours and add them to the conflict sets
		
	search each conflict set for edges
	
	remove one end of each found edge
	
	when i wrote the original paper i added a step to patch holes at the end

By spiting the algorithm up into rounds i am hoping to improve performance by avoiding sampling colours that are not needed, keeping the conflict sets small. this will also avoid the need for hole patching.

i will also test if pair quires significantly improve performance.

Citations:Sublinear Algorithms for (Δ+1) Vertex Coloring.  By: Sepehr Assadi, Yu Chen, Sanjeev Khanna. Published 2018. available at: arxiv.org/abs/1807.08886
