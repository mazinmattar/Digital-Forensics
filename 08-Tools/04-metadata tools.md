exiftool للصور 
download -> https://github.com/exiftool/exiftool

pdfinfo للملفات البيدي اف
download -> https://www.google.com/search?q=https://github.com/freedesktop/poppler

olevba للملفات اللي اخرها .doc
download -> https://github.com/decalage2/oletools

pdfimages -list 
pdfimages -all لاستخراج الصور من الملفات 

# فحص الصور

exiftool letter-image.jpg
strings letter-image.jpg | less   (download -> https://www.google.com/search?q=https://github.com/bminor/binutils-gdb)
binwalk -e letter-image.jpg   # يفكّ محتوى مخفي إن وُجد  (download -> https://github.com/ReFirmLabs/binwalk)
steghide info letter-image.jpg   # إن تم تثبيت steghide (download -> https://www.google.com/search?q=https://github.com/vnaum/steghide)

pngcheck  فحص سريع لبنية الصور (download -> http://www.libpng.org/pub/png/apps/pngcheck.html)

zsteg لتفحص ستجانوغرافيا PNG (download -> https://github.com/zed-0xff/zsteg)
