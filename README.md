# pizza-ontology-and-knowledge-graph-experimentation
In order to gain some grasp in to the capabilities of semantic web technologies and knowledge graphs, I first created a simple pizza ontology in protege, which was then transferred over to python. Using rdflib,  owlrl, and owlready2 libraries, various operations were performed such as conversion of a tabular dataset to a knowledge graph, alignment of said knowledge graph with the famous pizza ontology (https://protege.stanford.edu/ontologies/pizza/pizza.owl) , sparql querying, deductive reasoning using owlrl semantics, and experimenting with creating embeddings from the ontology using Owl2Vec (https://github.com/KRR-Oxford/OWL2Vec-Star). Using these vectorisations of the knowledge graph, an initial k-means clustering algorithm was applied to the entities of the ontology to gauge lexical and semantic similarities, which were then visualised and evaluated. 