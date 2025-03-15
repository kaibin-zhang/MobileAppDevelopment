// 导入路由模块，用于页面跳转
import { router } from '@kit.ArkUI';

// 定义一个名为 Index 的组件，并标记为入口组件
@Entry
@Component
struct Index {
  // 定义一个状态变量 message，初始值为 '这是第一个页面'
  @State message: string = '这是第一个页面';

  // 构建页面结构
  build() {
    // 创建一个水平排列的布局容器
    Row(){
      // 创建一个垂直排列的布局容器
      Column(){
        // 显示文本，内容为状态变量 message 的值
        Text(this.message)
          // 设置文本字体大小为 50
          .fontSize(50)
          // 设置文本字体加粗
          .fontWeight(FontWeight.Bold)
        // 创建一个按钮
        Button(){
          // 按钮上的文本内容为 'Next'
          Text('Next')
            // 设置按钮文本字体大小为 30
            .fontSize(30)
            // 设置按钮文本字体加粗
            .fontWeight(FontWeight.Bold)
        }
        // 设置按钮类型为胶囊型
        .type(ButtonType.Capsule)
        // 设置按钮的上边距为 20
        .margin({
          top:20
        })
        // 设置按钮背景颜色为半透明的紫色
        .backgroundColor('#ff0d94fb')
        // 设置按钮宽度为父容器的 40%
        .width('40%')
        // 设置按钮高度为父容器的 5%
        .height('5%')
        // 设置按钮的点击事件，点击时跳转到 Second 页面，并传递参数
        .onClick(() => {
          router.pushUrl({
            // 跳转的目标页面为 'pages/Second'
            url:'pages/Second',
            // 传递的参数，键为 'src'，值为 'Index页面传来的数据'
            params:{
              src:'Index页面传来的数据'
            }
          });
        })
      }
      // 设置垂直布局容器的宽度为 100%
      .width('100%')
    }
    // 设置水平布局容器的高度为 100%
    .height('100%')
  }
}