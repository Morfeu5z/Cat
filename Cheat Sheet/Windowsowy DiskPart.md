# DISKPART
## Formatowanie Pendriva przez CMD
1. Wpisujemy do cmd polecenie **`diskpart`**.
2. Polecenie **`list disk`** wyświetli listę dysków oraz pendriveów.
3. Namierzamy dysk do sformatowania po czym wpisujemy **`select disk {nr dysku}`**, np `select disk 2`.
4. Polecenie **`Clean`** odśmieci wcześniej wybrany dysk usuwając wszystko.
5. Teraz należy stworzyć partycję przewodnią przez polecenie **`create partition primary`**.
6. Dla pewności wybieramy **`select partition 1`**, po czym ją aktywujemy poleceniem **`active`**.
7. Na koniec **`format fs=ntfs`** by sformatować wybrany dysk do systemu plikowego ntfs.
8. Lub to samo ale szybko z dopiskiem quick czyli **`format fs=ntfs quick`**