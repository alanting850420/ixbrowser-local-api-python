# ixBrowser Local API

ixBrowser local API V2.0 official python version

## Installation

1. pypi install (Not supported yet)
```BASH
pip install ixbrowser-local-api
```

2. Source code install
```BASH
git clone https://github.com/ixspyinc/ixbrowser-local-api-python.git
cd ixbrowser-local-api-python
python setup.py install
```

## Usage

Basic usage
```python
import random
from ixbrowser_local_api import IXBrowserClient

c = IXBrowserClient()
data = c.get_profile_list()
if data is None:
    print('Get profile list error:')
    print('Error code=', c.code)
    print('Error message=', c.message)
else:
	item = random.choice(data)

	profile_id = item['profile_id']
	print('Random choice profile_id=', profile_id)

	open_result = c.open_profile(profile_id, cookies_backup=False, load_profile_info_page=False)
	if open_result is None:
		print('Open profile error:')
		print('Error code=', c.code)
		print('Error message=', c.message)
	else:
		print(open_result)
```

Advance use

For detailed usage, please refer to the files in the /examples directory.


