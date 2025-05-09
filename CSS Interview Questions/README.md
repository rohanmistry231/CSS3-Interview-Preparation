# CSS Interview Questions for AI/ML Roles

This README provides **170 CSS interview questions** tailored for AI/ML students preparing for technical interviews, focusing on CSS’s role in styling web interfaces for AI/ML applications (e.g., dashboards, model deployment interfaces, and data visualizations). The questions are categorized into **CSS Basics**, **Box Model and Layouts**, **Flexbox and Grid**, **Animations and Transitions**, **Responsive Design**, **CSS Preprocessors**, **Performance Optimization**, and **Integration with AI/ML**. Each category is divided into **Basic**, **Intermediate**, and **Advanced** levels, with practical code snippets to illustrate concepts. This resource supports candidates aiming for roles that combine web development with AI/ML workflows, such as creating responsive and visually appealing interfaces for model outputs or deploying ML models via web applications.

## CSS Basics

### Basic
1. **What is CSS, and how is it used in web development?**  
   Cascading Style Sheets style HTML elements.  
   ```html
   <style>
       h1 { color: blue; }
   </style>
   <h1>Hello, World!</h1>
   ```

2. **How do you link a CSS file to HTML?**  
   Uses `<link>` tag.  
   ```html
   <head>
       <link rel="stylesheet" href="styles.css">
   </head>
   ```

3. **What is the difference between inline, internal, and external CSS?**  
   Inline uses `style` attribute, internal uses `<style>` tag, external uses separate file.  
   ```html
   <!-- Inline -->
   <p style="color: red;">Inline</p>
   <!-- Internal -->
   <style>
       p { color: blue; }
   </style>
   <!-- External -->
   <link rel="stylesheet" href="styles.css">
   ```

4. **What is a CSS selector?**  
   Targets HTML elements for styling.  
   ```html
   <style>
       .class { font-size: 16px; }
       #id { color: green; }
   </style>
   <p class="class">Class</p>
   <p id="id">ID</p>
   ```

5. **How do you apply CSS to multiple elements?**  
   Uses comma-separated selectors.  
   ```html
   <style>
       h1, p, .class { margin: 10px; }
   </style>
   <h1>Title</h1>
   <p>Text</p>
   ```

6. **How do you visualize CSS rule application?**  
   Plots rule specificity (mock example).  
   ```python
   import matplotlib.pyplot as plt
   def plot_css_specificity():
       plt.plot([1, 2, 3], [10, 20, 15], 'o-', label='Specificity')
       plt.title('CSS Rule Specificity')
       plt.savefig('css_specificity.png')
   ```

#### Intermediate
7. **Write a function to toggle CSS classes dynamically.**  
   Adds/removes classes.  
   ```html
   <div id="box" class="box">Content</div>
   <button onclick="toggleClass()">Toggle</button>
   <style>
       .box { background: blue; }
       .active { background: red; }
   </style>
   <script>
   function toggleClass() {
       document.getElementById('box').classList.toggle('active');
   }
   </script>
   ```

8. **How do you use CSS pseudo-classes?**  
   Styles based on state.  
   ```html
   <style>
       a:hover { color: red; }
       li:nth-child(odd) { background: #f0f0f0; }
   </style>
   <a href="#">Link</a>
   <ul>
       <li>Item 1</li>
       <li>Item 2</li>
   </ul>
   ```

9. **Write a function to apply CSS styles dynamically.**  
   Sets inline styles.  
   ```html
   <div id="dynamic">Styled</div>
   <script>
   function applyStyles(elementId, styles) {
       const element = document.getElementById(elementId);
       Object.assign(element.style, styles);
   }
   applyStyles('dynamic', { color: 'blue', fontSize: '20px' });
   </script>
   ```

10. **How do you use CSS variables?**  
    Defines reusable values.  
    ```html
    <style>
        :root { --primary-color: #007bff; }
        .box { background: var(--primary-color); }
    </style>
    <div class="box">Box</div>
    ```

11. **Write a function to update CSS variables.**  
    Modifies custom properties.  
    ```html
    <div class="dynamic">Dynamic</div>
    <style>
        :root { --bg-color: blue; }
        .dynamic { background: var(--bg-color); }
    </style>
    <script>
    function updateCSSVariable(name, value) {
        document.documentElement.style.setProperty(name, value);
    }
    updateCSSVariable('--bg-color', 'red');
    </script>
    ```

12. **How do you use the `!important` rule?**  
    Increases rule priority.  
    ```html
    <style>
        .box { color: blue !important; }
        .box { color: red; }
    </style>
    <div class="box">Text</div>
    ```

#### Advanced
13. **Write a function to compute CSS specificity.**  
    Calculates selector weight (mock).  
    ```html
    <script>
    function computeSpecificity(selector) {
        // Mock: ID=100, Class=10, Element=1
        const idCount = (selector.match(/#/g) || []).length * 100;
        const classCount = (selector.match(/\./g) || []).length * 10;
        const elementCount = (selector.match(/[a-z]/gi) || []).length;
        return idCount + classCount + elementCount;
    }
    console.log(computeSpecificity('#id .class div')); // 111
    </script>
    ```

14. **How do you optimize CSS selector performance?**  
    Uses specific selectors.  
    ```html
    <style>
        /* Less efficient */
        * { margin: 0; }
        /* More efficient */
        .container div { margin: 0; }
    </style>
    <div class="container"><div>Content</div></div>
    ```

15. **Write a function to validate CSS properties.**  
    Checks valid properties.  
    ```html
    <script>
    function validateCSSProperty(property, value) {
        const div = document.createElement('div');
        div.style[property] = value;
        return div.style[property] === value;
    }
    console.log(validateCSSProperty('color', 'blue')); // True
    console.log(validateCSSProperty('invalid', 'value')); // False
    </script>
    ```

16. **How do you implement CSS feature detection?**  
    Uses `@supports`.  
    ```html
    <style>
        @supports (display: grid) {
            .box { display: grid; }
        }
    </style>
    <div class="box">Grid</div>
    ```

17. **Write a function to measure CSS rendering time.**  
    Logs style application time.  
    ```html
    <div id="test">Content</div>
    <script>
    function measureCSSRender() {
        const start = performance.now();
        document.getElementById('test').style.background = 'blue';
        return performance.now() - start;
    }
    console.log(measureCSSRender());
    </script>
    ```

18. **How do you use CSS combinators?**  
    Targets elements based on relationships.  
    ```html
    <style>
        div > p { color: blue; } /* Direct child */
        div + p { color: red; } /* Adjacent sibling */
    </style>
    <div>
        <p>Blue</p>
    </div>
    <p>Red</p>
    ```

## Box Model and Layouts

### Basic
19. **What is the CSS box model?**  
   Defines element dimensions (content, padding, border, margin).  
   ```html
   <style>
       .box {
           width: 100px;
           padding: 10px;
           border: 5px solid black;
           margin: 15px;
       }
   </style>
   <div class="box">Box</div>
   ```

20. **How do you set element dimensions?**  
   Uses `width` and `height`.  
   ```html
   <style>
       .box { width: 200px; height: 100px; background: blue; }
   </style>
   <div class="box"></div>
   ```

21. **What is the difference between `margin` and `padding`?**  
   Margin is outside, padding is inside.  
   ```html
   <style>
       .box { margin: 20px; padding: 10px; border: 1px solid; }
   </style>
   <div class="box">Content</div>
   ```

22. **How do you use `box-sizing`?**  
   Controls box model calculations.  
   ```html
   <style>
       .box { box-sizing: border-box; width: 100px; padding: 10px; border: 5px solid; }
   </style>
   <div class="box">Box</div>
   ```

23. **What is the `display` property?**  
   Defines element rendering.  
   ```html
   <style>
       .inline { display: inline; }
       .block { display: block; }
   </style>
   <span class="inline">Inline</span>
   <div class="block">Block</div>
   ```

24. **How do you visualize box model metrics?**  
   Plots element dimensions.  
   ```python
   import matplotlib.pyplot as plt
   def plot_box_model(sizes):
       plt.plot(sizes, label='Dimensions')
       plt.title('Box Model Metrics')
       plt.savefig('box_model_metrics.png')
   ```

#### Intermediate
25. **Write a function to adjust box model dynamically.**  
   Modifies padding and margin.  
   ```html
   <div id="box" class="box">Content</div>
   <style>
       .box { padding: 10px; margin: 10px; }
   </style>
   <script>
   function adjustBoxModel(elementId, padding, margin) {
       const box = document.getElementById(elementId);
       box.style.padding = padding + 'px';
       box.style.margin = margin + 'px';
   }
   adjustBoxModel('box', 20, 20);
   </script>
   ```

26. **How do you use `position` property?**  
   Controls element positioning.  
   ```html
   <style>
       .absolute { position: absolute; top: 10px; left: 10px; }
       .relative { position: relative; top: 20px; }
   </style>
   <div class="absolute">Absolute</div>
   <div class="relative">Relative</div>
   ```

27. **Write a function to center an element.**  
   Uses margin or flexbox.  
   ```html
   <div id="center" class="box">Centered</div>
   <style>
       .box { width: 100px; }
   </style>
   <script>
   function centerElement(elementId) {
       const element = document.getElementById(elementId);
       element.style.margin = 'auto';
       element.parentElement.style.display = 'flex';
       element.parentElement.style.justifyContent = 'center';
   }
   centerElement('center');
   </script>
   ```

28. **How do you use `float` for layouts?**  
   Aligns elements horizontally.  
   ```html
   <style>
       .float { float: left; width: 50%; }
       .clear { clear: both; }
   </style>
   <div class="float">Left</div>
   <div class="float">Right</div>
   <div class="clear"></div>
   ```

29. **Write a function to calculate element dimensions.**  
   Gets computed size.  
   ```html
   <div id="dim" style="width: 100px; padding: 10px;"></div>
   <script>
   function getDimensions(elementId) {
       const element = document.getElementById(elementId);
       const styles = window.getComputedStyle(element);
       return {
           width: parseFloat(styles.width) + parseFloat(styles.paddingLeft) + parseFloat(styles.paddingRight),
           height: parseFloat(styles.height) + parseFloat(styles.paddingTop) + parseFloat(styles.paddingBottom)
       };
   }
   console.log(getDimensions('dim'));
   </script>
   ```

30. **How do you use `z-index`?**  
   Controls stacking order.  
   ```html
   <style>
       .front { position: absolute; z-index: 10; background: blue; }
       .back { position: absolute; z-index: 5; background: red; }
   </style>
   <div class="front">Front</div>
   <div class="back">Back</div>
   ```

#### Advanced
31. **Write a function to enforce box model consistency.**  
   Standardizes dimensions.  
   ```html
   <div id="consistent" class="box">Box</div>
   <script>
   function enforceBoxModel(elementId, props) {
       const element = document.getElementById(elementId);
       Object.entries(props).forEach(([key, value]) => {
           element.style[key] = value;
       });
   }
   enforceBoxModel('consistent', { boxSizing: 'border-box', width: '100px', padding: '10px' });
   </script>
   ```

32. **How do you optimize box model rendering?**  
   Minimizes reflows.  
   ```html
   <style>
       .optimized { will-change: transform; }
   </style>
   <div class="optimized">Content</div>
   ```

33. **Write a function to audit box model properties.**  
   Checks for consistency.  
   ```html
   <div id="audit" style="box-sizing: border-box;"></div>
   <script>
   function auditBoxModel(elementId) {
       const element = document.getElementById(elementId);
       const styles = window.getComputedStyle(element);
       return styles.boxSizing === 'border-box' ? 'Compliant' : 'Non-compliant';
   }
   console.log(auditBoxModel('audit'));
   </script>
   ```

34. **How do you handle overlapping elements?**  
   Uses `position` and `z-index`.  
   ```html
   <style>
       .overlap1 { position: absolute; z-index: 2; background: blue; }
       .overlap2 { position: absolute; z-index: 1; background: red; }
   </style>
   <div class="overlap1">Top</div>
   <div class="overlap2">Bottom</div>
   ```

35. **Write a function to adjust layout dynamically.**  
   Modifies position.  
   ```html
   <div id="layout" style="position: absolute;">Box</div>
   <script>
   function adjustLayout(elementId, top, left) {
       const element = document.getElementById(elementId);
       element.style.top = top + 'px';
       element.style.left = left + 'px';
   }
   adjustLayout('layout', 50, 50);
   </script>
   ```

36. **How do you use CSS for sticky positioning?**  
   Keeps elements in view.  
   ```html
   <style>
       .sticky { position: sticky; top: 0; background: #f0f0f0; }
   </style>
   <div class="sticky">Sticky Header</div>
   <div>Content</div>
   ```

## Flexbox and Grid

### Basic
37. **What is Flexbox, and how is it used?**  
   Creates flexible layouts.  
   ```html
   <style>
       .flex { display: flex; gap: 10px; }
       .item { background: blue; }
   </style>
   <div class="flex">
       <div class="item">1</div>
       <div class="item">2</div>
   </div>
   ```

38. **How do you create a CSS Grid layout?**  
   Defines grid structure.  
   ```html
   <style>
       .grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
       .item { background: red; }
   </style>
   <div class="grid">
       <div class="item">1</div>
       <div class="item">2</div>
   </div>
   ```

39. **What is the `justify-content` property in Flexbox?**  
   Aligns items horizontally.  
   ```html
   <style>
       .flex { display: flex; justify-content: space-between; }
   </style>
   <div class="flex">
       <div>Left</div>
       <div>Right</div>
   </div>
   ```

40. **How do you use `align-items` in Flexbox?**  
   Aligns items vertically.  
   ```html
   <style>
       .flex { display: flex; align-items: center; height: 100px; }
   </style>
   <div class="flex">
       <div>Centered</div>
   </div>
   ```

41. **What is the `grid-template-areas` property?**  
   Defines named grid areas.  
   ```html
   <style>
       .grid {
           display: grid;
           grid-template-areas: "header header" "main sidebar";
       }
       .header { grid-area: header; }
       .main { grid-area: main; }
       .sidebar { grid-area: sidebar; }
   </style>
   <div class="grid">
       <div class="header">Header</div>
       <div class="main">Main</div>
       <div class="sidebar">Sidebar</div>
   </div>
   ```

42. **How do you visualize Flexbox layouts?**  
   Plots item alignment.  
   ```python
   import matplotlib.pyplot as plt
   def plot_flexbox_layout():
       plt.scatter([1, 2, 3], [1, 1, 1], label='Flex Items')
       plt.title('Flexbox Layout')
       plt.savefig('flexbox_layout.png')
   ```

#### Intermediate
43. **Write a function to toggle Flexbox properties.**  
   Changes flex properties dynamically.  
   ```html
   <div id="flex" class="flex">
       <div>1</div>
       <div>2</div>
   </div>
   <style>
       .flex { display: flex; }
   </style>
   <script>
   function toggleFlexProperty(elementId, property, value) {
       document.getElementById(elementId).style[property] = value;
   }
   toggleFlexProperty('flex', 'justifyContent', 'center');
   </script>
   ```

44. **How do you create a responsive Grid layout?**  
   Uses `auto-fit` and `minmax`.  
   ```html
   <style>
       .grid {
           display: grid;
           grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
           gap: 10px;
       }
       .item { background: blue; }
   </style>
   <div class="grid">
       <div class="item">1</div>
       <div class="item">2</div>
   </div>
   ```

45. **Write a function to adjust Grid columns.**  
   Modifies grid template.  
   ```html
   <div id="grid" class="grid">
       <div>1</div>
       <div>2</div>
   </div>
   <style>
       .grid { display: grid; }
   </style>
   <script>
   function adjustGridColumns(elementId, columns) {
       document.getElementById(elementId).style.gridTemplateColumns = columns;
   }
   adjustGridColumns('grid', 'repeat(3, 1fr)');
   </script>
   ```

46. **How do you use `flex-grow` and `flex-shrink`?**  
   Controls item scaling.  
   ```html
   <style>
       .flex { display: flex; }
       .grow { flex-grow: 1; }
       .shrink { flex-shrink: 0; }
   </style>
   <div class="flex">
       <div class="grow">Grow</div>
       <div class="shrink">Shrink</div>
   </div>
   ```

47. **Write a function to reorder Flexbox items.**  
   Changes `order` property.  
   ```html
   <div id="flex" class="flex">
       <div class="item">1</div>
       <div class="item">2</div>
   </div>
   <style>
       .flex { display: flex; }
       .item { order: 0; }
   </style>
   <script>
   function reorderFlexItems(elementId, index, order) {
       document.getElementById(elementId).children[index].style.order = order;
   }
   reorderFlexItems('flex', 1, 1);
   </script>
   ```

48. **How do you use `grid-auto-flow`?**  
   Controls item placement.  
   ```html
   <style>
       .grid { display: grid; grid-auto-flow: dense; gap: 10px; }
       .item { background: blue; }
   </style>
   <div class="grid">
       <div class="item">1</div>
       <div class="item">2</div>
   </div>
   ```

#### Advanced
49. **Write a function to create a dynamic Grid dashboard.**  
   Generates grid layout.  
   ```html
   <div id="dashboard" class="grid"></div>
   <style>
       .grid { display: grid; }
   </style>
   <script>
   function createGridDashboard(elementId, items) {
       const grid = document.getElementById(elementId);
       grid.style.gridTemplateColumns = 'repeat(auto-fit, minmax(200px, 1fr))';
       items.forEach(item => {
           const div = document.createElement('div');
           div.textContent = item;
           div.style.background = 'blue';
           grid.appendChild(div);
       });
   }
   createGridDashboard('dashboard', ['Metric 1', 'Metric 2']);
   </script>
   ```

50. **How do you optimize Flexbox for performance?**  
   Minimizes layout recalculations.  
   ```html
   <style>
       .flex { display: flex; contain: layout; }
   </style>
   <div class="flex">
       <div>1</div>
       <div>2</div>
   </div>
   ```

51. **Write a function to audit Grid layouts.**  
   Checks grid properties.  
   ```html
   <div id="grid" style="display: grid;"></div>
   <script>
   function auditGridLayout(elementId) {
       const styles = window.getComputedStyle(document.getElementById(elementId));
       return styles.display === 'grid' ? 'Valid' : 'Invalid';
   }
   console.log(auditGridLayout('grid'));
   </script>
   ```

52. **How do you combine Flexbox and Grid?**  
   Uses nested layouts.  
   ```html
   <style>
       .container { display: grid; grid-template-columns: 1fr 1fr; }
       .flex { display: flex; justify-content: center; }
   </style>
   <div class="container">
       <div class="flex">Flex Item</div>
       <div>Grid Item</div>
   </div>
   ```

53. **Write a function to monitor Flexbox performance.**  
   Logs layout rendering time.  
   ```html
   <div id="flex" class="flex">
       <div>1</div>
       <div>2</div>
   </div>
   <style>
       .flex { display: flex; }
   </style>
   <script>
   function monitorFlexRender() {
       const start = performance.now();
       document.getElementById('flex').style.justifyContent = 'space-between';
       return performance.now() - start;
   }
   console.log(monitorFlexRender());
   </script>
   ```

54. **How do you create a masonry layout with Grid?**  
   Uses `grid-auto-flow`.  
   ```html
   <style>
       .masonry {
           display: grid;
           grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
           grid-auto-flow: dense;
       }
       .item:nth-child(odd) { grid-row: span 2; }
   </style>
   <div class="masonry">
       <div class="item">1</div>
       <div class="item">2</div>
   </div>
   ```

## Animations and Transitions

### Basic
55. **What is a CSS transition?**  
   Smoothly changes property values.  
   ```html
   <style>
       .box { width: 100px; transition: width 0.3s; }
       .box:hover { width: 200px; }
   </style>
   <div class="box"></div>
   ```

56. **How do you create a CSS animation?**  
   Uses `@keyframes`.  
   ```html
   <style>
       @keyframes slide {
           from { transform: translateX(0); }
           to { transform: translateX(100px); }
       }
       .box { animation: slide 2s infinite; }
   </style>
   <div class="box"></div>
   ```

57. **What is the `transition-property`?**  
   Specifies properties to transition.  
   ```html
   <style>
       .box { transition-property: background-color; transition-duration: 0.3s; }
       .box:hover { background-color: blue; }
   </style>
   <div class="box"></div>
   ```

58. **How do you use `animation-delay`?**  
   Delays animation start.  
   ```html
   <style>
       @keyframes fade { to { opacity: 0; } }
       .box { animation: fade 1s; animation-delay: 0.5s; }
   </style>
   <div class="box"></div>
   ```

59. **What is the `transform` property?**  
   Modifies element appearance.  
   ```html
   <style>
       .box { transform: rotate(45deg); }
   </style>
   <div class="box"></div>
   ```

60. **How do you visualize animation performance?**  
   Plots frame rates.  
   ```python
   import matplotlib.pyplot as plt
   def plot_animation_metrics(frames):
       plt.plot(frames, label='Frame Rate')
       plt.title('Animation Performance')
       plt.savefig('animation_metrics.png')
   ```

#### Intermediate
61. **Write a function to trigger CSS animations.**  
   Adds animation dynamically.  
   ```html
   <div id="anim" class="box"></div>
   <style>
       @keyframes move { to { transform: translateX(100px); } }
       .animate { animation: move 1s; }
   </style>
   <script>
   function triggerAnimation(elementId) {
       const element = document.getElementById(elementId);
       element.classList.add('animate');
   }
   triggerAnimation('anim');
   </script>
   ```

62. **How do you create a loading spinner?**  
   Uses `@keyframes` and `transform`.  
   ```html
   <style>
       .spinner {
           width: 40px;
           height: 40px;
           border: 5px solid #f3f3f3;
           border-top: 5px solid blue;
           border-radius: 50%;
           animation: spin 1s linear infinite;
       }
       @keyframes spin { to { transform: rotate(360deg); } }
   </style>
   <div class="spinner"></div>
   ```

63. **Write a function to pause animations.**  
   Controls animation state.  
   ```html
   <div id="anim" style="animation: slide 2s infinite;"></div>
   <style>
       @keyframes slide { to { transform: translateX(100px); } }
   </style>
   <script>
   function pauseAnimation(elementId) {
       document.getElementById(elementId).style.animationPlayState = 'paused';
   }
   pauseAnimation('anim');
   </script>
   ```

64. **How do you chain multiple transitions?**  
   Uses multiple properties.  
   ```html
   <style>
       .box {
           width: 100px;
           height: 100px;
           transition: width 0.3s, height 0.3s 0.3s;
       }
       .box:hover { width: 200px; height: 200px; }
   </style>
   <div class="box"></div>
   ```

65. **Write a function to create custom keyframes.**  
   Generates dynamic animations.  
   ```html
   <div id="custom"></div>
   <script>
   function createKeyframes(name, rules) {
       const style = document.createElement('style');
       style.textContent = `@keyframes ${name} { ${rules} }`;
       document.head.appendChild(style);
       document.getElementById('custom').style.animation = `${name} 1s`;
   }
   createKeyframes('customAnim', 'to { transform: scale(1.5); }');
   </script>
   ```

66. **How do you use `will-change` for animations?**  
   Optimizes rendering.  
   ```html
   <style>
       .box { will-change: transform; transition: transform 0.3s; }
       .box:hover { transform: scale(1.2); }
   </style>
   <div class="box"></div>
   ```

#### Advanced
67. **Write a function to animate ML visualizations.**  
   Animates chart updates.  
   ```html
   <div id="chart" class="chart"></div>
   <style>
       @keyframes grow { to { height: 100px; } }
       .chart { height: 50px; background: blue; }
   </style>
   <script>
   function animateChart(elementId, data) {
       const chart = document.getElementById(elementId);
       chart.style.animation = 'grow 1s';
       chart.style.height = data + 'px';
   }
   animateChart('chart', 100);
   </script>
   ```

68. **How do you optimize CSS animations?**  
   Uses GPU-accelerated properties.  
   ```html
   <style>
       .box { transition: transform 0.3s; }
       .box:hover { transform: translateX(100px); }
   </style>
   <div class="box"></div>
   ```

69. **Write a function to synchronize animations.**  
   Coordinates multiple elements.  
   ```html
   <div id="box1" class="box"></div>
   <div id="box2" class="box"></div>
   <style>
       @keyframes move { to { transform: translateX(100px); } }
       .box { animation: move 1s; }
   </style>
   <script>
   function syncAnimations(ids) {
       ids.forEach(id => {
           const element = document.getElementById(id);
           element.style.animation = 'none';
           setTimeout(() => element.style.animation = 'move 1s', 0);
       });
   }
   syncAnimations(['box1', 'box2']);
   </script>
   ```

70. **How do you implement 3D transforms?**  
   Uses `perspective` and `transform`.  
   ```html
   <style>
       .container { perspective: 1000px; }
       .box { transform: rotateY(45deg); transition: transform 0.5s; }
       .box:hover { transform: rotateY(0deg); }
   </style>
   <div class="container">
       <div class="box">3D</div>
   </div>
   ```

71. **Write a function to monitor animation performance.**  
   Logs frame timing.  
   ```html
   <div id="anim" style="animation: slide 1s infinite;"></div>
   <style>
       @keyframes slide { to { transform: translateX(100px); } }
   </style>
   <script>
   function monitorAnimation() {
       let lastFrame = performance.now();
       function checkFrame() {
           const now = performance.now();
           console.log('Frame time:', now - lastFrame);
           lastFrame = now;
           requestAnimationFrame(checkFrame);
       }
       requestAnimationFrame(checkFrame);
   }
   monitorAnimation();
   </script>
   ```

72. **How do you create staggered animations?**  
   Uses `animation-delay`.  
   ```html
   <style>
       .item { animation: fade 1s; }
       .item:nth-child(1) { animation-delay: 0.1s; }
       .item:nth-child(2) { animation-delay: 0.2s; }
       @keyframes fade { to { opacity: 1; } }
   </style>
   <div class="item"></div>
   <div class="item"></div>
   ```

## Responsive Design

### Basic
73. **What is responsive design in CSS?**  
   Adapts layouts to screen sizes.  
   ```html
   <style>
       .box { width: 100%; max-width: 600px; }
   </style>
   <div class="box">Responsive</div>
   ```

74. **How do you use media queries?**  
   Applies styles based on conditions.  
   ```html
   <style>
       .box { background: blue; }
       @media (max-width: 600px) {
           .box { background: red; }
       }
   </style>
   <div class="box">Box</div>
   ```

75. **What is the `vw` and `vh` unit?**  
   Viewport-based units.  
   ```html
   <style>
       .box { width: 50vw; height: 50vh; background: blue; }
   </style>
   <div class="box"></div>
   ```

76. **How do you use `rem` and `em` units?**  
   Relative to font sizes.  
   ```html
   <style>
       html { font-size: 16px; }
       .rem { font-size: 2rem; } /* 32px */
       .em { font-size: 2em; } /* Relative to parent */
   </style>
   <div class="rem">REM</div>
   <div style="font-size: 20px;"><div class="em">EM</div></div>
   ```

77. **What is the `meta` viewport tag?**  
   Controls mobile scaling.  
   ```html
   <head>
       <meta name="viewport" content="width=device-width, initial-scale=1">
   </head>
   ```

78. **How do you visualize responsive breakpoints?**  
   Plots screen size distribution.  
   ```python
   import matplotlib.pyplot as plt
   def plot_breakpoints(sizes):
       plt.hist(sizes, bins=10, label='Screen Sizes')
       plt.title('Responsive Breakpoints')
       plt.savefig('breakpoints.png')
   ```

#### Intermediate
79. **Write a function to toggle responsive classes.**  
   Adds classes based on screen size.  
   ```html
   <div id="responsive" class="box"></div>
   <style>
       .mobile { font-size: 14px; }
   </style>
   <script>
   function toggleResponsiveClass(elementId) {
       const element = document.getElementById(elementId);
       if (window.innerWidth < 600) {
           element.classList.add('mobile');
       } else {
           element.classList.remove('mobile');
       }
   }
   window.addEventListener('resize', () => toggleResponsiveClass('responsive'));
   </script>
   ```

80. **How do you create a mobile-first design?**  
   Starts with base styles.  
   ```html
   <style>
       .box { width: 100%; }
       @media (min-width: 768px) {
           .box { width: 50%; }
       }
   </style>
   <div class="box">Mobile-first</div>
   ```

81. **Write a function to adjust styles for breakpoints.**  
   Modifies styles dynamically.  
   ```html
   <div id="break" class="box"></div>
   <style>
       .box { background: blue; }
   </style>
   <script>
   function adjustForBreakpoint(elementId) {
       const element = document.getElementById(elementId);
       element.style.background = window.innerWidth < 600 ? 'red' : 'blue';
   }
   window.addEventListener('resize', () => adjustForBreakpoint('break'));
   </script>
   ```

82. **How do you use `clamp()` for responsive sizing?**  
   Sets flexible values.  
   ```html
   <style>
       .box { font-size: clamp(16px, 2vw, 18px); }
   </style>
   <div class="box">Responsive Text</div>
   ```

83. **Write a function to test responsive layouts.**  
   Checks style changes.  
   ```html
   <div id="test" class="box"></div>
   <style>
       .box { background: blue; }
       @media (max-width: 600px) { .box { background: red; } }
   </style>
   <script>
   function testResponsive() {
       const element = document.getElementById('test');
       const bg = window.getComputedStyle(element).backgroundColor;
       return window.innerWidth < 600 ? bg === 'rgb(255, 0, 0)' : bg === 'rgb(0, 0, 255)';
   }
   console.log(testResponsive());
   </script>
   ```

84. **How do you use `aspect-ratio` for responsive media?**  
   Maintains proportions.  
   ```html
   <style>
       .media { aspect-ratio: 16 / 9; width: 100%; background: blue; }
   </style>
   <div class="media"></div>
   ```

#### Advanced
85. **Write a function to generate responsive media queries.**  
   Creates dynamic queries.  
   ```html
   <script>
   function generateMediaQuery(minWidth, styles) {
       const style = document.createElement('style');
       style.textContent = `@media (min-width: ${minWidth}px) { ${styles} }`;
       document.head.appendChild(style);
   }
   generateMediaQuery(768, '.box { font-size: 20px; }');
   </script>
   <div class="box">Responsive</div>
   ```

86. **How do you optimize responsive images with CSS?**  
   Uses `object-fit`.  
   ```html
   <style>
       img { width: 100%; height: 200px; object-fit: cover; }
   </style>
   <img src="model.png" alt="Model">
   ```

87. **Write a function to monitor responsive performance.**  
   Logs layout shift time.  
   ```html
   <div id="responsive"></div>
   <script>
   function monitorResponsive() {
       const start = performance.now();
       document.getElementById('responsive').style.width = window.innerWidth < 600 ? '100%' : '50%';
       return performance.now() - start;
   }
   window.addEventListener('resize', () => console.log(monitorResponsive()));
   </script>
   ```

88. **How do you implement fluid typography?**  
   Uses `vw` and `clamp`.  
   ```html
   <style>
       .text { font-size: clamp(16px, 2.5vw, 20px); }
   </style>
   <div class="text">Fluid Text</div>
   ```

89. **Write a function to audit responsive compliance.**  
   Checks media query application.  
   ```html
   <div id="audit" class="box"></div>
   <style>
       .box { background: blue; }
       @media (max-width: 600px) { .box { background: red; } }
   </style>
   <script>
   function auditResponsive() {
       const styles = window.getComputedStyle(document.getElementById('audit'));
       return window.innerWidth < 600 ? styles.backgroundColor === 'rgb(255, 0, 0)' : 'Compliant';
   }
   console.log(auditResponsive());
   </script>
   ```

90. **How do you use container queries?**  
   Styles based on container size.  
   ```html
   <style>
       .container { container-type: inline-size; }
       @container (min-width: 300px) {
           .item { font-size: 20px; }
       }
   </style>
   <div class="container">
       <div class="item">Content</div>
   </div>
   ```

## CSS Preprocessors

### Basic
91. **What is a CSS preprocessor, and why use it?**  
   Extends CSS with variables, mixins.  
   ```scss
   $primary: blue;
   .box { background: $primary; }
   ```

92. **How do you use variables in SCSS?**  
   Defines reusable values.  
   ```scss
   $font-size: 16px;
   .text { font-size: $font-size; }
   ```

93. **What is a mixin in SCSS?**  
   Reusable style blocks.  
   ```scss
   @mixin border { border: 1px solid black; }
   .box { @include border; }
   ```

94. **How do you use nesting in SCSS?**  
   Organizes selectors.  
   ```scss
   .container {
       background: blue;
       .item { color: white; }
   }
   ```

95. **What is the `@extend` directive in SCSS?**  
   Inherits styles.  
   ```scss
   .base { color: blue; }
   .extended { @extend .base; font-size: 16px; }
   ```

96. **How do you visualize preprocessor usage?**  
   Plots variable usage.  
   ```python
   import matplotlib.pyplot as plt
   def plot_preprocessor_metrics(variables):
       plt.bar(range(len(variables)), variables, label='Variables')
       plt.title('Preprocessor Usage')
       plt.savefig('preprocessor_metrics.png')
   ```

#### Intermediate
97. **Write a function to generate SCSS variables.**  
   Creates dynamic variables.  
   ```html
   <style type="text/scss">
       $color: blue;
       .box { background: $color; }
   </style>
   <script>
   function generateSCSSVariable(name, value) {
       // Mock SCSS injection
       console.log(`$${name}: ${value};`);
   }
   generateSCSSVariable('color', 'red');
   </script>
   ```

98. **How do you use SCSS loops?**  
   Generates repetitive styles.  
   ```scss
   @for $i from 1 through 3 {
       .item-#{$i} { margin: $i * 10px; }
   }
   ```

99. **Write a function to compile SCSS (mock).**  
   Simulates SCSS processing.  
   ```html
   <script>
   function compileSCSS(code) {
       // Mock: Replace SCSS variable
       return code.replace(/\$color: (\w+);/, 'background: $1;');
   }
   console.log(compileSCSS('$color: blue; .box { background: $color; }'));
   </script>
   ```

100. **How do you use SCSS functions?**  
    Creates custom logic.  
    ```scss
    @function double($size) { @return $size * 2; }
    .box { width: double(50px); }
    ```

101. **Write a function to manage SCSS mixins.**  
     Applies reusable styles.  
     ```html
     <style type="text/scss">
         @mixin border { border: 1px solid; }
         .box { @include border; }
     </style>
     <script>
     function applyMixin(mixinName) {
         // Mock mixin application
         console.log(`Applying mixin: ${mixinName}`);
     }
     applyMixin('border');
     </script>
     ```

102. **How do you use SCSS imports?**  
     Combines multiple files.  
     ```scss
     @import 'variables';
     .box { background: $primary; }
     ```

#### Advanced
103. **Write a function to optimize SCSS output.**  
     Minifies compiled CSS.  
     ```html
     <script>
     function optimizeSCSS(css) {
         return css.replace(/\s+/g, ' ').replace(/; /g, ';');
     }
     console.log(optimizeSCSS('.box { background: blue; margin: 10px; }'));
     </script>
     ```

104. **How do you modularize SCSS code?**  
     Uses partials and imports.  
     ```scss
     // _base.scss
     $primary: blue;
     // main.scss
     @import 'base';
     .box { background: $primary; }
     ```

105. **Write a function to audit SCSS variables.**  
     Checks variable usage.  
     ```html
     <script>
     function auditSCSSVariables(code) {
         const variables = code.match(/\$[\w-]+/g) || [];
         return variables.length > 0 ? 'Variables found' : 'No variables';
     }
     console.log(auditSCSSVariables('$color: blue; .box { background: $color; }'));
     </script>
     ```

106. **How do you integrate SCSS with build tools?**  
     Uses Webpack (mock).  
     ```html
     <script>
     function mockSCSSBuild() {
         console.log('Compiling SCSS with Webpack...');
     }
     mockSCSSBuild();
     </script>
     ```

107. **Write a function to generate SCSS mixins dynamically.**  
     Creates reusable styles.  
     ```html
     <script>
     function generateSCSSMixin(name, properties) {
         const rules = Object.entries(properties).map(([k, v]) => `${k}: ${v};`).join(' ');
         console.log(`@mixin ${name} { ${rules} }`);
     }
     generateSCSSMixin('bordered', { border: '1px solid', padding: '10px' });
     </script>
     ```

108. **How do you use SCSS for theming?**  
     Defines theme variables.  
     ```scss
     $theme: (
         light: (bg: white, text: black),
         dark: (bg: black, text: white)
     );
     .light { background: map-get(map-get($theme, light), bg); }
     ```

## Performance Optimization

### Basic
109. **How do you optimize CSS file size?**  
     Minifies CSS.  
     ```html
     <!-- Before -->
     <style>
         .box { background: blue; margin: 10px; }
     </style>
     <!-- After -->
     <style>.box{background:blue;margin:10px}</style>
     ```

110. **What is critical CSS?**  
     Prioritizes above-the-fold styles.  
     ```html
     <style>
         .hero { font-size: 24px; }
     </style>
     <div class="hero">Dashboard</div>
     ```

111. **How do you reduce CSS reflows?**  
     Uses transform for animations.  
     ```html
     <style>
         .box { transition: transform 0.3s; }
         .box:hover { transform: translateX(10px); }
     </style>
     <div class="box"></div>
     ```

112. **What is the `contain` property?**  
     Limits rendering scope.  
     ```html
     <style>
         .box { contain: layout; }
     </style>
     <div class="box">Content</div>
     ```

113. **How do you use `will-change` for performance?**  
     Prepares browser for changes.  
     ```html
     <style>
         .box { will-change: transform; }
     </style>
     <div class="box"></div>
     ```

114. **How do you visualize CSS performance?**  
     Plots rendering times.  
     ```python
     import matplotlib.pyplot as plt
     def plot_css_performance(times):
         plt.plot(times, label='Render Time')
         plt.title('CSS Performance')
         plt.savefig('css_performance.png')
     ```

#### Intermediate
115. **Write a function to remove unused CSS.**  
     Simulates CSS pruning.  
     ```html
     <style id="styles">
         .used { color: blue; }
         .unused { color: red; }
     </style>
     <div class="used">Content</div>
     <script>
     function removeUnusedCSS() {
         const styles = document.getElementById('styles').textContent;
         return styles.replace(/\.unused[^}]+}/, '');
     }
     console.log(removeUnusedCSS());
     </script>
     ```

116. **How do you optimize font loading with CSS?**  
     Uses `font-display`.  
     ```html
     <style>
         @font-face {
             font-family: 'Custom';
             src: url('font.woff2');
             font-display: swap;
         }
         .text { font-family: 'Custom'; }
     </style>
     <div class="text">Text</div>
     ```

117. **Write a function to measure CSS load time.**  
     Logs style application.  
     ```html
     <style id="test">.box { background: blue; }</style>
     <div class="box"></div>
     <script>
     function measureCSSLoad() {
         const start = performance.now();
         document.getElementById('test').textContent += '.box { color: red; }';
         return performance.now() - start;
     }
     console.log(measureCSSLoad());
     </script>
     ```

118. **How do you use CSS containment?**  
     Isolates rendering.  
     ```html
     <style>
         .container { contain: strict; }
     </style>
     <div class="container"><div>Content</div></div>
     ```

119. **Write a function to defer CSS loading.**  
     Loads non-critical CSS dynamically.  
     ```html
     <script>
     function deferCSS(url) {
         const link = document.createElement('link');
         link.rel = 'stylesheet';
         link.href = url;
         document.head.appendChild(link);
     }
     deferCSS('non-critical.css');
     </script>
     ```

120. **How do you optimize CSS for GPU rendering?**  
     Uses transform and opacity.  
     ```html
     <style>
         .box { transition: transform 0.3s, opacity 0.3s; }
         .box:hover { transform: scale(1.1); opacity: 0.8; }
     </style>
     <div class="box"></div>
     ```

#### Advanced
121. **Write a function to implement CSS code splitting.**  
     Loads styles dynamically.  
     ```html
     <script>
     function loadCSSModule(url) {
         const link = document.createElement('link');
         link.rel = 'stylesheet';
         link.href = url;
         document.head.appendChild(link);
     }
     loadCSSModule('module.css');
     </script>
     ```

122. **How do you minimize CSS parse time?**  
     Reduces selector complexity.  
     ```html
     <style>
         /* Complex */
         div > ul > li > a { color: blue; }
         /* Simple */
         .link { color: blue; }
     </style>
     <a class="link">Link</a>
     ```

123. **Write a function to monitor CSS rendering performance.**  
     Logs style application time.  
     ```html
     <div id="perf"></div>
     <script>
     function monitorCSSPerf() {
         const start = performance.now();
         document.getElementById('perf').style.background = 'blue';
         return performance.now() - start;
     }
     console.log(monitorCSSPerf());
     </script>
     ```

124. **How do you implement progressive CSS loading?**  
     Loads critical CSS first.  
     ```html
     <style>
         .critical { font-size: 16px; }
     </style>
     <link rel="stylesheet" href="non-critical.css">
     ```

125. **Write a function to reduce CSS repaint costs.**  
     Minimizes style changes.  
     ```html
     <div id="repaint"></div>
     <script>
     function optimizeRepaint(elementId, styles) {
         const element = document.getElementById(elementId);
         requestAnimationFrame(() => Object.assign(element.style, styles));
     }
     optimizeRepaint('repaint', { transform: 'translateX(10px)' });
     </script>
     ```

126. **How do you use CSS custom properties for performance?**  
     Reduces redundant rules.  
     ```html
     <style>
         :root { --color: blue; }
         .box { background: var(--color); }
         .text { color: var(--color); }
     </style>
     <div class="box"></div>
     <div class="text">Text</div>
     ```

## Integration with AI/ML

### Basic
127. **How do you style ML model outputs in CSS?**  
     Styles prediction displays.  
     ```html
     <style>
         .prediction {
             background: #f0f0f0;
             padding: 10px;
             border-radius: 5px;
         }
     </style>
     <div class="prediction">Prediction: 0.95</div>
     ```

128. **How do you create a dashboard layout for ML metrics?**  
     Uses Grid for layout.  
     ```html
     <style>
         .dashboard {
             display: grid;
             grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
             gap: 10px;
         }
         .metric { background: blue; color: white; padding: 10px; }
     </style>
     <div class="dashboard">
         <div class="metric">Accuracy: 95%</div>
         <div class="metric">Loss: 0.1</div>
     </div>
     ```

129. **How do you style interactive ML interfaces?**  
     Uses hover effects.  
     ```html
     <style>
         .button { transition: background 0.3s; }
         .button:hover { background: blue; color: white; }
     </style>
     <button class="button">Run Model</button>
     ```

130. **How do you use CSS to style TensorFlow.js outputs?**  
     Formats model results.  
     ```html
     <style>
         .output { font-size: 18px; border: 1px solid; padding: 10px; }
     </style>
     <div class="output" id="tf-output"></div>
     <script src="https://cdn.jsdelivr.net/npm/@tensorflow/tfjs"></script>
     <script>
     document.getElementById('tf-output').textContent = 'Model Output';
     </script>
     ```

131. **How do you style data visualizations in CSS?**  
     Enhances chart appearance.  
     ```html
     <style>
         .chart { border: 1px solid; padding: 10px; background: #f9f9f9; }
     </style>
     <canvas class="chart" id="data-vis"></canvas>
     ```

132. **How do you visualize ML styling metrics?**  
     Plots style application times.  
     ```python
     import matplotlib.pyplot as plt
     def plot_ml_styling_metrics(times):
         plt.plot(times, label='Style Time')
         plt.title('ML Styling Performance')
         plt.savefig('ml_styling_metrics.png')
     ```

#### Intermediate
133. **Write a function to style ML predictions dynamically.**  
     Updates styles based on data.  
     ```html
     <div id="ml-pred" class="prediction"></div>
     <style>
         .prediction { padding: 10px; }
     </style>
     <script>
     function stylePrediction(elementId, value) {
         const element = document.getElementById(elementId);
         element.style.background = value > 0.5 ? 'green' : 'red';
         element.textContent = `Prediction: ${value}`;
     }
     stylePrediction('ml-pred', 0.75);
     </script>
     ```

134. **How do you create a responsive ML dashboard?**  
     Uses media queries and Grid.  
     ```html
     <style>
         .dashboard {
             display: grid;
             grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
         }
         @media (max-width: 600px) {
             .dashboard { grid-template-columns: 1fr; }
         }
         .metric { background: blue; }
     </style>
     <div class="dashboard">
         <div class="metric">Metric</div>
     </div>
     ```

135. **Write a function to animate ML visualizations.**  
     Animates metric updates.  
     ```html
     <div id="metric" class="metric"></div>
     <style>
         @keyframes pulse { to { transform: scale(1.1); } }
         .metric { background: blue; }
     </style>
     <script>
     function animateMetric(elementId) {
         const element = document.getElementById(elementId);
         element.style.animation = 'pulse 1s infinite';
     }
     animateMetric('metric');
     </script>
     ```

136. **How do you style real-time ML outputs?**  
     Uses transitions for updates.  
     ```html
     <style>
         .realtime {
             transition: opacity 0.5s;
             opacity: 1;
         }
         .realtime.updated { opacity: 0.5; }
     </style>
     <div class="realtime">Data: 0.95</div>
     ```

137. **Write a function to apply SCSS for ML interfaces.**  
     Generates SCSS styles.  
     ```html
     <script>
     function generateSCSSForML(metric) {
         console.log(`
             $color: ${metric > 0.5 ? 'green' : 'red'};
             .metric { background: $color; }
         `);
     }
     generateSCSSForML(0.75);
     </script>
     ```

138. **How do you use CSS to style ML model controls?**  
     Enhances form elements.  
     ```html
     <style>
         .control { padding: 10px; border-radius: 5px; transition: background 0.3s; }
         .control:hover { background: #e0e0e0; }
     </style>
     <input class="control" type="number" placeholder="Epochs">
     ```

#### Advanced
139. **Write a function to optimize ML dashboard styles.**  
     Reduces CSS overhead.  
     ```html
     <style id="dashboard">
         .metric { background: blue; padding: 10px; }
     </style>
     <script>
     function optimizeDashboardCSS() {
         const style = document.getElementById('dashboard').textContent;
         return style.replace(/\s+/g, ' ');
     }
     console.log(optimizeDashboardCSS());
     </script>
     ```

140. **How do you style ML model outputs for accessibility?**  
     Uses high-contrast colors.  
     ```html
     <style>
         .output {
             background: #000;
             color: #fff;
             padding: 10px;
             font-size: 18px;
         }
     </style>
     <div class="output">Accuracy: 95%</div>
     ```

141. **Write a function to style streaming ML data.**  
     Updates styles dynamically.  
     ```html
     <div id="stream" class="stream"></div>
     <style>
         .stream { transition: background 0.5s; }
     </style>
     <script>
     function styleStreamData(elementId, value) {
         const element = document.getElementById(elementId);
         element.style.background = value > 0 ? 'green' : 'red';
         element.textContent = `Data: ${value}`;
     }
     styleStreamData('stream', 0.8);
     </script>
     ```

142. **How do you optimize CSS for ML visualizations?**  
     Uses GPU-accelerated styles.  
     ```html
     <style>
         .chart { transform: translateZ(0); transition: transform 0.3s; }
         .chart:hover { transform: scale(1.1); }
     </style>
     <div class="chart"></div>
     ```

143. **Write a function to monitor ML styling performance.**  
     Logs style application time.  
     ```html
     <div id="ml-style"></div>
     <script>
     function monitorMLStyling() {
         const start = performance.now();
         document.getElementById('ml-style').style.background = 'blue';
         return performance.now() - start;
     }
     console.log(monitorMLStyling());
     </script>
     ```

144. **How do you use CSS custom properties for ML theming?**  
     Defines dynamic themes.  
     ```html
     <style>
         :root { --metric-color: blue; }
         .metric { background: var(--metric-color); }
     </style>
     <div class="metric">Metric</div>
     ```

## Security

### Basic
145. **How do you prevent CSS-based attacks?**  
     Sanitizes user-generated styles.  
     ```html
     <style>
         .safe { color: blue; }
     </style>
     <div class="safe">Safe</div>
     ```

146. **What is CSS injection, and how do you prevent it?**  
     Validates dynamic CSS.  
     ```html
     <script>
     function safeCSS(property, value) {
         const valid = /^[a-z-]+$/i.test(property) && /^[a-z0-9#]+$/i.test(value);
         return valid ? `${property}: ${value};` : '';
     }
     console.log(safeCSS('color', 'blue')); // color: blue;
     </script>
     ```

147. **How do you secure CSS for user inputs?**  
     Limits style scope.  
     ```html
     <style>
         .user-input { contain: style; }
     </style>
     <div class="user-input">User Data</div>
     ```

148. **What is the `isolation` property?**  
     Isolates element rendering.  
     ```html
     <style>
         .isolated { isolation: isolate; }
     </style>
     <div class="isolated">Isolated</div>
     ```

149. **How do you use Content Security Policy with CSS?**  
     Restricts style sources.  
     ```html
     <meta http-equiv="Content-Security-Policy" content="style-src 'self'">
     ```

150. **How do you visualize security metrics for CSS?**  
     Plots injection attempts.  
     ```python
     import matplotlib.pyplot as plt
     def plot_css_security_metrics(attempts):
         plt.plot(attempts, label='Injection Attempts')
         plt.title('CSS Security Metrics')
         plt.savefig('css_security_metrics.png')
     ```

#### Intermediate
151. **Write a function to sanitize CSS inputs.**  
     Prevents malicious styles.  
     ```html
     <script>
     function sanitizeCSS(property, value) {
         const allowed = ['color', 'background', 'font-size'];
         return allowed.includes(property) && /^[a-z0-9#]+$/i.test(value) ? `${property}: ${value};` : '';
     }
     console.log(sanitizeCSS('color', 'blue')); // color: blue;
     </script>
     ```

152. **How do you secure dynamic CSS?**  
     Uses safe properties.  
     ```html
     <style>
         .dynamic { color: var(--safe-color, blue); }
     </style>
     <div class="dynamic">Safe</div>
     ```

153. **Write a function to detect CSS injection.**  
     Monitors suspicious styles.  
     ```html
     <script>
     function detectCSSInjection(code) {
         return /expression|url\(/i.test(code) ? 'Injection detected' : 'Safe';
     }
     console.log(detectCSSInjection('color: expression(alert(1));')); // Injection detected
     </script>
     ```

154. **How do you limit CSS scope?**  
     Uses shadow DOM (mock).  
     ```html
     <style>
         .scoped { contain: style; }
     </style>
     <div class="scoped">Scoped</div>
     ```

155. **Write a function to log CSS security events.**  
     Tracks style changes.  
     ```html
     <style id="secure"></style>
     <script>
     function logCSSEvent(change) {
         console.log(`CSS change: ${change}`);
     }
     document.getElementById('secure').textContent = '.box { color: blue; }';
     logCSSEvent('Style updated');
     </script>
     ```

156. **How do you secure CSS animations?**  
     Limits animation properties.  
     ```html
     <style>
         .safe { animation: safeAnim 1s; }
         @keyframes safeAnim { to { transform: translateX(10px); } }
     </style>
     <div class="safe"></div>
     ```

#### Advanced
157. **Write a function to enforce CSS security policies.**  
     Applies safe styles.  
     ```html
     <script>
     function enforceCSSPolicy(styles) {
         const safe = styles.replace(/expression|url\(/gi, '');
         return safe;
     }
     console.log(enforceCSSPolicy('color: expression(alert(1));')); // color: ;
     </script>
     ```

158. **How do you secure CSS custom properties?**  
     Validates variable values.  
     ```html
     <style>
         :root { --safe-color: blue; }
         .box { background: var(--safe-color); }
     </style>
     <div class="box"></div>
     ```

159. **Write a function to monitor CSS injection attempts.**  
     Logs suspicious styles.  
     ```html
     <script>
     function monitorCSSInjection(code) {
         if (/[<>\"\';]/.test(code)) {
             console.log('Potential CSS injection');
         }
     }
     monitorCSSInjection('color: <script>alert(1)</script>');
     </script>
     ```

160. **How do you secure CSS in shadow DOM?**  
     Isolates styles.  
     ```html
     <script>
     const div = document.createElement('div');
     const shadow = div.attachShadow({ mode: 'closed' });
     const style = document.createElement('style');
     style.textContent = '.box { color: blue; }';
     shadow.appendChild(style);
     </script>
     ```

161. **Write a function to audit CSS security.**  
     Checks for unsafe properties.  
     ```html
     <script>
     function auditCSSSecurity(code) {
         return /expression|url\(/i.test(code) ? 'Unsafe' : 'Safe';
     }
     console.log(auditCSSSecurity('.box { background: url(malicious.js); }')); // Unsafe
     </script>
     ```

162. **How do you integrate CSS security with CSP?**  
     Restricts style sources dynamically.  
     ```html
     <meta http-equiv="Content-Security-Policy" content="style-src 'self' 'unsafe-inline'">
     ```

## Testing and Validation

### Basic
163. **How do you test CSS styles?**  
     Verifies applied styles.  
     ```html
     <div id="test" class="box"></div>
     <style>
         .box { color: blue; }
     </style>
     <script>
     function testCSS() {
         const styles = window.getComputedStyle(document.getElementById('test'));
         return styles.color === 'rgb(0, 0, 255)' ? 'Valid' : 'Invalid';
     }
     console.log(testCSS());
     </script>
     ```

164. **How do you validate CSS code?**  
     Uses CSS validator (mock).  
     ```html
     <style>
         .box { background: blue; }
     </style>
     <div class="box"></div>
     ```

165. **How do you test responsive CSS?**  
     Checks media query styles.  
     ```html
     <div id="responsive" class="box"></div>
     <style>
         .box { background: blue; }
         @media (max-width: 600px) { .box { background: red; } }
     </style>
     <script>
     function testResponsiveCSS() {
         const styles = window.getComputedStyle(document.getElementById('responsive'));
         return window.innerWidth < 600 ? styles.backgroundColor === 'rgb(255, 0, 0)' : 'Valid';
     }
     console.log(testResponsiveCSS());
     </script>
     ```

166. **How do you test CSS animations?**  
     Verifies animation application.  
     ```html
     <div id="anim" class="animated"></div>
     <style>
         .animated { animation: move 1s; }
         @keyframes move { to { transform: translateX(10px); } }
     </style>
     <script>
     function testAnimation() {
         const styles = window.getComputedStyle(document.getElementById('anim'));
         return styles.animationName === 'move' ? 'Valid' : 'Invalid';
     }
     console.log(testAnimation());
     </script>
     ```

167. **How do you mock CSS rendering for testing?**  
     Simulates style application.  
     ```html
     <script>
     function mockCSSRender(styles) {
         const div = document.createElement('div');
         div.style.cssText = styles;
         return div.style.cssText;
     }
     console.log(mockCSSRender('color: blue;'));
     </script>
     ```

168. **How do you visualize CSS test results?**  
     Plots test pass rates.  
     ```python
     import matplotlib.pyplot as plt
     def plot_css_test_results(passes):
         plt.plot(passes, label='Pass Rate')
         plt.title('CSS Test Results')
         plt.savefig('css_test_results.png')
     ```

#### Intermediate
169. **Write a function to test CSS specificity.**  
     Verifies selector priority.  
     ```html
     <div id="specific" class="box"></div>
     <style>
         .box { color: blue; }
         #specific { color: red; }
     </style>
     <script>
     function testSpecificity() {
         const styles = window.getComputedStyle(document.getElementById('specific'));
         return styles.color === 'rgb(255, 0, 0)' ? 'Valid' : 'Invalid';
     }
     console.log(testSpecificity());
     </script>
     ```

170. **How do you test CSS for accessibility?**  
     Checks contrast and font sizes.  
     ```html
     <div id="access" class="text"></div>
     <style>
         .text { color: #fff; background: #000; font-size: 16px; }
     </style>
     <script>
     function testAccessibility() {
         const styles = window.getComputedStyle(document.getElementById('access'));
         return parseFloat(styles.fontSize) >= 16 && styles.color === 'rgb(255, 255, 255)' ? 'Valid' : 'Invalid';
     }
     console.log(testAccessibility());
     </script>
     ```