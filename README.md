# DJANGO RANGE SLIDER

<snippet>
  <content>

[![Build Status](https://travis-ci.org/Chive/django-multiupload.svg?branch=master)](https://travis-ci.org/Chive/django-multiupload)


A range-slider field that uses django's ```forms.CharField()``` and ```jquery-ui``` to stylize and create the field. 

## Installation

* Install the package using pip (or easy_install if you really have to)

```bash
$ pip install django-multiupload
```

* Or directly from this repository to get the development version (if you're feeling adventurous)

```bash
$ pip install -e git+https://github.com/Chive/django-multiupload.git#egg=multiupload
```

## Usage

An example app is avilable at [example app](https://github.com/shakle17/django_range_slider/tree/master/test_slider).


Since we use ```jquery``` and ```jquery-ui``` for the widgets , you need to include them in your main template (or the template where the widgets will be rendered)

```python
# templates/base.html

# You should include jquery , jquery-ui.js & jquery-ui.css
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>
<link href="http://code.jquery.com/ui/1.12.0/themes/smoothness/jquery-ui.css" rel="stylesheet">
<script src="http://code.jquery.com/ui/1.12.0/jquery-ui.min.js" ></script>
</head>
```

Add the form field to your form , with or without the optional keyword-arguments.
* ```label=False``` is set as default value for the input field

```python
# forms.py
from django import forms
from django_range_slider.fields import RangeSliderField

class SliderForm(forms.Form):
     name_range_field = RangeSliderField(minimum=30,maximum=300,name="TestName") # with name inside the input field (no label)
     range_field = RangeSliderField(minimum=10,maximum=102) # without name or label
     label_range_field = RangeSliderField(label=True,minimum=1,maximum=10) # with label (no name)

    # For images (requires Pillow for validation):
    attachments = MultiImageField(min_num=1, max_num=3, max_file_size=1024*1024*5)
```

## License
MIT License

Copyright (c) 2016 Aleksandar

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

</content>
</snippet>
