---
theme: uncover
style: |
  section {
  }
  section {
    background-image:    url(./images/background.svg);
    background-size:     cover;
    background-repeat:   no-repeat;
    background-position: center center;
    overflow: hidden;
    width: 100vw;
    height: 100vh;
    text-align: left;
    vertical-align: top;
    padding-top: 50px;
    display: table-cell;
  }
  section.title {
    text-align: center;
    vertical-align: middle;
    padding-top: 0px;
    display: table-cell;
  }
  section.title header {
    display: none;
  }
  header {
    text-align: left;
    color: black;
  }
  img[alt~="center"] {
    display: block;
    margin: 0 auto;
  }
  .columns {
    display: flex;
    gap: 1rem;
  }
  .columns > div {
    font-size: 0.8rem;
    flex: 1 1 0;
  }
  .big-graph > svg {
    max-height: 500px;
  }
  .language-mermaid > svg {
    max-height: 480px;
  }

---

<!-- header: TITLE -->
<!-- _class: title -->

# TITLE

SUBTITLE
<script type="module">
  import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
  mermaid.initialize({ startOnLoad: true });
  await mermaid.run({
    querySelector: '.language-mermaid',
  });
</script>

---

<!-- header: Example > Overview -->

## What we'll cover
* Mermaid graph
* Columns
* Images
* Code blocks
* All together
* Exports

---

<!-- header: Example > Mermaid Graph -->

### Mermaid Graph

```mermaid
  graph TD;
  A[Goes to] --> B;
  B{Decision?} --> |yes| C;
  B --> |no| D;
  C[Next step] --> E;
  E{Another decision?} --> |yes| G;
  E --> |no| D;
  D[outcome 1];
  G[outcome 2];
```

---

<!-- header: Example > Columns -->

### Two column layout

<div class=columns>
<div>

- You can put anything in this column

</div>
<div>

Any something else over here including images and graphs

</div>
</div>

---

### Three column layout

<div class=columns>
<div>

Now with

</div>
<div>

three 

</div>
<div>

columns 

</div>
</div>

---

<!-- header: Example > Images -->

# Images
* Usually width 400px is a good setting

Include in div
<div>
    <img width="400px" src=./images/example.svg/>
</div>

Include inline
![width:400px center](./images/example.svg)

---

<!-- header: Example > Code Blocks -->

#### Code Blocks
Python
```python
import math
def example():
    return math.sqrt(4)
```

Bash
```bash
echo "Hello world"
```

Javascript
```javascript
function example() {
    return 4;
}
```

---

<!-- header: Example > Together! -->

# All combined now!

<div class=columns>
<div>
    <img width="400px" src=./images/example.svg/>
</div>
<div>

```mermaid
graph TD;
  A[Goes to] --> B;
  B{Decision?} --> |yes| C;
  B --> |no| D;
  C[Next step] --> E;
  E{Another decision?} --> |yes| G;
  E --> |no| D;
  D[outcome 1];
  G[outcome 2];
```

</div>

---

<!-- header: Example > Exporting -->

# Export Slides
* The normal PDF export doesn't work great with divs and embedded mermaid
* Instead open the presentation as an HTML file in a browser and print to PDF
  ```
  marp --html presentation.md
  google-chrome-stable --headless --print-to-pdf="presentation.pdf" ./presentation.html
  ```
