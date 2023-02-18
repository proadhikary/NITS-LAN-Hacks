# Linux Hacks
NB: I keep doing stuffs and post the code snippt here, if I feel the process usefull. packages may expire or developers may update the methood. So, try; if failed, debug. Thanks!
<br>
<p>
<details>
<summary> <b>1. OCR from PDF using TIFF2TXT</b></summary><br/>

1. Install Imagemagic, tesseract.
```
pip install imagemagic
```
2. Run this to convet the pdfs into .tiff file to keep the resulation intact.
```
convert -density 300 *.pdf -depth 8 -strip -background white -alpha off 2%5d.tiff
```
3. Extract the texts into text file.
```
tesseract filename.tiff eng > outtext //single file
```
```
for i in *.tif ; do tesseract $i stdout >> outtext;  done; //multiple files
```
  
</details>
</p>
