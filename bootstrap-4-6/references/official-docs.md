# Bootstrap 4.6 Official Reference

Use only these official Bootstrap 4.6 sources for framework-specific decisions:

- Main documentation: https://getbootstrap.com/docs/4.6/
- Starter template and CDN: https://getbootstrap.com/docs/4.6/getting-started/introduction/
- Package managers and distributed assets: https://getbootstrap.com/docs/4.6/getting-started/download/
- jQuery plugins and dependency rules: https://getbootstrap.com/docs/4.6/getting-started/javascript/
- Component and utility navigation: https://getbootstrap.com/docs/4.6/components/ and https://getbootstrap.com/docs/4.6/utilities/

## Verified 4.6.2 CDN

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.6.2/dist/css/bootstrap.min.css" integrity="sha384-xOolHFLEh07PJGoPkLv1IbcEPTNtaed2xpHsD9ESMhqIYd0nLMwNLD69Npy4HI+N" crossorigin="anonymous">

<script src="https://cdn.jsdelivr.net/npm/jquery@3.5.1/dist/jquery.slim.min.js" integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
<script src="https://cdn.jsdelivr.net/npm/bootstrap@4.6.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-Fy6S3B9q64WdZWQUiU+q4/2Lc9npb8tCaSX9FK7E8HnRr0Jz8D6OP9dO5Vg3Q9ct" crossorigin="anonymous"></script>
```

`bootstrap.bundle.min.js` includes Popper. All Bootstrap 4 JavaScript plugins require jQuery; dropdowns, popovers, and tooltips require Popper.

## Version Boundaries

- Keep Bootstrap 4 attributes: `data-toggle`, `data-target`, `data-dismiss`.
- Keep Bootstrap 4 layout and form classes. Do not replace them with v5-only syntax.
- Bootstrap 4.6 is end-of-life. Do not select it for a new project without an explicit compatibility requirement.
