<div align="center">

# - Docker -
### For Windows 10 in PowerShell

<div align="justify">

>### Wyświetlenie obrazów
>>      docker images
>>      docker image ls
>> Dzięki tym poleceniom można sprawdzić jakie obrazy kontenerów są dostępne na naszej maszynie.
>
>### Uruchomienie kontenera
>>      docker run -it -rm <nazwa kontenera>:<wersja>
>> Powyższy zapis umożliwi odpalenie kontenera. Wskazania `-it` oznaczają to samo co `-i -t` czyli `interactive terminal`, bez tego kontener by się uruchomił ale nie otworzył nam terminalu. Następnie pisząc `--rm` ustawiamy usunięcie kontenera po wyjściu z teminala, inaczej nawet po zamknięciu, kontener by działał w tle lub został wstrzymany. A poniżej przykład:
>>
>>      docker run -it --rm toja/mojubuntu:latest
>>      
>### Lokalne budowanie kontenera
>>      docker build -t <nazwa obrazu> <ściżka do folderu z plikiem>
>>Nim zaczniemy warto wpisać ```docker system prune```. Pozwoli to uniknąć ewentualnych błędów. Budujemy kontener podając nazwę wyjściową kontenera (z małych liter) i ścieżkę, a to `-t` to nie wiem po co ale potrzebne. Przykładowo:
>>      
>>      docker build -t mojobraz C:\mojobraz
>>      
>### Czyszczenie pozostałości po kontenerach
>>      docker system prune
>>Usuwa pozostałości po kontenerach, np. po nieudanym budowaniu, gdy w `images` widać `<none>`. Przy budowie kontenera, jeśli wystąpi błąd to może to pomóc.
