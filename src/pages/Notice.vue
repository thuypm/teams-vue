 
<template>
  <div class="list-notice-pane" >
    <a-list
      item-layout="vertical"
      size="large"
      :pagination="pagination"
      class="list-notice"
      style="padding: 10px; background: #fff; border-radius: 5px"
      :data-source="listData"
    >
      <div slot="footer"><b>ant design vue</b> footer part</div>
      <a-list-item slot="renderItem" key="item.title" slot-scope="item">
        <template v-for="{ type, text } in actions" slot="actions">
          <span :key="type">
            <a-icon :type="type" style="margin-right: 8px" />
            {{ text }}
          </span>
        </template>
        <a-list-item-meta :description="item.description">
          <a slot="title" :href="item.href">{{ item.title }}
               <a-icon type="notification" style="color: red ;float:right"/>
            </a>
          <a-avatar slot="avatar" :src="item.avatar" />
          <a-icon type="star"/>
        </a-list-item-meta>
      </a-list-item>
    </a-list>
  </div>
</template>
<script>
const listData = [];
for (let i = 0; i < 23; i++) {
  listData.push({
    href: "https://www.antdv.com/",
    title: `ant design vue part ${i}`,
    avatar: "https://zos.alipayobjects.com/rmsportal/ODTLcjxAfvqbxHnVXCYX.png",
    description:
      "Ant Design, a design language for background applications, is refined by Ant UED Team.",
    content:
      "We supply a series of design principles, practical patterns and high quality design resources (Sketch and Axure), to help people create their product prototypes beautifully and efficiently.",
  });
}

export default {
  data() {
    return {
      listData,
      pagination: {
        onChange: (page) => {
          console.log(page);
        },
        pageSize: 2,
      },
      actions: [
        { type: "check", text: "Đã đọc" },
        { type: "read", text: "Đánh dấu là chưa đọc" },
        { type: "delete", text: "Xóa" },
      ],
    };
  },
};
</script>
<style scoped>
.list-notice-pane{
padding: 20px 80px 0 80px
}
</style>