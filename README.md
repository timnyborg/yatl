# Yet Another Template Language

This is the web2py template language described [here](http://web2py.com/books/default/chapter/29/05/the-views] made available as stand alone package so it can be used anywhere.

Basically it is pure python within "{{" ... "}}" delimiters and blocks are terminated with "pass" if termination is not obvious. For example

```
from yatl import render, SPAN

example = """
<div> 
{{for k in range(num):}}
<span>{{=SPAN(k, _class='number')}} is {{if k % 2 == 0:}}even{{else:}}odd{{pass}}</span>
{{pass}}
</div>
"""

print(render(example, context=dict(num=10, SPAN=SPAN), delimiters="{{ }}"))
```

In the example SPAN is an optional helper.
Output is escaped by default unless marked up with the XML helper as in {{=XML('1 < 2')}}.
