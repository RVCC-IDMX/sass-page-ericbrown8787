# SASS File System

The SASS directory structure for this project is organized as follows:

```
scss/
├── abstracts/
│   ├── _functions.scss
│   ├── _mixins.scss
│   └── _variables.scss
├── base/
│   ├── _reset.scss
│   └── _typography.scss
├── components/
│   └── _header.scss
├── pages/
│   └── _home.scss
├── main.scss
└── README.md
```

The intended purposes of each file and folder are outlined below. Files prefixed with an underscore "\_" will not be directly compiled into CSS by SASS.

## scss/

This is the main directory containing all of the project's SASS code.

- ### main.scss

  This file contains links to the reset stylesheet and stylesheets for individual pages, and is the stylesheet directly linked to in the head of each page. This file should only contain @use rules.

- ### utilities/

  This folder contains config files and any code that is likely to be referenced and reused in other parts of the project in order to reduce repetition and make changing properties that appear in more than one place easier. they can be imported to a stylesheet using the `@use "../abstracts/file-name"` syntax.

  - #### \_functions.scss

    This file contains function declarations. In SASS, functions are reusable sets of instructions for complex behavior that may be referenced in other stylesheets using the `func.function-name(arguments)` syntax after being imported.

  - #### \_variables.scss

    This file contains general variable declarations. Variables should be values that may be reused in multiple areas of the stylesheet, such as theme colors and borders. They can be referenced as property values using the `$variable-name` syntax.

  - #### \_mixins.scss
    This file contains mixins, which are groups of CSS declarations that may be referenced throughout the project for different elements using the `@include mixins.mixin-name` rule.

- ### base/

  This folder contains global styles that are applied to every page before more specific styles.

  - #### \_reset.scss

    This is a global reset applied for consistency of behavior.

  - #### \_typography.scss

    This file contains typography-related styling variables, and can contain `@use` and `@font-face` rules for fonts if applicable

- ### components/

  This folder contains stylesheets for self-contained, reusable components such as headers, cards, buttons and navbars. Each component should have its own file, and files should be referenced in relevant pages' specific stylesheets in the pages/ directory.

  - #### \_header.scss

    This file contains all styles specific to the site's header. Any rules here should only target the header.

- ### pages/

  This folder contains styles specific to individual pages. Each page should have one file.

  - #### \_home.scss

    This file contains styles specific to the site's homepage.
