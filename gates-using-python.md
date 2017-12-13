## Let's Implement `AND`, `NOT` and `OR` gates  

Before starting I want to remind you all one thing.

> Any fool can write code that a computer can understand.
> Good programmers write code that humans can understand.

```
class Gate(object):
    """ class representing a gate. It can be any gate. """
    
    def __init__(self, **kwargs):
        """ constructor """
        self.output = None  # placeholder to save the output
        for key, value in kwargs.items():
            setattr(self, key, value)  # assign all the input values against an attribute
    
    def logic(self):
        """ the brain of the class """
        raise NotImplementedError
    
    def output(self):
        """ the output of the gate """
        return self.output
```
