# Values with uncertanties: `ValueWithError`

One of the central object in `ostap` is C++ class `Gaudi::Math::ValutWithError`, accessible in python via shortcut `VE`. This class stands fot r a combination of the value with uncertainties:
```python
from Ostap.Core import VE
a = VE( 10 , 10 ) ## the value & squared uncertainty - 'variance' 
b = VE( 20 , 20 ) ## the value & squared uncertainty - 'variance' 
print "a=%s" % a 
print "b=%s" % b 
print 'Value    of a is %s'  % a.value() 
print 'Effor    of b is %s'  % b.error() 
print 'Variance of b is %s'  % b.cov2 () 
```  
A lot of math operations are predefined for `VE`-objects.
{% challenge "Challenge" %}
Make a try with all binary  operations (`+,-,*,/,**`) for the pair 
of `VE` objects and combinations of `VE`-objects with numbers, e.g. 
```python
a + b 
a + 1 
1 - b
2 ** a 
a +=1   
b += a  
``` 
Compare the difference for following expresssions: 
```python
a/a      ## <--- HERE 
a/VE(a)  ## <--- HERE
a-a      ## <--- HERE 
a-VE(a)  ## <--- HERE
```
Note that for trivial cases the correlations are propertly taken into account     
{% endchallenge %}
Additionally many math-functions are provided, carefully takes care on uncertainties
```
from LHCbMath.math_ve import * 
sin(a)+cos(b)/tanh(b) 
atan2(a,b)/log(a) 
```