## 一、概述
通用Dialog，适用于ProgressDialog，BuilderDialog。
## 二、版本
已在多个项目中使用，且已上传jCenter，最新版本0.0.5，直接在gradle中添加即可。
compile 'com.hengda.zwf:HdDialog:0.0.5'
## 三、效果
### 1、ProgressDialog补间动画
![](http://oksdjdocc.bkt.clouddn.com/17-2-6/79120594-file_1486346779883_dc73.png)
### 2、ProgressDialog帧动画
![](http://oksdjdocc.bkt.clouddn.com/17-2-6/49606317-file_1486346779998_c220.png)
### 3、BuilderDialog默认布局
![](http://oksdjdocc.bkt.clouddn.com/17-2-6/95840505-file_1486346780216_7f00.png)
### 4、BuilderDialog自定义布局
![](http://oksdjdocc.bkt.clouddn.com/17-2-6/76351990-file_1486346780326_3ff9.png)
## 四、使用
此处以BuilderDialog自定义布局为例，简单介绍说使用，具体用法参见demo。
```
    /**
     * 该方法通过提取文字参数和点击事件继续封装
     *
     * @author 祝文飞（Tailyou）
     * @time 2017/2/6 9:37
     */
    private void showCustomDlg() {
        HDialogBuilder hDialogBuilder = new HDialogBuilder(mContext);

        View customView = View.inflate(mContext, R.layout.dialog_custom_view_all, null);
        TextView tvTitle = HdTool.getView(customView, R.id.tvTitle);
        TextView tvMsg = HdTool.getView(customView, R.id.tvMsg);
        TextView btnYes = HdTool.getView(customView, R.id.btnYes);
        TextView btnNo = HdTool.getView(customView, R.id.btnNo);
        tvTitle.setText("注销");
        tvMsg.setText("退出账号可能会使连续登录记录归零，确定退出？");
        btnYes.setText("确定退出");
        btnNo.setText("取消");
        btnYes.setOnClickListener(v -> hDialogBuilder.dismiss());
        btnNo.setOnClickListener(v -> hDialogBuilder.dismiss());

        hDialogBuilder.setCustomView(customView)
                .dlgColor(Color.TRANSPARENT)
                .cancelable(false)
                .show();
    }
```