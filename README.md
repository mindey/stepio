# StepIO
Asset parser for Step.investables and Step.deliverables in Infinity.

Usage:

```{python}
>>> import stepio
>>> i = u'programmer person-days: 10~12@50usd; analyst person-days: 11~45@45usd; software package: 1@159.99usd'

>>> stepio.parse(i)

[{u'programmer person-days': {'max_units': u'12', 'min_units': u'10', 'price_unit': u'usd', 'f_units': '', 'min_price': u'50', 'f_price': '', 'max_price': u'50'}}, {u'analyst person-days': {'max_units': u'45', 'min_units': u'11', 'price_unit': u'usd', 'f_units': '', 'min_price': u'45', 'f_price': '', 'max_price': u'45'}}, {u'software package': {'max_units': u'1', 'min_units': u'1', 'price_unit': u'usd', 'f_units': '', 'min_price': u'159.99', 'f_price': '', 'max_price': u'159.99'}}]
```

```{python}
>>> i = u'complete solar assembly drawings: 0~1; solar cell assemblies: 1~2[exp(x)]@5.5~5.9[beta(2,2)((x-a)/(b-a))]h'

>>> stepio.parse(i)

[{'complete solar assembly drawings': 
  {
    'min_units': '0',
    'max_units': '1',
    'f_units': '',
    'min_price': '',
    'max_price': '',
    'f_price': '',
    'price_unit': ''
    }
  },
 {'solar cell assemblies': 
  {
    'min_units': '1',
    'max_units': '2',
    'f_units': 'exp(x)',
    'min_price': '5.5',
    'max_price': '5.9',
    'f_price': 'beta(2,2)((x-a)/(b-a))',
    'price_unit': 'h'
    }
 }
]
```



