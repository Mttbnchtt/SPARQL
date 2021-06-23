# RELATIONS
This folder contains queries to check whether the relations in a model are as desired.

## INVERSE RELATIONS

Some relations have an inverse. A binary relation Q is the inverse of a binary relation P if and only if, for every x and y, xPy if and only if yQx.

When building an ontology, it may be the case that we want a relation ?predicate to have an inverse ?inversePredicate but, by mistake, we end up adding the triple { ?subject ?predicate ?object }, but we do not add the triple { ?object ?inversePredicate ?subject }. Sometimes, the ontology editor adds the inverse automatically and sometimes, if not added, it can infer it.

However, sometimes we simply end up with a model contain a triple but not its inverse when we actually want the inverse to be in the ontology too. For example, we may imagine a case where we have added the triple { :Animal skos:narrower :Dog } but the model does not contain the triple { :Dog skos:broader :Animal } (the inverse triple) while we actually want each inverse of a triple whose predicate is skos:narrower to be in the ontology.

### inverseRelations_bySubjectType_SELECT.rq
Given a finite list of types, this query selects all the triples { ?s ?p ?o } where $?s is of a desired type and the inverse triple does not exist. The query is designed for non-symmetric relations.

### inverseRelations_byRelationType_SELECT.rq
Given a class of relations, this query selects all the triples { ?s ?p ?o } where ?p belongs to that class and the inverse triple does not exist. The query is designed for non-symmetric relations.

### inverseRelations_INSERT.rq
Given the conditions of the query inverseRelations_bySubjectType_SELECT.rq, this query insert all the missing inverse relations. The query is designed for non-symmetric relations.
