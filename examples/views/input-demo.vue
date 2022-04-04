<script>
/**
 * 为什么antv的AInput没有用v-model或者没有在onChange事件中改变value, blur时输入的值会自动重置？
 * 因为其内部监听了input的blur事件，在blur中做了forceUpdate
 *
 */
window.inputValue = '123';
export default {
  created() {
    this.a = '456';
  },
  render() {
    console.log('render');
    return <a-input value={this.a} onChange={this.changeHandler}></a-input>;
    // return <input type='text' value={window.inputValue} onChange={this.changeHandler}/>
  },
  methods: {
    changeHandler(e) {
      console.log(e.target.value);
      window.inputValue = e.target.value;
      this.a = e.target.value;
      // this.$forceUpdate()
    },
  },
};
</script>
