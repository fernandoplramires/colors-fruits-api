# POC:
Demonstration of using anypoint queues, so, I created an example where a word passed in query parameter in method (/api/push/{word}) (or injected in the MQ) is redirected to one of the 3 queues created:
 - Fruit: the word is a fruit.
 - Color: the word is a color.
 - Undefined: None of the above options
Some endpoints were also created to remove/pop the word from thes queues.

# Anypoint MQ:
(queue/fifo) Input -> (exchange) exchange-route -> (queues) output-[colors/fruits/undefined]

# Push:
https://colors-fruits-api-usnewc.rajrd4-2.usa-e1.cloudhub.io/api/push/{word}

# Pop:
https://colors-fruits-api-usnewc.rajrd4-2.usa-e1.cloudhub.io/api/pop/fruits
https://colors-fruits-api-usnewc.rajrd4-2.usa-e1.cloudhub.io/api/pop/colors
https://colors-fruits-api-usnewc.rajrd4-2.usa-e1.cloudhub.io/api/pop/undefined