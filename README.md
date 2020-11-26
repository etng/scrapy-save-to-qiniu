# Pipeline to save scrapy item field attachment to qiniu


## Installation

Install scrapy-save-to-qiniu using pip::

    $ pip install scrapy-save-to-qiniu

## Configuration

1. Add the  ``settings.py`` of your Scrapy project like this:

```python
QINIU_AK = ''
QINIU_SK = ''
QINIU_BUCKET = ''
QINIU_DOMAIN = ''
QINIU_DEL_SRC = True
QINIU_POLICY = {

}
QINIU_FIELDS = [
    'pdf_url',
]
```

2. Enable the pipeline by adding it to ``ITEM_PIPELINES`` in your ``settings.py`` file and changing HttpCompressionMiddleware
 priority:
   
```python
ITEM_PIPELINES = {
    'scrapy_save_to_qiniu.pipelines.SaveToQiniuPipeline': -1,
}
```
The order should before your persist pipeline such as save to database and after your preprocess pipeline.

## Usage

no need to change your code

## Getting help

Please use github issue

## Contributing

PRs are always welcomed.