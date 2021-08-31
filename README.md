# Vue JS Accordion
A simple Accordion component for Vue JS.  
This component is compatible with Vue 3.

- [Vue JS Accordion](#vue-js-accordion)
  - [Installation](#installation)
  - [Usage](#usage)
    - [Simple usage example](#simple-usage-example)
  - [Props](#props)
  - [Events](#events)

## Installation
First, run `npm install @2alheure/vue-accordion`.  
Then import it with `import Accordion from "@2alheure/vue-accordion";`.  

## Usage
### Simple usage example
```html
<Accordion :headerStyle="headerStyle" :contentStyle="contentStyle">
  <template #header">
    Your accordion title. Can also be <strong>HTML</strong>.
  </template>

  Your accordion content. It can be simple text like this.
  <p>It can also be HTML.</p>
</Accordion>

<script>
  import Accordion from "@2alheure/vue-accordion";
  
  export default {
    components: {
      Accordion
    },
    data() {
      return {
        headerStyle: 'background-color: white;',
        contentStyle: {
          color: 'red',
          fontSize: '42px'
        }
      }
    }
  };
</script>
```

## Props
| Name           |      Type       |                         Default value                          | Description                                                |
| :------------- | :-------------: | :------------------------------------------------------------: | ---------------------------------------------------------- |
| opened         |     Boolean     |                            `false`                             | Whether the content should be displayed when loaded.       |
| symbolOpened   |     String      |                             `&or;`                             | The symbol to use for the opened accordion. (Can be HTML.) |
| symbolClosed   |     String      |                             `&gt;`                             | The symbol to use for the closed accordion. (Can be HTML.) |
| headerStyle    | String / Object |                       `padding: .5rem;`                        | The style for the header.                                  |
| symbolStyle    | String / Object | `font-size: 1.5rem; font-weight: 700; vertical-align: middle;` | The style for the symbol.                                  |
| contentStyle   | String / Object |          `width: 98%; margin: auto; padding: .5rem;`           | The style for the content.                                 |
| accordionClass | String / Object |                             `null`                             | The classes for the accordion.                             |
| headerClass    | String / Object |                             `null`                             | The classes for the header.                                |
| symbolClass    | String / Object |                             `null`                             | The classes for the symbol.                                |
| contentClass   | String / Object |                             `null`                             | The classes for the content.                               |

## Events
| Name   | Description                                                      |
| :----- | ---------------------------------------------------------------- |
| open   | Emitted each time the accordion is opened.                       |
| close  | Emitted each time the accordion is closed.                       |
| switch | Emitted each time the accordion switches between open and close. |
