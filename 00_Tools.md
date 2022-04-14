# All  the tools

  -  <a href="#Cross Linked">Cross Linked</a> 


## [Cross Linked](https://github.com/m8r0wn/CrossLinked)

<p>
  CrossLinked is a LinkedIn enumeration tool that uses search engine scraping to collect valid employee names from a target organization. This technique provides accurate results without the use of API keys, credentials, or even accessing the site directly. Formats can then be applied in the command line arguments to turn these names into email addresses, domain accounts, and more.CrossLinked is a LinkedIn enumeration tool that uses search engine scraping to collect valid employee names from a target organization. This technique provides accurate results without the use of API keys, credentials, or even accessing the site directly. Formats can then be applied in the command line arguments to turn these names into email addresses, domain accounts, and more.
  </p>

<b> To run </b>
```bash

# Help
└─$ python3 crosslinked.py -h

# To get the info
└─$ python3 crosslinked.py -f '{first}.{last}@domain.com' google 

└─$ python3 crosslinked.py -f 'google\{f}{last}' -t 45 -j 0.5 google


```

  
