# 智慧弈星（IntelliGobang）- 智能五子棋对战平台

![游戏界面预览](/img/2025-05-14_223038_191.png) <!-- 实际使用时可替换为游戏截图 -->

## 🎮 项目概述
一个基于HTML5 Canvas的智能五子棋对战平台，支持双人对战（PVP）和人机对战（PVE）模式。AI采用启发式搜索算法实现智能落子决策。

## ✨ 核心功能
| 功能模块       | 描述                          |
|----------------|-------------------------------|
| 双人对战模式   | 支持本地两位玩家轮流对战      |
| 智能AI对战     | 基于启发式评估的AI决策系统    |
| 动态棋盘渲染   | Canvas实现的平滑棋盘绘制效果  |
| 胜利条件检测   | 实时五子连线检测系统          |
| 游戏状态管理   | 完整游戏生命周期控制          |

## 📜 文件结构
```tree
IntelliGobang/
├── index.html            # 主界面与游戏逻辑
├── LICENSE               # 版权信息
└── README.md             # 文档介绍
```

## ⚙ 核心算法流程
![核心算法流程](/img/game.svg)

## 🧠 AI算法设计
```python
def evaluate_position(x, y, player):
    # 四方向评估：横向、纵向、对角线
    score = 0
    for dx, dy in [(1,0), (0,1), (1,1), (1,-1)]:
        count = 1
        # 正向检测连续棋子
        for i in range(1,5):
            nx, ny = x + dx*i, y + dy*i
            if 超出边界 or 非当前玩家: break
            count +=1
        # 反向检测连续棋子
        for i in range(1,5):
            nx, ny = x - dx*i, y - dy*i
            if 超出边界 or 非当前玩家: break
            count +=1
        # 评分策略：连珠数指数增长
        score += 10 ** count
    return score
```

## 🚀 功能演进
- [x] 基础棋盘绘制与落子功能
- [x] 双人对战模式实现
- [x] 基于规则的AI引擎
- [ ] 蒙特卡洛树搜索算法集成
- [ ] 在线对战功能开发
- [ ] 棋谱记录与回放系统

## 📚 技术栈
**前端框架**  
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![Canvas](https://img.shields.io/badge/Canvas-2C2255?style=flat&logo=html5&logoColor=white)

**AI引擎**  
![启发式搜索](https://img.shields.io/badge/启发式搜索-00B4D8?style=flat)
![决策树](https://img.shields.io/badge/决策树-0096C7?style=flat)

## 📄 开源协议
[Apache-2.0 license](LICENSE) © 2025 科技语者开发团队
