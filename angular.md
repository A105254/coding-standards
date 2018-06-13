# Best practices to follow for Angular development

## Development

* write pure functions as much as possible
* variable and function names should be clear to convey its purpose
* check for spelling
* use !! operator instead of checking for null or undefined through if
* always specify return type for function where the it is not void
* for property types, ? defines optional where as <Type> | null defines it can either be of <Type> or null
* a function should do only one thing
* a function ideally should not contain more than 20-25 lines of code
* do not use `::ng-deep` style hack to override child component's style unless the business requirement cannot be negotiated and there is no other way to meet requirement
* move code logic from templates to component functions
* encapsulate properties into a type if there are many component properties
* do not use both unique class and id on a DOM element if not required
* create a folder for new components and keep all related files there
* create a module for new functional areas - group of related components
* avoid two way binding in template
* do not check-in commented codes
* create models to have contain component's logic and data structure
* try to achieve full code coverage
* try not use `elementRef` as it can introduce XSS vulnerabilities
* if we need to use `elementRef`, try to minimize its scope using ViewChild on specific DOM section through template reference variable
* to interact with the DOM, use `Renderer2` APIs
* data model class should not contain Model in name; but the file name should be like `*.model.ts`
* do not check-in code with `console.log`


## Testing

## Useful VS Code Extensions

* Angular Language Service
* Angular v6 Snippets
* Angular Files
* TS Lint
* Code Spell Checker
* Debugger for Chrome
* Bracket Pair Colorizer
* Auto Import
* Path Intellisense
* VS Live Share
* Bookmarks
* GitLens

