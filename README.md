- [1. Utilizzo di base](#1-utilizzo-di-base)
  - [1.1. Aprire e chiudere vim](#11-aprire-e-chiudere-vim)
  - [1.2. Modalità di vim](#12-modalità-di-vim)
    - [1.2.1. Normal mode](#121-normal-mode)
    - [1.2.2. Insert mode](#122-insert-mode)
    - [1.2.3. Append mode](#123-append-mode)
    - [1.2.4. Command mode](#124-command-mode)
    - [1.2.5. Visual mode](#125-visual-mode)
      - [1.2.5.1. Copiare e incollare](#1251-copiare-e-incollare)
      - [1.2.5.2. Ordinare righe alfabeticamente](#1252-ordinare-righe-alfabeticamente)
  - [1.3. Buffers](#13-buffers)
    - [1.3.1. Split](#131-split)
  - [1.4. Configurazione di vim](#14-configurazione-di-vim)
    - [1.4.1. Aggiungere numero di riga](#141-aggiungere-numero-di-riga)


# 1. Utilizzo di base

## 1.1. Aprire e chiudere vim

Per aprire vim bisogna aprire il terminale e digitare uno dei seguenti comandi:
```
vim
```
oppure
```
vim <nomeFile>
```

Per chiudere vim basta digitare 
```vim
:q
```

## 1.2. Modalità di vim

### 1.2.1. Normal mode
quando apriamo vim siamo in **normal mode**, non ci permette di scrivere niente. Ma ci permette di usare alcune funzionalità, come ad esempio:
  - se abbiamo fatto delle modifiche a un file, ma vogliamo tornare in dietro, dobbiamo premere la lettera u (undo), in modo tale che verrà eliminata la modifica più recente
  - per tornare all'inizio di una riga di un file possiamo schiacciare 0
  - per andare alla fine della riga corrente possiamo schiacciare $
  - possiamo eliminare un carattere premendo x
  - possiamo eliminare l'intera riga premendo dd, ciò copia l'intera riga e possiamo schiacciare p per incollarla (cut and paste)
  - possiamo spostarci all'inizio del file premendo gg
  - possiamo spostarci alla fine di un file premendo shift+g

### 1.2.2. Insert mode
se vogliamo modificare o scrivere su un file dobbiamo passare alla **insert mode**, per fare ciò bisogna digitare
```vim
 i
 ```
 Quando abbiamo finito di modificare il file, per ritornare in normal mode bisogna schiacciare esc. 

### 1.2.3. Append mode
la **append mode** è un caso specifico di insert mode, in quanto ci permette di aggiungere qualcosa a una riga specifica di un file. Per fare ciò:
1. possiamo aprire tale file
2. spostarci sulla riga
3. premere shift+a, in questo modo entriamo in insert mode e il cursore viene spostato alla fine della riga(append). 

Può essere utile ad esempio se vogliamo aggiungere una nuova riga immediatamente sotto a quella corrente

### 1.2.4. Command mode
un'altra modalità è la **command mode**, per accedervi bisogna premere : e poi digitare dei comandi
```vim
:comando
```
ad esempio:
  - per quittare senza salvare si può usare il comando :q! (quit!)
  - per salvare usiamo il comando :w (write)
  - per salvare un nuovo file con nome digitiamo :w nomeFile
  - per quittare salvando si può digitare :wq
  - per copiare e incollare un file dentro ad un altro file possiamo digitare :r (read) 
  - per eseguire un comando del terminale direttamente da vim possiamo digitare :! comandoTerminale
  - per fare una find and replace digitiamo :%s/nomeDaCercare/nomeSostituto/g

### 1.2.5. Visual mode

Per accedere alla **visual mobe** bisogna digitare
```vim
v
```

#### 1.2.5.1. Copiare e incollare
La visual mode ci permette di copiare/incollare il testo, per fare ciò:
1. entriamo in visual mode
2. ci spostiamo con le frecce per selezionare il testo che vogliamo copiare
3. schiacciamo y
4.  incolliamo il testo premendo il tasto p (paste).

#### 1.2.5.2. Ordinare righe alfabeticamente
Inoltre in visual mode possiamo ordinare alfabeticamente delle linee di testo. Per fare ciò:
1. entriamo in visual mode
2. selezioniamo le righe che vogliamo ordinare con le frecce
3. poi premiamo :
4. infine digitiamo sort ui

## 1.3. Buffers

I buffers ci permettono di aprire più file contemporanemente.

Per aprire un nuovo buffer usando il contenuto di un file esistente bisogna digitare il comando 
```vim
:e nomeFile
```

Per aprire un nuovo buffer, rimanendo in quello corrente usiamo il comando 
```vim
:badd nomeFile
```

Per navigare tra i buffers usiamo i comandi buffer previous e buffer next
```vim
:bp e :bn
```

Per aprire un nuovo buffer vuoto dobbiamo digitare il comando 
```vim
:enew
```

Per chiudere un buffer possiamo usare il comando buffer delete
```vim
 :bd
```

### 1.3.1. Split 

Possiamo anche aprire più file in un unico buffer, splittando la schermata. Per fare ciò dobbiamo usare il comando 
```vim
:sp nomeFile
```
 Per splittare verticalmente usiamo il comando 
 ```vim
 :vs nomeFile
 ```

La schermata verrà divisa in due e il file su cui siamo in questo momento avrà il nome scritto in grassetto. Per spostarci da un file a un altro dobbiamo schiacciare 
```vim
ctrl + ww
```

Per chiudere uno dei due file bisogna spostarsi su quel file e digitare 
```vim
:q
```

Possiamo anche aprire direttamente due file con la schermata splittata digitando
```
vim -o nomeFile1 nomeFile2
```
oppure per splittare verticalmente
```
vim -O nomeFile1 nomeFile2
```

## 1.4. Configurazione di vim

Nella cartella home possiamo creare il file .vimrc che useremo per configurare vim.

Per aggiungere un commento in questo file usiamo "

### 1.4.1. Aggiungere numero di riga
per aggiungere permanentemente il numero di riga dobbiamo digitare all'interno del file .vimrc il comando:
```vim
set number
```
