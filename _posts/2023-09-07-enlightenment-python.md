---
categories: [backend]
published: false
title: How to get enlightenment in Python
---
Last week when I was working with LangChain library to build some POC, I tried to take sneak peek of source code of LangChain library to understand some internal prompts. But because of my less exposure in Python language I was not able to understand the syntax and internal implementation of LangChain library. At that moment I decided to get better in Python. In this article I will list down my journey towards the Python perfectionist.


OOPs in Python:
Class in python has two type of variable: class variable and instance variable. Class variable are shared variable and instance variables are those whose value are not changed.

```
class Car:
    # Class variable.
    milege = 23
    def __init__(self,model,fuel_type,power,torque):
        # instance variable.
        self.model = model
        self.fuel_type = fuel_type
        self.power = power
        self.torque = torque

```
