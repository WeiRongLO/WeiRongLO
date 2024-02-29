<script>
export default {

  data() {
    return {
      textValue: '',
      selectedTab: '',
    };
  },
  computed: {
    // 篩選完成事項
    getData() {
      return this.checkbox.filter(input => input.checkbox === true);
    },
  },
  methods: {
    getInputValue(e) {
      this.textValue = e.target.value;
    },
  },
};
</script>

<template>
  <main>
    <div class="w-full h-screen	bg-gradient-to-b from-pink-200 ... flex justify-center	items-center	flex-col">
      <div class="box w-2/3	h-3/4	bg-orange-50 p-3">
        <div class="enter">
          <input type="text" class="add-text w-5/6 h-7">
          <button class="add-list w-[100px] ml-11 bg-blue-200 hover:bg-blue-300 px-3 py-1 rounded-lg">新增</button>
        </div>
        <div class="title-list flex justify-start	 items-center px-2 pt-3">
          <button type="button"
            class="title w-20 h-10 bg-indigo-400 hover:bg-yellow-200 px-3 text-center leading-9 rounded-t"
            data-title="all-data">全部</button>
          <button type="button"
            class="title w-20 h-10 bg-indigo-400 hover:bg-yellow-200 px-3 text-center leading-9 mx-2 rounded-t	"
            data-title="do-data">已執行</button>
          <button type="button"
            class="title w-20 h-10 bg-indigo-400 hover:bg-yellow-200 px-3 text-center leading-9 rounded-t"
            data-title="yet-data">未執行</button>
        </div>
        <div class="content-list w-full	 h-auto	 bg-teal-50	">
          <div class="content" data-content="all-data">
            <div class="in-title flex justify-around	 items-center py-2">
              <span>執行</span>
              <span>事項</span>
              <span>功能</span>
            </div>
            <div class="in-tool flex justify-around py-1">
              <input type="checkbox" name="" id="">
              <div class="data-show">{{ textValue }}</div>

              <div class="ml-[400px]">
                <button class="set w-[100px] bg-yellow-200 hover:bg-yellow-300 px-3 py-1 rounded-lg">編輯</button>
                <button class="delete w-[100px] bg-red-200 hover:bg-red-300 px-3 py-1 ml-2 rounded-lg">刪除</button>
              </div>

            </div>
          </div>
          <div class="content hidden" data-content="do-data"></div>
          <div class="content hidden" data-content="yet-data"></div>
        </div>
      </div>

    </div>
  </main>
</template>
<style scoped>
.hidden {
  display: none;
}
</style>
