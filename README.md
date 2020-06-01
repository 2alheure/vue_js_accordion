# Vue JS Accordion
A simple Accordion component for Vue JS.

## How to use
Download the component file and place it in your `components/` folder.  
Then, you can import it with `import Accordion from "@/components/Accordion.vue";`.  
  
Nota Bene: this component was built using [Tailwind CSS](https://tailwindcss.com/). If you don't want to use it, then check the `alternative_style.css` file and add its content to the component's `<style>` tag.

## Props
You can pass several props to the component, mainly to style it as you wish:
- `opened` is a boolean, that defaults to `false`, and tells whether the content should be displayed by default.
- `symbolOpened` and `symbolClosed` are two String parameters that define what to use as symbol for opened and closed accordion. They respectively default to `&or;` and `&gt;`. Can be HTML.
- `accordionStyle`, `headerStyle`, `symbolStyle` and `contentStyle` are 4 props used to style different parts of the accordion. They can be String or Object and default to the basic styling of this component. The component is very lightly styled so you can customize it as you wish.

## Example
```html
<Accordion :headerStyle="headerStyle" :contentStyle="contentStyle">
  <template #header">
    Your accordion title. Can also be <strong>HTML</strong>.
  </template>

  Your accordion content. It can be simple text like this.
  <p>It can also be HTML.</p>
</Accordion>

<script>
  import Accordion from "@/components/Accordion.vue";
  
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
