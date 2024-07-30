<div id="app">
  <ul>
    <li v-for="item in items" :key="item.id">{{ item.text }}</li>
  </ul>
  <button @click="changeItems">Change Items</button>
</div>

<script>
  new Vue({
    el: '#app',
    data: {
      items: [
        { id: 1, text: 'Item 1' },
        { id: 2, text: 'Item 2' },
        { id: 3, text: 'Item 3' }
      ]
    },
    methods: {
      changeItems() {
        this.items = [
          { id: 1, text: 'New Item 1' },
          { id: 2, text: 'New Item 2' },
          { id: 3, text: 'New Item 3' }
        ];
      }
    }
  });
</script>
