<div align="center">

# - Samba on debian -
### Prosta konfiguracja dla dysku sieciowego

<div align="justify">

### Instalacja samba
Do zainstalowania wystarczy użyć polecenia:
> `sudo apt install samba`

Następnie dodamy folder, w którym będą udostępniane podfoldery:
> `sudo mkdir /home/\<username\>/sambashare/`
>
> `sudo mkdir /home/aleks/netdrive/`
 
A w nim podfolder aleks_space

> `sudo mkdir /home/aleks/netdrive/aleks_space`

Teraz dodajmy konfigurację w pliku `/etc/samba/smb.conf`
> `sudo nano /etc/samba/smb.conf`

Na końcu pliku należy dodać konfigurację, której parametry określają zachowanie katalogu udostępnianego.

Stwórzmy prywatny katalog do którego dostęp ma Aleks:
```bash
[myspace]                                   # Nazwa katalogu w sieci    
    comment = Przestrzeń dyskowa Aleksa     # Komentarz
    path = /home/aleks/netdrive/aleks_space # Ścieżka do katalogu
    read only = no                          # Blokada: jedynie do odczytu
    browsable = yes                         # Widoczne w sieci
    guest ok = no                           # Dozwoleni niezalogowani
    create mask = 0760                      # Narzucenie uprawnień plikom
    directory mask = 0760                   # Narzucenie uprawnień katalogom
    force group = aleks                     # Narzucenie grupy plikom/katalogom
    valid users = aleks                     # Urzytkownicy z dostępem
```

A teraz do którego ma dostęp cała rodzina:
```bash
[familyspace]    
    comment = Wspolna przestrzen na pliki
    path = /home/aleks/netdrive/familyspace/
    read only = no
    browsable = yes
    guest ok = yes
    create mask = 0760
    directory mask = 0760
    force group = forall
```

Na koniec coś dla wszystkich ale tylko do odczytu. Pamiętać należy by sam katalog miał uprawnienia rwx dla wszystkich (`sudo chmod 777 anonspace` lub `sudo chmod 776 anonspace` więcej w tabeli uprawnień na samym dole)
```bash
[anonspace]    
    comment = Wspolna przestrzen na pliki dla wszystkich, ale tylko do odczytu
    path = /home/aleks/netdrive/anonspace/
    read only = yes
    browsable = yes
    guest ok = yes
```

Dodanie do firewall'a zasady o ruchu
> `sudo ufw allow samba`

Dodanie użytkownika samba, pierw dodając użytkowników linuxowych:
> `sudo adduser aleks`
> 
> `sudo smbpasswd -a aleks`

Nowa grupa dla użytkowników
> `sudo addgroup forall`

Dodanie grup użytkownikom
> `sudo usermod -a -G group user`
> 
> `sudo usermod -a -G forall aleks`

Usuwanie użytkownika z grupy
> `sudo gpasswd -d user group`
> 
> `sudo gpasswd -d aleks forall`

Restart serwisu
> `sudo service smbd restart`

Wylistowanie użytkowników samba
> `sudo pdbedit -L -v`

Wyświetl listę grup przypisanych użytkownikowi
> `sudo groups aleks`

<br>

:warning: Uprawnienia i grupy przypisane do katalogów i plików są często mocną bazą dla zachowania udostępnionych katalogów samba. 

:warning: Nawet z brakiem uprawnień do odczytu, nadpisu i wykonywania pliku, nadal można go skasować jeśli reguła katalogu samba na to zezwala.

### Lista uprawnień
* 0 = ---
* 1 = --x
* 2 = -w-
* 3 = -wx
* 4 = r--
* 5 = r-x
* 6 = rw-
* 7 = rwx

### Oznaczenia
* r - read, odczyt
* w - write, zapis
* x - execute, wykonaj

### Kolejność uprawnień
> [`właściciel` `grupa` `inni`]

> [`drwx------`] właściecie ma pełne funkcje 

> [`drwxrwx---`] właściecie i grupa mają pełne funkcje 

> [`drwxrwxrwx`] właściecie, grupa i pozostali mają pełne funkcje