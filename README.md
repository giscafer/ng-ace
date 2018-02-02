# ng-ace

[![npm package](https://img.shields.io/npm/v/ng-ace.svg)](https://www.npmjs.org/package/ng-ace)

A basic ace editor directive for angular2\angular4\agnular5. base on [@seiyria/ng2-ace](https://github.com/seiyria/ng2-ace)

Online Demo see https://github.com/giscafer/ng-form-builder

# Install

`npm i ng-ace`

# Sample Usage

```ts
import { Component } from '@angular/core';

import { AceEditorDirective } from 'ng-ace';

import 'brace/theme/clouds';
import 'brace/mode/sql';

@Component({
  directives: [AceEditorDirective],
  template: `
  <div ace-editor
       [text]="text"
       [mode]="'sql'"
       [theme]="'clouds'"
       [options]="options"
       [readOnly]="false"
       (textChanged)="onChange($event)"
       style="display:block; height: 80vh; width:100%"></div>
  `
})
export class MyComponent {
  constructor() {
    this.text = 'test';
    this.options = { printMargin: false };
    this.onChange = (data) => {
      console.log(data);
    }
  }
}
```
Important pieces to note in the HTML template: `[ace-editor]` attribute, `[text]`, `[theme]`, `[mode]`, `[readOnly]`, `[options]` inputs, `(textChanged)` ,`(editorRef)` output. As per Ace, you must also make it a `display: block;` and give it a width and height.


