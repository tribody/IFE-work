# 三栏式布局
本次课程我采用的是左右浮动，中间相对定位并使用margin膨胀。

了解了下大致有三种方法可以实现三栏式布局，来源度娘。

## 1、绝对定位法
新建3个div，将其中两个利用position的absolute属性将其中两个固定再浏览器的两侧，另外一个div用左右margin值撑开距离。此种方法三个div顺序可以进行调换。

## 2、浮动方法
新建3个div，将其第一个与第二个进行左浮动与右浮动，设置width，第三个为内容（注意清除浮动）将宽度设置为auto。注意：div顺序不能改变，左右浮动的div必须放在前面。

## 3、负margin值法
这种方法是在实际的网站中应用的最多的，我个人感觉多少有些跟风的嫌疑。此方法很难用一句话概括。首先，中间的主体要使用双层标签。外层div宽度100%显示，并且浮动（本例左浮动，下面所述依次为基础），内层div为真正的主体内容，含有左右210像素的margin值。左栏与右栏都是采用margin负值定位的，左栏左浮动，margin-left为-100%，由于前面的div宽度100%与浏览器，所以这里的-100%margin值正好使左栏div定位到了页面的左侧；右侧栏也是左浮动，其margin-left也是负值，大小为其本身的宽度即200像素。