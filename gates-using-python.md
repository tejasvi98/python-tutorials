## Let's Implement digital gates using python

Before starting I want to remind you all one thing.

> Any fool can write code that a computer can understand.
> Good programmers write code that humans can understand.

Now lets see the different way people could implement this

### Using simple functions

```
def and_gate(input_1, input_2):
    """ and gate implementation """
    return input_1 and input_2

def or_gate(input_1, input_2):
    """ or gate implementation """
    return input_1 or input_2

def not_gate(input):
    """ not gate implementation """
    return not input

```

Lets see the problems in this implementation,

* Lets say we want to implement some feature at gate level, which means
something that is applicable for all the gates. There is no provision to do that.
* Lets say I want to reuse my code to create something else. For example, if want
to create a NAND gate by combining NOT and AND there is on provision to do that.
* What ever code we have written above. Are we really able to imagine it as a real life thing.
* Something is missing here

### Lets rewrite the same thing using OOPs

```
class Gate(object):
    """ class representing a gate. It can be any gate. """

    def __init__(self, *args):
        """ initialise the class """
        self.input = args
        self.output = None

    def logic(self):
        """ the intelligence to be performed """
        raise NotImplementedError

    def output(self):
        """ the output of the gate """
        self.logic()
        return self.output


class AndGate(Gate):
    """ class representing AND gate """

    def logic(self):
        self.output = self.input[0] and self.input[1]


class OrGate(Gate):
    """ class representing OR gate """

    def logic(self):
        self.output = self.input[0] and self.input[1]


class NotGate(Gate):
    """ class representing NOT gate """

    def logic(self):
        self.output = not self.input[0]
```

Now lets see how this is different from the above implementation,

* If I want to implement something at `GATE` level. Lets say something
that is common to all gates, Then I can simply do it in the `GATE` class
and will be available for all other classes `AND`, `OR` and `NOT`
* I can simply combine `AND` and `NOT` to create `NAND` gate

```
class NandGate(AndGate, NotGate):
    pass
```
* How the above code snippet works? Can someone tell me? I will give you some hints `multiple inheritance`, `super()`

### Practise problems

* Implement Universal gates using OOPs (I want them to be created out of basic gates). Hint: Implement basic gates first and then using multiple inheritance implement universal gates.
