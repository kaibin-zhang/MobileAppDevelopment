// 导入路由模块，用于页面跳转
import router from '@ohos.router';

// 定义一个名为 Second 的组件，并标记为入口组件
@Entry
@Component
struct Second {
  // 定义一个状态变量 message，初始值为 '这是第二个页面'
  @State message: string = '这是第二个页面';

  // 构建页面结构
  build() {
    // 创建一个水平排列的布局容器
    Row() {
      // 创建一个垂直排列的布局容器
      Column() {
        // 显示文本，内容为状态变量 message 的值
        Text(this.message)
          // 设置文本字体大小为 50
          .fontSize(50)
          // 设置文本字体加粗
          .fontWeight(FontWeight.Bold)
        // 创建一个按钮
        Button() {
          // 按钮上的文本内容为 'Back'
          Text('Back')
            // 设置按钮文本字体大小为 30
            .fontSize(30)
            // 设置按钮文本字体加粗
            .fontWeight(FontWeight.Bold)
            // 设置按钮的点击事件，点击时返回上一个页面
            .onClick(() => {
              router.back();
            })
        }
        // 设置按钮背景颜色为半透明的绿色
        .backgroundColor('#ff0aea0a')
      }
      // 设置垂直布局容器的子组件垂直居中对齐
      .justifyContent(FlexAlign.Center)
      // 设置垂直布局容器的子组件水平居中对齐
      .alignItems(HorizontalAlign.Center)
      // 设置垂直布局容器的高度为 100%
      .height('100%')
      // 设置垂直布局容器的宽度为 100%
      .width('100%')
    }
  }
}