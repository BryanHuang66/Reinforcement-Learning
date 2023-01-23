# 增强学习
参考自 ![莫烦python](https://github.com/MorvanZhou/Reinforcement-learning-with-tensorflow/blob/master/contents/3_Sarsa_maze/RL_brain.py)

主要修改地方：

1.  由于迷宫比较小，初始化的时候直接初始化整张Q Table，在初始化Q Table的时候要求如果上下左右存在障碍物时，直接将Q Table对应的值更新为-1, 实践证明这种方法能够提升收敛速度。
2. 更新的时候，如果走到了重复的路线，我要求reward为-0.1，这样可以少走回头路。
3. 将搜寻的过程从动画这边为后台运行，能够进一步节约模型学习的时间。
4. 基于tkinter实现交互界面，可以点击迷宫中的白色方块（非障碍物），自动规划路径




## 安装环境
```
pip install -r requirements.txt
```

## q learning走迷宫
使用方法：

1. 逐步运行Jupyter Notebook
2. 弹出交互界面
3. 根据指令点击白色区域
4. 等待，详细运行过程可以看Jupyter Notebook界面
5. 继续进行实验

## Sarsa 走迷宫
区别于 q learning, Sarsa更新 Q(s,a) 的时候基于的是下一个 Q(s_, a_), 因此改动的代码就在更新Q Table中。不过我没有对此调整参数，有可能会出现找不到路径的情况。有兴趣的同学可以继续调参。
