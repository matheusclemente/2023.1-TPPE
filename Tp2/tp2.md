# Atributos de código

## Características de um bom projeto de software

Um bom projeto apresenta um conjunto específico de características, e a ausência dessas características é indicativo de um projeto ruim. Segundo Pete Goodliffe, tais características são:

### Simplicidade

Um projeto simples é fácil de entender, coerente e consistente, escrito com o menor código possível, e não menor que isso. O projeto deve cumprir exatamente o que é necessário, usando o mínimo possível, sem quaisquer complexidades desnecessárias.

Sendo a característica mais importante de um código bem projetado, é compreensível que diversos "maus cheiros" de código interfiram na simplicidade do código. De fato, cada um dos maus cheiros descritos por Fowler interferem, em maior ou menor intensidade, com a simplicidade de um projeto. Igualmente, qualquer operação de refatoração, contanto que corretamente aplicada, contribuirá para essa característica.

### Elegância

Essa característica, diretamente associada à simplicidade, diz respeito à estética estrutural do código. Engloba pontos como um adequado controle de fluxo através do sistema, completude entre as partes, resultando em um projeto estruturalmente "belo".

Pode-se estabelecer uma relação direta entre essa caracterísca e o mau cheiro de codigo da "cirurgia com rifle". Esse atributo descreve um código onde uma mudança individual acarreta em pequenas mudanças em diversas classes, o que vai em direta contradição com o que Goodliffe estabelece como característica de elegância, em que "uma única, simples mudança em um lugar não leva a modificações no código em vários outros lugares". Uma oportunidade de refatoração para esse caso específico seria _mover método_ ou _mover campo_ de forma a agrupar as mudanças em uma única classe, ou _incorporar classe_ para agrupar um grupo de comportamentos em uma mesma estrutura.

Quanto ao fluxo do sistema, é possível associar tal característica ao mau cheiro de "aglomerados de dados", que pode ser lidado através da refatoração de _extrair classe_ para transformar aglomerados em objetos, e _introduzir objeto parâmetro_ ou _preservar objeto inteiro_ para simplificar-los.

### Modularidade

Projetos de código são dividos em diversos "módulos", ou "componentes", como classes, objetos, pacotes, dentre outros. Uma boa modularidade atenta-se à coesão e acoplamento do código. Coesão diz respeito a funcionalidades relacionadas entre si serem agrupadas em um mesmo módulo, enquanto acoplamento se refere à interdependência entre módulos diferentes. Um bom projeto deve apresentar forte coesão e baixo acoplamento.

Classe grande, inveja de recursos, homem do meio e classe preguiçosa são apenas alguns exemplos de mau cheiros de código que afetam a modularidade de um projeto. De forma geral, oportunidades de refatoração que interajam intensamente com classes (módulos) e suas interações irão, consequentemente, impactar a coesão e acoplamento do código, melhorando assim a modularidade do projeto. Para os exemplos de mau cheiros citados, podemos aplicar refatorações como _extrair método/mover método_, _mover atributo_ ou _extrair classe_.

### Boas interfaces

### Extensibilidade

### Ausência de duplicidades

### Portabilidade

### Idiomático

### Boa documentação
