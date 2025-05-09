nowrap (default) → All flex items stay in a single line, even if they overflow.
wrap → Flex items wrap onto the next line if they don’t fit.
wrap-reverse → Like wrap, but items wrap in the reverse direction.


%	Relative to the parent element

em	Relative to the font-size of the element (2em means 2 times the size of the current font)

rem	Relative to font-size of the root element




5. Common Mistakes and Misunderstandings:
Using margin: auto; without a specified width on the block element will not center it.

It only works for block-level elements (like div), not inline elements (like span).

It centers elements horizontally, not vertically. For vertical centering, you need other methods like Flexbox or Grid.


//

CSS has various units to define sizes (font size, padding, margin, etc.)
Two of the most important relative units are em and rem.

    
🚀 What is em in CSS?
Definition: em is a relative unit based on the size of the parent element's font.

Calculation: 1em = 100% of the parent element’s font size.

Use Cases: Ideal for responsive designs because it scales with parent size.

ex:
<!DOCTYPE html>
<html>
<head>
<style>
  body {
    font-size: 16px;
  }

  .parent {
    font-size: 20px;
  }

  .child {
    font-size: 2em; /* 2 times the parent's font size */
  }
</style>
</head>
<body>
  <div class="parent">
    Parent Text (Font Size: 20px)
    <div class="child">
      Child Text (Font Size: 40px - 2 times parent)
    </div>
  </div>
</body>
</html>

✅ Output Explanation:
The parent font size is set to 20px.

The child’s font size is set to 2em, making it 2 * 20px = 40px.


🚀 What is rem in CSS?
Definition: rem is a relative unit based on the size of the root (HTML) font.

Calculation: 1rem = 100% of the root element’s font size (<html>).

Use Cases: Consistent sizing across the website, easier to maintain.

Ex:
<!DOCTYPE html>
<html>
<head>
<style>
  html {
    font-size: 16px;
  }

  .element {
    font-size: 2rem; /* 2 times the root font size */
  }
</style>
</head>
<body>
  <div class="element">
    Text with 2rem size (Font Size: 32px)
  </div>
</body>
</html>

✅ Output Explanation:
The root font size (html) is set to 16px.

The element font size is 2rem, making it 2 * 16px = 32px.


🚀Key Differences Between em and rem
Aspect	       em	                                 rem
Based On	   Parent element font size	             Root (html) font size
Scaling	       Changes based on parent	             Consistent across the document
Usage	       Nested elements, modular designs	     Global sizing, consistent UI
Complexity	   Can become confusing when nested	     Simple, predictable


🚀When to Use em and rem?
Use rem for:

Global font sizes.

Padding/margin for a consistent layout.

Use em for:

Element-specific scaling (e.g., buttons, nested elements).


🚀Best Practices with em and rem:
Set the root (html) font size using rem for consistent scaling.

css:
html {
  font-size: 16px; /* Base size for all rem calculations */
}


Use rem for main elements (body, headings, buttons):

css:
h1 {
  font-size: 2rem; /* 32px (2 * 16px) */
}
Use em for nested elements where you want size to be relative to parent:

css:
.parent {
  font-size: 1.5rem; /* 24px */
}

.parent .child {
  font-size: 0.8em; /* 80% of parent (24px * 0.8 = 19.2px) */
}


🚀Advanced Tips:
To create a fully scalable UI, use a combination of rem for layout and em for elements within components.

Avoid excessive nesting with em to prevent confusing size calculations.