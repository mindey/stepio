# StepIO
Asset parser for Step.investables and Step.deliverables in Infinity.

Usage:

```
>>> import stepio
>>> i = u'programmer person-days: 10~12@1.2h; analyst person-days: 11~45@1.1h; software package: 1@15.453h'

>>> stepio.parse(i)

[{'programmer person-days': 
  {
    'min_units': '10',
    'max_units': '12',
    'f_units': '',
    'min_price': '1.2',
    'max_price': '1.2',
    'f_price': '',
    'price_unit': 'h'
    }
  },
 {'analyst person-days': 
  {
    'min_units': '11',
    'max_units': '45',
    'f_units': '',
    'min_price': '1.1',
    'max_price': '1.1',
    'f_price': '',
    'price_unit': 'h'
    }
 },
 {'software package': 
  {
    'min_units': '1',
    'max_units': '1',
    'f_units': '',
    'min_price': '15.453',
    'max_price': '15.453',
    'f_price': '',
    'price_unit': 'h'
    }
 }
]
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



