# 一.ui控件xml属性

## 通用熟悉
android:id

长宽

android:layout_width

android:layout_height

长宽值
match_parent(=file_parent)
wrap_content,让当前控件的大小，刚好包住里面的内容

可见度
android:visibility

visible可见
invisible不可见但占据位置
gone无


## TextView 

文本对齐方向

android:gravity

center
布局对齐方向

android:layout_gravity

center

在xml中

android:ellipsize = "end"　　  省略号在结尾

android:ellipsize = "start" 　　省略号在开头

android:ellipsize = "middle"     省略号在中间

android:ellipsize = "marquee"  跑马灯

最好加一个约束android:singleline = "true"

## Button

## EditText

提示性文本

android:hint

最大行数

android:maxLines

## ImageView

图片地址

android:src

由于图片高宽未知，所以都设为 wrap_content

```
程序修改图片
imageView.setImageResource(R.drawable.jelly_bean);

```
图片自适应

android:scaleType
```
程序修改图片放大居中
 Iconimg.setScaleType(ImageView.ScaleType.CENTER_CROP);
 
 
 fixxy,拉伸填充
```
## ProgressBar

style="?android:attr/progressBarStyleHorizontal"

配合程序代码更改进度
android:max="100"
```
progressBar.getProgress();
progressBar.setProgress();
```

## AlertDialog

代码用法
``` java
@Override
public void onClick(View v){
  switch(v.getId()){
  case R.id.button:  
    AlertDialog.Builder dialogBuilder =new AlertDialog.Builder(context);
        dialogBuilder.setTitle("通知");
        dialogBuilder.setMessage("  ～   ～ ");
        dialogBuilder.setCancelable(false);
        dialogBuilder.setPositiveButton("好", new DialogInterface.OnClickListener() {
            //确认按钮的点击事件
            @Override
            public void onClick(DialogInterface dialog, int which) {

            }
        });
        dialogBuilder.setNegativeButton("不", new DialogInterface.OnClickListener() {
            @Override
            public void onClick(DialogInterface dialog, int which) {
                
            }
        });
        AlertDialog dialog=dialogBuilder.create();
        dialog.getWindow().setType(WindowManager.LayoutParams.TYPE_SYSTEM_ALERT);//设置AlertDialog类型，保证在广播接收器中可以正常弹出
        dialog.show();
    break;
  default:
    break;
  }
}
```

## PorgressDialog
方法与AlertDialog类似

表示袋控件，不能通过back键取消掉
    dialog.setCancelable("false");
    
关闭
    progressDialog.dissmiss()
    
# 二.界面布局

## LinearLayout
android:layout_width

android:layout_height

wrap_content

match_parent(=full_parent)

文本对齐方向

android:gravity

center

布局对齐方向(当orientation为vehicle时候起上下作用)

android:layout_gravity

android:layout_weight
当布局oriendtion为竖直，layout_weight可以决定横向权重。


## RelativeLayout

android:layout_alignParentLeft="true"
android:layout_alignParentTop="true"
android:layout_alignParentRight="true"
android:layout_alignParentBottom="true"

android:layout_above="@id/ffw"
android:layout_toRightOf="@id/f32"

## FrameLayout
统统都是左上角对齐
## TableLayout
表格对齐
合并单元格
android:layout_span="2"

拉伸表格宽度,将第二列拉伸
android:stretchColumns="1"
