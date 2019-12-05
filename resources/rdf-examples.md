# 194.083 Hackathon – Semantic Web

## RDF Examples

### Local Blazegraph

### 1) TTL Input

`http://ip:port/blazegraph/#update`

Type: RDF Data Format: Turtle

```js
@prefix p: <http://tempuri.com/people/> .
@prefix r: <http://example.com/relationships/> .

p:Alice r:like p:Bob;
    r:givenName "Alice";
    r:familyName "Brown";
    r:age 25 .
p:Bob r:like p:Alice, p:Charlie;
    r:givenName "Bob";
    r:familyName "Carter";
    r:age 31 .
p:Charlie r:like p:Alice;
    r:givenName "Charles";
    r:familyName "David";
    r:age 27 .
```

### 2) SPARQL Query

`http://ip:port/blazegraph/#query`

```js


PREFIX p: <http://tempuri.com/people/>
PREFIX r: <http://example.com/relationships/>

SELECT ?person
WHERE {
    _:liker r:like ?person;
           r:givenName "Bob".
    ?person r:age 25 .
}
```

### DBpedia

### 3) SPARQL

```js
PREFIX dbo: <http://dbpedia.org/ontology/>
PREFIX dbr: <http://dbpedia.org/resource/>

SELECT DISTINCT ?person
WHERE {
    ?person dbo:birthPlace dbr:Vienna .
}
```

### 4) SPARQL: Multiple Statements

```js
PREFIX dbo: <http://dbpedia.org/ontology/>
PREFIX dbr: <http://dbpedia.org/resource/>

SELECT DISTINCT ?person
WHERE {
    ?person dbo:birthPlace dbr:Vienna .
    ?person dbo:deathPlace dbr:Vienna .
}
```

### 4) SPARQL: Multiple Statements

```js
PREFIX dbo: <http://dbpedia.org/ontology/>
PREFIX dbr: <http://dbpedia.org/resource/>

SELECT DISTINCT ?person
WHERE {
    ?person dbo:birthPlace dbr:Vienna .
    ?person dbo:deathPlace dbr:Vienna .
}
```

#### 5) SPARQL: Projection

```js
PREFIX dbo: <http://dbpedia.org/ontology/>
PREFIX dbr: <http://dbpedia.org/resource/>
PREFIX foaf: <http://xmlns.com/foaf/0.1/>

SELECT DISTINCT ?name ?person
WHERE {
    ?person dbo:birthPlace dbr:Vienna .
    ?person dbo:deathPlace dbr:Vienna .
    ?person foaf:name ?name .
}
```

### 6) SPARQL: Projection

```js
PREFIX dbo: <http://dbpedia.org/ontology/>
PREFIX dbr: <http://dbpedia.org/resource/>
PREFIX foaf: <http://xmlns.com/foaf/0.1/>

SELECT distinct ?name ?birth ?p
WHERE {
    ?p dbo:birthPlace dbr:Vienna .
    ?p dbo:deathPlace dbr:Vienna .
    ?p foaf:name ?name .
    ?p dbo:birthDate ?birth
}
```

### 7) SPARQL: Order

```js
PREFIX dbo: <http://dbpedia.org/ontology/>
PREFIX dbr: <http://dbpedia.org/resource/>
PREFIX foaf: <http://xmlns.com/foaf/0.1/>

SELECT distinct ?name ?birth ?p
WHERE {
    ?p dbo:birthPlace dbr:Vienna .
    ?p dbo:deathPlace dbr:Vienna .
    ?p foaf:name ?name .
    ?p dbo:birthDate ?birth
}  ORDER BY ?name
```

### 8) SPARQL: Filter

```js
PREFIX dbo: <http://dbpedia.org/ontology/>
PREFIX dbr: <http://dbpedia.org/resource/>
PREFIX foaf: <http://xmlns.com/foaf/0.1/>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>

SELECT distinct ?name ?birth ?p
WHERE {
    ?p dbo:birthPlace dbr:Vienna .
    ?p foaf:name ?name .
    ?p dbo:birthDate ?birth .
    FILTER (?birth < “2000-01-01”^^xsd:date) .
}  ORDER BY ?name
```

### 9) SPARQL: Count

```js
PREFIX dbo: <http://dbpedia.org/ontology/>
PREFIX dbr: <http://dbpedia.org/resource/>
PREFIX foaf: <http://xmlns.com/foaf/0.1/>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>

SELECT (COUNT(?p) AS ?personen)
WHERE {
    ?p dbo:birthPlace dbr:Vienna .
    ?p foaf:name ?name .
    ?p dbo:birthDate ?birth .
    FILTER (?birth < "2000-01-01"^^xsd:date) .
}
```

### 10) Hands On

Amount of People who were born in Berlin before 1900

```js
PREFIX dbo: <http://dbpedia.org/ontology/>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX foaf: <http://xmlns.com/foaf/0.1/>
PREFIX : <http://dbpedia.org/resource/>

SELECT DISTINCT (COUNT (?person) AS ?amount) WHERE {
	?person dbo:birthPlace :Berlin .
	?person dbo:birthDate ?birth .
	?person foaf:name ?name .
	?person dbo:deathDate ?death .
	FILTER (?birth < "1900-01-01"^^xsd:date) .
}
```

### 11) Hands On

```js
SELECT (COUNT(?s) AS ?triples) WHERE { ?s ?p ?o }
```
