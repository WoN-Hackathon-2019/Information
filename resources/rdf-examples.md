# 194.083 Hackathon – Semantic Web

## RDF Examples

### TTL Input

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
