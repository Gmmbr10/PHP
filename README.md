
# Curso de PHP

Aqui veremos sintaxe básica de PHP e alguns comandos!!

_*Dica 1*_: SEMPRE acabe os comandos com **;**

_*Dica 2*_: Neste arquivo, será utilizado o camel case (Forma de nomeação de alguns itens)
## Variáveis, constantes e comandos de saída

_*Dica 3*_: Dê nomes sugestivos para as variáveis!!!

```php

    # Comandos de saída
    echo 'Olá Mundo!!!';
    echo "Olá Mundo!!!";
    echo("Olá Mundo!!!");
    
    print "Olá Mundo!!!";
    print("Olá Mundo!!!");

    # Criar variáveis - tipos de dados
    $nome       = "Giovanne";   # STRING
    $idade      = 16;           # INT
    $altura     = 1.65;         # FLOAT
    $estudando  = true;         # BOOLEAN
    $peso;                      # NÃO DEFINIDO

    # Mostrar informações sobre variáveis
    var_dump($nome);
    var_dump($idade);
    var_dump($altura);
    var_dump($estudando);

    # Escrever os valores das variáveis
    echo "<p>Nome: $nome<p>";
    echo "<p>Idade: $idade</p>";
    echo "<p>Altura: $altura</p>";

    # Criar constantes
    # defines("nomeDaConstante",valor que irá receber)
    defines("TAXA",0.5);
    defines("JUROS",0.1);

    # Mostrar valores das constantes
    echo "<p>Taxa " . TAXA . "% </p>";
    echo "<p>Juros " . JUROS . "% </p>";

```


## Operações e number_format

### Operadores Aritméticos

| Operador | Função |
| --- | --- |
| + | Adição |
| - | Subtração |
| * | Multiplicação |
| / | Divisão |
| % | Resto de Divisão |
| ** | Exponencial |

### Operadores Atribuição

| Operador | Função |
| --- | --- |
| = | Atribui |
| += | Atribui adicionando |
| -= | Atribui subtraindo |
| *= | Atribui multiplicando |
| /= | Atribui dividindo |
| %= | Atribui com resto de divisão |

### Operadores Atribuição

| Operador | Função |
| --- | --- |
| == | Igual |
| === | Idêntico |
| != | Não igual |
| <> | Não igual |
| !== | Não idêntico |
| > | Maior que |
| < | Menor que |
| >= | Maior ou igual |
| <= | Menor ou igual |

**<=>**

- Verifica qual é o _**maior**_
- 0 são iguais
- 1 o valor da esquerda é maior
- -1 o valor da direita é maior

### Operadores de incremento e decremento

| Operador | Função |
| --- | --- |
| ++$variavel | Pré-incremento |
| $variavel++ | Pós-incremento |
| --$variavel | pré-decremento |
| $variavel-- | Pós-decremento |

### Operadores lógicos

| Operador | Nome | Para dar TRUE em comparações |
| --- | --- | --- |
| and / && | E | Todos precisam ser verdadeiros |
| or / II | OU | Precisa de um ou mais para ser verdadeiro |
| xor | xor | Apenas um para ser verdadeiro |
| ! | Não | Precisa ser falso para ser verdadeiro |

## Função number_format()

number_format( $variavel , numeroCasasDecimais , separadorDecimais , separadorMilar )

```php

    $nota1 = 5.65;
    $nota2 = 3.94;
    $notaFinal = $nota1 + $nota2;
    $notaFinalFormatada = number_format($notaFinal, 2, ",",".");

```


## Condições

```php

    # if e else

    $idade = 16;

    if ($idade >= 18) {
        echo "<p>Voto obrigatório</p>";
    } else if ($idade >= 16) {
        echo "<p>Voto opicional</p>";
    } else {
        echo "<p>Não pode votar</p>";
    };

    # if ternário

    $maiorIdade = ($idade >= 18) ? "<p>Maior de idade</p>" : "<p>Menor de idade</p>" ;

    # Switch case

    $estudando = "S";

    switch ($estudando) {
        case 'S': case 's':
            echo "<p>Está estudando</p>";
        break;
        case 'N': case 'n':
            echo "<p>Não está estudando</p>";
        break;
        default:
            echo "<p>Selecione a opção correta!!!</p>";
        break;
    };

```
## Loop / Laço de repetição

```php

    $nomes = [
        "Edson",
        "Ramiro",
        "Matheus",
        "Henry"
    ];

    $quantidade = count($nomes);

    # for

    for ($i=0; $i < $quantidade; $i++) { 
        echo "<p>$nomes[$i]</p>";
    };

    echo "<hr>";

    # foreach
    # ( nomeDoArray as indice => nomeDeCadaElemento )
    foreach ($nomes as $key => $nome) {
        echo "<p>$nome</p>";
    };

    echo "<hr>";

    # while
    while ($a <= $quantidade) {
        echo "<p>$nomes[$a]</p>";
        $a++;
    };

    echo "<hr>";

    # do...while
    do {
        echo "<p>$nomes[$b]</p>";
        $b++;
    } while ($b <= $quantidade);

```
## Array

```php

    # Criando arrays
    $lugares    = array("Arujá","Santa Isabel","Mogi das Cruzes");
    $cursos     = ["PHP","JavaScript","MySQL"];
    $cardapio   = [
        "bebidas" => ["Coca-Cola","Pepsi","Sukita"],
        "lanches" => ["X-tudo","X-bacon","X-salada"]
    ];
    $categorias = [];
    $categorias[0] = "Programação";
    $categorias[1] = "Design";

    # var_dump e print_r
    var_dump($lugares);
    echo "<br>";
    print_r($lugares);
    echo "<hr>";

    # Funções para arrays

    # Adicionando valores no final do array
    # array_push($variavel, valores);
    array_push($lugares, "Guarulhos");

    # Adicionando valores no começo do array
    # array_unshift($variavel, valores);
    array_unshift($lugares, "São Paulo");

    # Remover valores no final do array
    # array_pop($variavel);
    array_pop($lugares);

    # Remover valores no começo do array
    # array_shift($variavel);
    array_shift($lugares);

    # Contar elementos do array
    $quantidadeLugares = count($lugares);

    # Ordenar elementos do array
    
    # Crescente
    sort($lugares);
    print_r($lugares);
    echo "<br>";

    # Decrescente
    rsort($lugares);
    print_r($lugares);
    echo "<hr>";

```
## $_POST[]

```php

    <form action="" method="post">
        <label>
            Nome: <br>
            <input type="text" name="nome"><br>
        </label>
        <label>
            Cidade que estuda: <br>
            <input type="text" name="cidadeEstuda"><br>
        </label>
        <button type="submit">Enviar</button>
    </form>

    <?php

        $name = $_POST["nome"];
        $studyCity = $_POST["cidadeEstuda"];

        if ($name != '' and $studyCity != '') {
            $res = "<p>Você é o $name e você estuda na cidade de $studyCity</p>";
        }

    ?>

    <section>
        <?php echo $res; ?>
    </section>

```
## $_GET[]

```php

    <form action="" method="get">
        <label>
            Nome: <br>
            <input type="text" name="nome"><br>
        </label>
        <label>
            Cidade que estuda: <br>
            <input type="text" name="cidadeEstuda"><br>
        </label>
        <button type="submit">Enviar</button>
    </form>

    <?php

        $name = $_GET["nome"];
        $studyCity = $_GET["cidadeEstuda"];

        if ($name != '' and $studyCity != '') {
            $res = "<p>Você é o $name e você estuda na cidade de $studyCity</p>";
        }

    ?>

    <section>
        <?php echo $res; ?>
    </section>

```
