# pero-enhance

Tool for text-guided textual document scan quality enhancement.

<img src="images/orig.png" height="256"> <img src="images/enhanced_correct.png" height="256">

We currently provide models for OCR and enhancement of czech newspaper.

## Installation
Clone the repository and add the pero_enhance and pero_ocr package to your `PYTHONPATH`:
```
clone https://github.com/DCGM/pero-enhance.git
export PYTHONPATH=/abs/path/to/repo/pero-enhance:/abs/path/to/repo/pero-enhance/pero-ocr:$PYTHONPATH
```
Install other dependencies:
```
TBD
```
Before processing a document, you need to download configuration and models needed for enhancement and OCR: 
```
python ./model/download_models.py
```
By default, models for czech newspaper is downloaded. Other models can be found in the table below. The list will be updated as we prepare more models.

## Usage
The enhancement uses document information in PAGE XML format. Folder of images can be enhanced by running following:
```
python repair_page.py -i /path/to/images -x /path/to/xmls -o /path/to/outputs
```
Alternatively, you can run interactive demo by running the following:
```
python demo.py -i /path/to/image -x /path/to/xml
```
In case of XML missing or the path to XML file/folder not specified, automatic text detection and OCR is done using the pero `PageParser`. The default path to the downloaded enhancement and OCR models can be modified using `-r /path/to/enhancement/json`and `-p /path/to/ocr/config`, respectively. 

## Models

 | OCR Model | Enhancement Model | Target data |
 | --- | --- | --- |
 | [ocr_LN_2019-12-18.zip](http://www.fit.vutbr.cz/~ihradis/pero-models/ocr_LN_2019-12-18.zip) | [enhance_LN_2019-12-18.zip](http://www.fit.vutbr.cz/~ihradis/pero-models/enhance_LN_2019-12-18.zip) | Czech newspaper (Lidové Noviny) |
 | More to come | | |
