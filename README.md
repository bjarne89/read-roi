# read-roi

[![Build Status](https://travis-ci.com/hadim/read-roi.svg?branch=master)](https://travis-ci.com/hadim/read-roi)
[![PyPI version](https://img.shields.io/pypi/v/read-roi.svg?maxAge=2591000)](https://pypi.org/project/read-roi/)

Read ROI files .zip or .roi generated with ImageJ. Code is largely inspired from : http://rsb.info.nih.gov/ij/developer/source/ij/io/RoiDecoder.java.html

## Functions

```python
from read_roi import read_roi_file
from read_roi import read_roi_zip
from read_roi import read_roi_bytearray

roi = read_roi_file(roi_file_path)

# or

rois = read_roi_zip(roi_zip_path)

# or
import tifffile

with tifffile.TiffFile('path/to/file.tif') as tif:
    s = tif.imagej_metadata
    name = tif.filename
    for imageJ_roi in s['rois']:
        rois = read_roi_bytearray(imageJ_roi, name)

```

## Note

- Some format specifications are not implemented. See `RoiDecoder.java` for details.
- Most of "normal" ROI files should work.
- Feel free to hack it and send me modifications.

## Requirements

- Python 3.6 and above.

## Install

`pip install git+https://github.com/bjarne89/read-roi`

## License

Under BSD license. See [LICENSE](LICENSE).

## Authors

- Hadrien Mary <hadrien.mary@gmail.com>
- Bjarne Kvæstad <bjarnekvae@gmail.com>