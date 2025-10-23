[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/fomightez/pmc_id_converter_demo-binder/HEAD?urlpath=%2Flab%2Ftree%2FDemonstrate+pmc_id_converter.ipynb)

# pmc_id_converter_demo-binder
Demonstrating of pmc_id_converter for ID converter between PMID, PMCID and DOI, via the MyBnder service.  
Click 'launch' badge above to get started.

See [suqingdong's repo for pmc_id_converter here](https://github.com/suqingdong/pmc_id_converter) for more about the command line/Python utility.

I use Jupyter Notebooks here with some code to demonstrate how easy it is to use and how you can combine `pmc_id_converter` use in with Python coding and Jupyter convenience to more easily mine or collect information you need about scientific references at PubMed Central and PubMed.

## IMPORTANT: PLAY NICE with the NCBI API Service:

You should remember to use your actual email address when using it in production.

When installed via `pip` it doesn't prompt you to set email. If you are using this to do a lot you should clone [suqingdong's original repo for pmc_id_converter from here](https://github.com/suqingdong/pmc_id_converter) and edit the code to set the email to your email to consider NCBI.


## Attribution

***Clarifying Software Attribution: I, Wayne, am not involved with suqingdong's pmc_id_converter development in any way. I simply set up this repository to demonstrate the use of it in MyBinder-served Jupyter Sessions. See the links above and below for the materials by suqingdong who develops and maintains fpmc_id_converter.***

--------

## Usage
### Command Line

See [the source repo here](https://github.com/suqingdong/pmc_id_converter#command-line) for command line Usage details.

### Python

(The offerings at the source repo would be best as this, I suggest. See the demo for more information.)

```python
from pmc_id_converter import API

query_id = 'PMC3531190'
records_of_query_results = API.idconv(query_id)
for record in records_of_query_results:
    print(record)
query_id = '23193287'
records_of_query_results = API.idconv(query_id)
for record in records_of_query_results:
    print(record)
query_id = '10.1093/nar/gks1195'
records_of_query_results = API.idconv(query_id)
for record in records_of_query_results:
    print(record)
print(record.data['pmcid'])
print(record.data['pmid'])
print(record.data['doi'])


records_of_query_results = API.idconv('PMC3531190', 'PMC3531191123', 'PMC3531191')
for record in records_of_query_results:
    print(record)

#--OR---
query_ids = 'PMC3531190, PMC3531191123, PMC3531191'
records_of_query_results = API.idconv(query_ids)
for record in records_of_query_results:
    print(record)

my_pmids = []
query_ids = 'PMC3531190, PMC3531191123, PMC3531191'
records_of_query_results = API.idconv(query_ids)
for record in records_of_query_results:
    my_pmids.append(record.data.get('pmid'))
my_pmids = [str(x) if isinstance(x, int) else x for x in my_pmids]
print(my_pmids)
```



-------

## Related utilities

- ???

