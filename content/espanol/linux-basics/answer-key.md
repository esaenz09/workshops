---
title: "Answer Key - Linux Basics"
description: "Respuestas de las actividades"
date: 2022-09-23
difficulty: "Intermedio"
hidden: true
draft: true
weight: 15
---

### Actividad 1

```
whoami
```

### Actividad 2

```
pwd
cd Desktop
cd..
```

### Actividad 3

```
ls -l
mv Documents/ Downloads/
ls -l Downloads
mv Downloads/Documents/ .
```

### Actividad 4

```
mkdir files
touch file1
vim file1
mv file1 files
```

### Actividad 5

```
chmod u=rwx g=rx o=x file1
chmod 751 [insert filename]
```

### Actividad 6

```
cd
grep -R "Do. Or do not. There is no try."
find . -name *.sh
```

### Actividad 7

```
head -n 5 malware.sh
tail -n 5 malware.sh
cat malware.sh
more malware.sh
less malware.sh
```

### Actividad 8

```
find . -name *.txt
grep -R "Do. Or do not. There is no try."
ls -la
diff malware.sh secret-message.txt
vimdiff malware.sh secret-message.txt
```

### Actividad 9

```
rm Downloads/malware.sh
rm files
mkdir files
```

### Actividad 10

```
mv secret-message.txt .
ls -l
cp secret-message.txt file1
ls
cd files
cp secret-message.txt file1
ls -l
```

### Actividad 11

```
tar -f files.tar.gz
```

; Mantenerlo claro para principiantes. Preserva los términos técnicos, la sintaxis de código y el formato. Traduce únicamente los comentarios que expliquen conceptos. Adapta las referencias culturales cuando sea apropiado. No traduzcas la clave de encabezado "title"; no traduzcas el HTML de imágenes.