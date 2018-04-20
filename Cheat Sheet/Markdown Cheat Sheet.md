<center>

# - Markdown -
### For .md file
#### Markdown pozwala na proste tworzenie notatek za pomocą znaczników własnych jak i html'a.
</center>

### Cheet Sheet:
>#### Zacznijmy od tego, że nie wszystko działa:
>>:warning: Style `css` działają w boostnote, ale nie na githubie.
>>
>>:warning:  Nie zawsze `HTML` działa z plikiem `README.md`, by zadziałało trzeba wkleić do github wiki zawartość roboczą, zapisać i przekopiować z wiki do `README.md`
>>
>> Dlaczego? Nie wiem. Ale działa :+1:
>***
>#### Emoji
>>      :point_right::ok_hand::rage:
>> Wyświetli takie oto emoji: :point_right::ok_hand::rage:
>> 
>> [Lista dostępnych emoji](https://gist.github.com/rxaviers/7360908)
>***
>#### Nagłówki:
>>      ### Tekst
>> Im więcej `#` tym mniejszy nagłówek, czyli `# Tekst` to to samo co `<h1>Tekst</h1>`.
>***
>#### Linie kodu
>>      `<some code>`
>> Używając `'`, to ten znak tam gdzie ` ~ `, możemy wypisywać linie kodu i będzie wyglądało to tak: `<some code>`
> ***
>#### Wyświetlenie obrazu
>>      ![something](http://link/do/mojego/zdjecia.jpg)
>> Takim sposobem sprawimy, że obraz pojawi się w naszym dokumencie.
> ***
>#### Link odsyłający
>>      [Nazwa linku](http://link/do/mojego/zdjecia.jpg)
>> Usuwając z początku `!` sprawiamy, że pojami się link pod taką nazwą jaką wpiszemy pomiędzy `[ ... ]`
> ***
>#### Wyśrodkowanie i ogólnie align
>>      <div align="center">
>>      
>>      ## My Title with Markdown
>>      </div>
>> Taki zapis pozwoli na przesunięcie tekstu w div'ie na środek. Ewentualnie pozycjonować do prawej `align="right"`, do lewej `align="left"` lub wyjustować `align="justify"`.
>> 
>> :warning: Uwaga: między div'em, a znacznikiem markdown musi być linia przerwy inaczej markdown nie zostanie poprawnie zinterpretowany.
>***
>#### Check box
>>      - [ ] Odznaczone
>>      - [x] Zaznaczone
>> - [ ] Odznaczone
>> - [x] Zaznaczone
>> 
>> Jak widać w ten sposób tworzymy checkboxy i możemy np. listę To Do zrobić.
>***
>#### Lista nienumeryczna
>>      * punkt 1
>>      * punkt 2
>>        * podpunkt 2.1
>>          * podpunkt 2.1.1
>>      * punkt 3
>> Odstępy przed `*` tworzone co dwie spacje ustalają hierarchię podpunktów, czyli zapis powyżej da efetk:
>> * punkt 1
>> * punkt 2
>>   * podpunkt 2.1
>>     * podpunkt 2.1.1
>> * punkt 3
>***
>#### Lista numerowana
>>
>>      1. Punkt 1
>>      2. Punkt 2
>>         1. Podpunkt
>>             1. Pod Podpunkt
>>          1. Podpunkt
>>          1. Podpunkt
>>      3. Punkt 3
>>      
>> Podobnie jak poprzednio robimy wcięcia dla hierarchii, ale dodatkowo numerujemy. Elementy będące podpunktami numerujemy od `1` jak nową listę.
>> 
>> 1. Punkt 1
>> 2. Punkt 2
>>    1. Podpunkt
>>       1. Pod Podpunkt
>>    2. Podpunkt
>>    3. Podpunkt
>> 3. Punkt 3
>> 
>***
>#### Stylowanie tekstu
>>      __some text__
>>      _some text_
>>      *__some text__*
>>      ~~some text~~
>>      ~~*__sometext__*~~
>> Podwójne znaczniki do stylizowania fragmentów tekstu, można je ze sobą łączyć tak jak to widać poniżej:
>> 
>> __some text__
>>
>>  _some text_
>> 
>> *__some text__*
>> 
>> ~~some text~~
>> 
>> ~~*__sometext__*~~
>>
>>:warning: `*` daje ten sam efekt co `_`.
>***
>#### Bloki kodu `~~~`
>>      >~~~ javascript
>>      >var x = 0;
>>      >print(x);
>>      >~~~
>> Powyższy zapis pozwala użyć tyldy `~~~` by stworzyć blok kodu pozwalający na formatowanie przy pomocy znaczników md np. wcięcie z linią przez `>`. Po podaniu nazwy języka programowania formatują się dodatkowo kolory.
>> >~~~ javascript
>> >var x = 0;
>> >print(x);
>> >~~~
***
#### Alternatywny blok kodu ` ``` `
    ``` javascript
    var x = 0;
    print(x);
    ```
:warning: Robi to co wyżej z jednym ale... wyłącza część formatowania md, przez co później powstają bugi. osobiście polecam `~~~`

``` javascript
var x = 0;
print(x);
```

>***
>> #### Tabela
>>      | Kolumna 1 | Kolumna 2 | Kolumna 3 |
>>      | - | - | - |
>>      | Aleks | Serhii | Mikołaj |
>>      | Jimm | Jimm | Jack |
>>      | 1 | 2 | 3 |
>> Rysujemy tabelę w ascii i tyle.
>> 
>> | Kolumna 1 | Kolumna 2 | Kolumna 3 |
>> | - | - | - |
>> | Aleks | Serhii | Mikołaj |
>> | Jimm | Jimm | Jack |
>> | 1 | 2 | 3 |
>> 
>***
>#### Linia jak `<hr/>`
>>      ***
>> No i w sumie tyle, a ewentualnie również trzy razy `_`. 
>>***
>***
## THE END?
