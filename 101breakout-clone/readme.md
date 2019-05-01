1. 首先确定 有多少个div
    ball, barrier, brick, score, gameover

2. javascript 用一个函数来创建游戏 首先用构造函数 拿到这几个div
    其他的方法 都写在prototype里面 自动继承给这个函数 **

3. prototype里面 一个函数 init初始化 全部的brick， barrier 和 ball 
    （1）brick比较简单 先计算每行多少个 然后创建 加入到div里面
    （2）barrier初始位置 document然后绑定一个鼠标移动时间 移动的设置为barrier的中间
        并且设置不能超出左右的边界 这里用 超过最大就=最大 超过最左 就=0 **
    （3）初始ball位置 then设置一个速度 然后绑定一个事件 当点击鼠标就开始游戏
        这里用settimeinterval来保持更新 用一个bool控制 在这个里面 调用一个方法更新
            11.ball的位置，和移动的位置计算 其实每次就移动一格 只是有正负
            22.检查碰撞边框和barrier 碰撞找中间点 取abs值 
            33.检查碰撞brick 中间点减去中间点 取abs 值在一半内就说明碰撞了


4. 注意添加px设置坐标时候，当绑定事件 内部拿不到外面的对象 需要bind(this) 这样只能把回调函数写成方法***

clientX, clientY是相对于视口的坐标 
offsetX, offsetY是鼠标相对于对象的坐标

offsetparent:
offsetleft 物体左边到parent的距离 offsetTop是到上边parent的距离
offsetHeight, offsetWidth是物体整个 包括padding和broder-size 游戏里面应该就用这个