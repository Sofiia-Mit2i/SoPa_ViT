
1. Split Image into Patches
	- whole image too big for Attention computation
	- might overlap (stride parameter)
2. vectorization
	- d1 x d2 x d3 3D Image becomes d1 d2 d3 x 1 vector
3. Dense into smaller vectors
	- z1 = W * v1 + b
	- z2 = W * v2 + b
	- ...
4. Add positional encodings (vector!) to those dense vectors
	- network itself has no idea about position (puzzle piece)
	- similiar for patches close to eachother (neighbors, same row/column)
--> zi contains info about content AND position of the i-th patch
5. add embedded **CLS** Token 
	- will contain classification info in the end (z0)
6. feed into  **Transformer Encoder Network** (multi-head self attention layer, Dense, Attention, ...)
--> output c0 for classification
7. feed c0 into softmax classifier
	- outputs probabilities that the input belongs to the given classes



[[Sources]]:
https://www.youtube.com/watch?v=qU7wO02urYU (17.3.25)
https://www.youtube.com/watch?v=HZ4j_U3FC94 (17.3.25)

 