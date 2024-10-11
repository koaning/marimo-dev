# marimo-dev

nbdev ... but for marimo!

```python
from marimo._ast.app import InternalApp
from demo import app


order = InternalApp(app).execution_order
codes = {k: v.code for k, v in InternalApp(app).graph.cells.items() if v.language=="python" and "#| lib" in v.code}
for i in order:
    if i in codes:
        print(codes[i].replace("#| lib", ""))
        print()
```
