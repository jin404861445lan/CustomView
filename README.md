# CustomView
Android自定义View

参考csdn

http://blog.csdn.net/guolin_blog/article/details/17357967#t0

![image](https://github.com/jin404861445lan/CustomView/blob/master/images/BAA9067EDBA6DCE142E38347D74047BC.jpg)

代码：
 
```
public class CustomView extends View implements View.OnClickListener {
    private Paint mPaint;
    private Rect mBounds;
    private int mCount = 0;


    public CustomView(Context context, AttributeSet attrs) {
        super(context, attrs);
        mPaint = new Paint(Paint.ANTI_ALIAS_FLAG);
        mBounds = new Rect();
        setOnClickListener(this);
    }


    @Override
    protected void onDraw(Canvas canvas) {
        super.onDraw(canvas);
        mPaint.setColor(Color.BLUE);
        canvas.drawRect(0, 0, getWidth(), getHeight(), mPaint);
        mPaint.setColor(Color.YELLOW);
        mPaint.setTextSize(30);
        String text = String.valueOf(mCount);
        mPaint.getTextBounds(text, 0, text.length(), mBounds);
        float textWidth = mBounds.width();
        float textHeight = mBounds.height();
        canvas.drawText(text, getWidth() / 2 - textWidth / 2, getHeight() / 2
                + textHeight / 2, mPaint);
    }

    @Override
    public void onClick(View v) {
        mCount++;
        invalidate();//重绘
    }
}

```


###欢迎关注虚实科技微信公众号，获得最新的技术和科技资讯

 <img src="https://github.com/jin404861445lan/Images/blob/master/wx.jpg" width = "300" height = "300" alt="" align=center />
