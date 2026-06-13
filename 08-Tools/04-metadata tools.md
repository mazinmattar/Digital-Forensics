exiftool للصور 

pdfinfo للملفات البيدي اف

olevba للملفات اللي اخرها .doc

pdfimages -list 
pdfimages -all لاستخراج الصور من الملفات 

# فحص الصور

exiftool letter-image.jpg
strings letter-image.jpg | less
binwalk -e letter-image.jpg   # يفكّ محتوى مخفي إن وُجد
steghide info letter-image.jpg   # إن تم تثبيت steghide

pngcheck فحص سريع لبنية الصور

zsteg لتفحص ستجانوغرافيا PNG
