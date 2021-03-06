# Alap szintaxisok

## Függvények

### Deklaráció
```kotlin
fun sum(a: Int, b: Int): Int {
    return a+b
}
```
Ezt lehetünk akár nagyon karakter fukárok is `fun sum(a: Int, b: Int) = a + b`.
Az előbb is láthattuk és ebben a példában is, hogy nem szükséges a `;` de az se baj ha kirakjuk ;)

Ha nincs visszatérési értéke a függvénynek, azaz `void` akkor vagy simán elhagyjuk a visszatérési értéket jelző kulcsszót, vagy `Unit` kulcsszót használunk.

```kotlin
fun printSum(a: Int, b: Int): Unit {
    println("sum of $a and $b is ${a + b}")
}
```

#### Alapértelmezet érték a paraméternek
```kotlin
fun foo(bar: Int = 0, baz = Int) { /* ... */ }

/* használat */
foo(baz = 1)
```

##### Lambda
```kotlin
fun foo(bar: Int 0, baz = 1, qux: () -> Unit) {/* ... */}

/* használat */
foo(1) {/* ... */} //bar = 1, baz = 1, qux = null
foo  {} /* ...  */} // bar = 0, baz = 1, qux = null
```

#### Változók száma argumentumként (Varargs)
 ```kotlin
// fordító: "Ez egy függvénydefiníció, ami T típust generikusan haszálja, a függvén neve 'arList'. Paraméterként kap egy argomentum tömbött aminek minden eleme T típusú. Visszatérési értéke egy T típusú lista
fun <T> asList(vararg ts: T): List<T> { 
    val result = ArrayList<T>()
    //ts egy tömb. t változó felveszi ts tömbb minden elemét, "egyessével", és hozzáadja result tömbhöz.
    for (t in ts) //ez valójában egy foreach
        result.add(t)
    return result
}
 ```


