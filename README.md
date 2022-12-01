# POC:
Demonstration of using anypoint queues, so, I created an example where a word passed in query parameter in method (/api/push/{word}) (or injected in the MQ) is redirected to one of the 3 queues created:
 - Fruit: the word is a fruit.
 - Color: the word is a color.
 - Undefined: None of the above options
Some endpoints were also created to remove/pop the word from thes queues.

# Anypoint MQ:
(queue/fifo) Input -> (exchange) exchange-route -> (queues) output-[colors/fruits/undefined]

# Push:
http://colors-fruits-api.br-s1.cloudhub.io/api/push/{word}

# Pop:
http://colors-fruits-api.br-s1.cloudhub.io/api/pop/fruits
http://colors-fruits-api.br-s1.cloudhub.io/api/pop/colors
http://colors-fruits-api.br-s1.cloudhub.io/api/pop/undefined

# Authentication:

## (Free) Colors Fruit API / Limit 1 request per minute
client_id: bdd43aec112a4ce1a3d8cb48a8fcd6c8
client_secret: b3983C09Bf474056811Dc94C405A3b37
Authorization: Basic Y29nbml6YW50OmMwZ24xejRudA==

## (Silver) Colors Fruit API / Limit 1 request per 30 seconds
client_id: 0709fa66c1804db4a3afaba81a22c171
client_secret: c24699c7166F4f1b813a1cbFfe2DfCb6
Authorization: Basic Y29nbml6YW50OmMwZ24xejRudA==

## (Gold) Colors Fruit API / Limit 1 request per second
client_id: 35a6504364a647caa509ecdc878540da
client_secret: 7a047c6e97534E589e16a46791701F6b
Authorization: Basic Y29nbml6YW50OmMwZ24xejRudA==
