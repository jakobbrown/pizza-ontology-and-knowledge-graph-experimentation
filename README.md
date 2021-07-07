# pizza-ontology-and-knowledge-graph-experimentation
In order to gain some grasp in to the capabilities of semantic web technologies and knowledge graphs, I first created a simple pizza ontology in protege, which was then transferred over to python. Using rdflib,  owlrl, and owlready2 libraries, various operations were performed such as conversion of a tabular dataset to a knowledge graph, alignment of said knowledge graph with the famous pizza ontology (https://protege.stanford.edu/ontologies/pizza/pizza.owl) , sparql querying, deductive reasoning using owlrl semantics, and experimenting with creating embeddings from the ontology using Owl2Vec (https://github.com/KRR-Oxford/OWL2Vec-Star). Using these vectorisations of the knowledge graph, an initial k-means clustering algorithm was applied to the entities of the ontology to gauge lexical and semantic similarities, which were then visualised and evaluated. 

In the code zip file, you will find all you need to run all the code used in this piece of coursework. 

Please first ensure that all the packages in ‘requirements.txt’ are installed.

To run the main notebook, which includes:
-	Data pre-processing
-	Programming the tabular data to RDF triples
-	SPARQL and reasoning task
-	Ontology alignment task

You need only to open the notebook entitled “main_notebook.ipynb”, ensuring that it is in the same directory/file as the other files in the zip file, and run all cells. This will reproduce and thus overwrite some of the files provided as part of the submission, though their contents will not be changed. Run time is prolonged by the dbpedia lookup stage by approx. 45 minutes. OWLRL reasoning also takes approx. 5 minutes each time. Should you want to avoid these steps, new rdflib graphs are initialised and relevant Knolwedge graphs are parsed to it at different stages in the process, so avoiding the long wait is easy. Just run the import cell at the top of the notebook, and make sure you run any given section from the start, where there should hopefully be an initialization of the graph needed for the task at hand.

To run the embedding task, there are two different notebooks. Enter the file ‘embedding section’ to see the ‘embeddings_notebook.ipynb’. This was the notebook just to create the embeddings. Results are not reproducible simply by running the script, as between each of the 3 main cells which created the embeddings, the file ‘default.cfg’ was altered and saved. The changes made from the default setting was documented in the notebook above each cell, should you want to alter it in the same way and reproduce the embeddings for each. The embeddings for each of the 3 configurations are saved in binary textual format in the file ‘output_embedding’. Their numbering corresponds to the order in which they were made in the ‘embeddings_notebook.ipynb’.

Finally, to reproduce the final part of the coursework, in calculating similarity scores between 5 pairs of word vectors, and clustering the whole group of ontology word vectors, enter the ‘output_embedding’ file. In there, there will be a notebook entitled ‘similarity and clustering notebook.ipynb’. All that needs to be done Is to run all of the cells in the notebook to reproduce the content.

In terms of the other files, they are either there to be used in the coding, or to be viewed as part of the submission. The files that are asked for as part of the submission are named as follows:
-	Ontology in turtle of RDF/XML format – ‘base_ontology.ttl’
-	RDf data in turtle format – ‘RDF_data.ttl’
-	Extended RDF data after reasoning in turtle format – ‘ontology_with_data_post_reasoning.ttl’
-	Csv file created in SPARQL subtask 2 – ‘SPARQL_task2_query_results.csv’
-	Ontology alignment in turtle format – ‘ontology_alignments.ttl’ & ‘aligned_ontology_with_data.ttl’
-	Ontology alignments in both binary and textual format – ‘embedding section’ -> ‘output_embedding’ -> ‘created_ontology.embeddings*’

Other files that may be of interest:
-	File containing full query results from Subtask OA.2.b i.e. all pizzas of type ‘pizza:MeatyPizza’ – ‘OA_meatypizza_query_results.csv’

Note: any ‘ttl’ file that contains a form of ontology post reasoning, and therefore has ‘post_reasoning’ at the end of its name, could not be opened in protégé. Un-reasoned versions must be loaded in to protégé and then reasoning can be performed with Hermit there.
![image](https://user-images.githubusercontent.com/71882999/124762643-0aa36400-df2b-11eb-8ebe-6b9c6194b2f9.png)
