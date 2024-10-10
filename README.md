Dataset compression plays a crucial role in modern data management and analytics. As the volume of data generated and collected continues to skyrocket, the need for efficient storage and processing becomes more pressing. While reducing the size of the dataset, it is essential to ensure that the compression is lossless i.e. the original dataset can be retrieved efficiently from the compressed dataset without any loss in information.

The following dataset- 
T1 - A, B, C, D, E
T2 - A, B, C, D, F
T3 - A, B, C, D, E, G
T4 - A, B, C, D, E, F, G
Here T1, T2, T3, T4 are the transaction IDs and A, B, C, D, E, F, G are items.

we create the following mapping to re-label some itemsets - 
{
	X: {A, B, C, D},
	Y: {E, G}
}
The new dataset becomes - 
T1 - X, E
 T2 - X, F 
T3 - X, Y 
T4 - X, Y, F

The storage cost is taken as the total number of items across all transactions in the dataset and the number of keys and items in the decoder mapping.
For example – In this case, the size of the original dataset is 23 as there are 23 items we need to store.
The size of the mapping table is 8 and the size of the compressed dataset is 9.
Hence we are able to reduce the storage size from 23 (size of original dataset) to 17 (size of mapping table + size of compressed dataset).
This corresponds to roughly 26% compression.

