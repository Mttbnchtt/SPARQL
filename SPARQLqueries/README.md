# INVERSE RELATIONS

Some relations have an inverse. A binary relation Q is the inverse of a binary relation P if and only if, for every x and y, xPy if and only if yQx. 

When building an ontology, it may be the case that we want a relation ?predicate to have an inverse ?inversePredicate but, by mistake, we end up adding the triple { ?subject ?predicate ?object }, but we do not add the triple { ?object ?inversePredicate ?subject }. Sometimes, the ontology editor adds the inverse automatically and sometimes, if not added, it can infer it. 

However, sometimes we simply end up with a model contain a triple but not its inverse when we actually want the inverse to be in the ontology too. For example, we may imagine a case where we have added the triple { :Animal skos:narrower :Dog } but the model does not contain the triple { :Dog kos:broader :Animal } (the inverse triple) while we actually want each inverse of a triple whose predicate is skos:narrower to be in the ontology.

The queries in this folder indicates how to inquiry which triples are missing their inverses and how to add the inverses.