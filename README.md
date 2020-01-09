# icris_automation

**icris_automation** is a Python automation tool that  provides convenient to automate tasks such as document purchasing from the Hong Kong government's ICRIS website convenient and efficient. 

The package is highly modularized, making it easy to modify and extend the functionality provided. Different parts of the ICRIS website are represented as classes--based on the Page Object Model--in the `website_layout` module; functions associated with navigating the website and carrying out tasks across multiple pages are defined in the `navigation` module; and functions related to managing data are defined in the `data_processing` module. In the context of this project, an `identifier` is a registered company name or a Companies Registry Number through which a coporate entity in Hong Kong can be identified independently.

## Installation

### Method 1
1. Download the root directory
2. Run `pip install -r requirements.txt`

### Method 2

1. Run 'pip install git+ssh:`

## Usage

The package can be imported into the Python interpreter and be run from the command line. 

Running it in Python Interactive:
```Python
>>> from icris_automation import *
>>> 
>>> companies_list = ['MIGRASIA GLOBAL SOLUTIONS LIMITED', 'TopMan Asia Limited']
>>> browser = init_browser(headless=False) # Open Firefox
>>> browser = init_icris(browser)
>>> status_df = process_requests(
...                            companies_list,
...                            browser,
...                            document_type='Annual Return',
...                            num_doc=3,
...                            ) # Cart documents and return a dataframe containing information about the process
```

Running it from the command line:
```Bash
$ python -m icris_automation entities.txt Annual\ Return 3 -p
```

## License

This project is distributed under the [MIT](https://github.com/adityaverma415/icris_automation/blob/master/LICENSE) license. 
