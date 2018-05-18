<div align="center">

# - Git -
### With Github.com

<div align="justify">

>#### Git login
>>      git config --global user.email "mój@email.com"
>>      git config --global user.name "MyName"
>>W ten sposób umożliwimy pushowanie repo, do którgo mamy dostęp.
>
>#### Clone Repo
>>      git clone https://github.com/Morfeu5z/Cat.git
>
>#### Pull
>>      git pull
>>Pozwala pobrać najnowszą wersję z githuba
>
>#### Force pull
>>      git reset --hard origin/<branch_name>
>>W ten sposób można wymusić zmianę Repo na maszynie lokalnej na kod z githuba. Wcześniej musimy być w folderze z projektem.
>
>#### Status
>>      git status
>>Pozwala na sprawdzenie które pliki są śledzone i zmieniane.
>
>#### Śledzenie plików
>>      git add -A
>>Dodaje wszystkie pliki w obecnym katalogu do śledzenia wersji
>>
>>      git add app.py
>>Taki zazpis pozwala dodać konkretne pliki do śledzenia.
>>
>>      git reset
>>Resetuje śledzenie wersji plików
>>
>>      touch .gitignore
>>Gitignore to plik wskazujący, które pliki nie będą sprawdzane.
>>      
>#### Gałęźie
>>      git branch
>>Wyświetli dostępne gałązki
>>
>>      git checkout mojagalaz
>>W ten sposób zmieniasz gałąź
>
>#### Commit
>>      git commit -m 'New update'
>>Pozwala na dodanie commita ale nie robi pusha.
>
>#### Push
>>      git push LinkToMyProject master
>>Wykona się wysłanie nowej wersji na github'a na gałąź master. Może poprosić o login i haslo.
>
