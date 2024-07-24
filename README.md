# svg-demo

## 设备视窗/视口 viewport
> 实际设备的大小，例如浏览器的大小

## svg 视口 viewport
> svg元素的大小，由svg的width和height属性决定；也可以通过css的width和height属性来设置，会覆盖svg的width和height属性

## viewBox
> 可以理解为一个照相机窗口来看svg元素
* x代表横轴的移动,>0照相机镜头向右移，那svg内容就向左移；
* y代表纵轴的移动，>0照相机镜头向下移，那svg内容就向上移；
* width代表横轴的可见'单位'数量，例如svg元素宽度是100px，而viewBox的width是100px，那就是1:1；而如果viewBox的width是200px，代表x轴需要看到200个单位，那固定的svg视口下，元素就要缩小才能看到更多,可以理解为摄像机离远了；而如果viewBox的width是50px，代表x轴需要看到50个单位，那固定的svg视口下，元素就要放大才能看到更多，可以理解为摄像机离近了 => 图形被裁剪，然后缩放以适应视口

* height代表纵轴的可见'单位'数量，例如svg元素高度是100px，而viewBox的height是100px，那就是1:1；而如果viewBox的height是200px，代表y轴需要看到200个单位，那固定的svg视口下，元素就要缩小才能看到更多

* viewBox="0,0,200,200" 理解为svg元素宽高只有100*100，但是要把200*200单位的内容放进去，那只能缩小
* viewBox="0,0,50,50" 理解为svg元素宽高有100*100，但只要显示50*50单位，那固定的svg视口下，元素就要放大才能看到更多;可能只显示元素的部分，只显示局部内容

> viewBox 的min-x 或 min-y 属性指定了非零值，则可能需要进行平移变换；类似于 CSS 变换中的 translate

> viewBox 的width 或 height属性，指定了与 svg 的 width 或 height 值，则可能需要进行缩放变换；像是 CSS 变换中的 scale


## preserveAspectRatio  保留横纵比
> 用于控制 SVG 中的 viewBox 在视口中的缩放和定位。这个属性主要用来确保图形在缩放时能够保持宽高比一致
> 值可以是 none、xMinYMin、xMidYMin、xMaxYMin、xMinYMid、xMidYMid、xMaxYMid、xMinYMax、xMidYMax 或 xMaxYMax 中的一个
> viewBox的min-x、mid-x、max-x、min-y、mid-y 、 max-y与 viewPort的min-x、mid-x、max-x、min-y、mid-y 、 max-y的对齐方式
* xMinYMin: viewBox 的 min-x 轴与视口的 min-x 轴对齐、viewBox 的 min-y 轴与视口的 min-y 轴对齐



视口坐标系统->常用的前端UI坐标系统
用户坐标系统->