# 新蜂商城Vue3项目结构说明

## 1. 根目录结构
- `README.md`：项目概述与技术栈说明
- `LICENSE`：MIT开源协议授权文件
- `package.json`：项目依赖管理及npm脚本配置
  - dependencies含Vue3全家桶、Vant4组件库、axios等核心依赖
  - devDependencies配置Vite构建工具链
- `vite.config.js`：Vite构建配置
  - 开发服务器配置(8080端口)
  - Vue插件及Vant组件自动导入
  - @路径别名配置
- `yarn.lock`：锁定依赖版本确保一致性
- `index.html`：应用入口文件
  - 包含视图窗口配置
  - 加载主脚本及字体图标
- `.gitignore`：版本控制忽略规则
  - 排除node_modules
  - 忽略构建产物目录
- `postcss.config.cjs`：PostCSS自动REM转换配置
- `public/`：静态资源目录
  - `favicon.ico`：网站图标

## 2. 核心代码(src)

### 2.1 入口文件
- `main.js`：应用主入口
- `App.vue`：根组件

### 2.2 路由配置
- `router/index.js`：路由配置中心

### 2.3 组件库
- `components/`：通用组件
  - `ListScroll.vue`：滚动加载组件（带触底加载功能）
  - `NavBar.vue`：顶部导航栏组件（集成返回按钮&标题）
  - `SimpleHeader.vue`：简化版头部（用于订单页）
  - `Swiper.vue`：商品轮播图组件（支持自动播放）
  - `VueImageVerify.vue`：图形验证码组件（登录验证）

## 2.4 页面视图
- `views/`：页面级组件
  - `Home.vue`：商城首页（含Banner+分类入口）
  - `ProductDetail.vue`：商品详情页（SKU选择+规格参数）
  - `Cart.vue`：购物车页面（商品勾选/全选）
  - `OrderDetail.vue`：订单详情页（支付状态跟踪）
  - `Address.vue`：地址列表页（默认地址标记）
  - `AddressEdit.vue`：地址编辑页（省市区三级联动）
  - `CreateOrder.vue`：订单创建页（运费计算）

## 2.5 状态管理
- `stores/cart.js`：购物车状态管理（Pinia实现）
  - 管理购物车商品数据
  - 处理勾选状态切换
  - 计算选中商品总价

## 2.6 工具模块
- `utils/axios.js`：封装Axios请求
  - 请求拦截器（添加token）
  - 响应拦截器（错误处理）
  - 统一API出口

## 3. 服务层接口
- `service/`：按业务模块划分的接口
  - `user.js`：用户服务（登录/注册/退出）
  - `cart.js`：购物车服务（增删改查）
  - `order.js`：订单服务（创建/查询）
  - `address.js`：地址服务（增删改查）
  - `good.js`：商品服务（详情查询）

### 2.4 页面视图
- `views/`：页面级组件
  - `Home.vue`：首页
  - `ProductDetail.vue`：商品详情页
  - `Cart.vue`：购物车页
  - `OrderDetail.vue`：订单详情页

### 2.5 状态管理
- `stores/cart.js`：购物车状态管理(Pinia)

### 2.6 工具模块
- `utils/axios.js`：封装Axios请求

## 3. 服务层接口
- `service/`：按业务模块划分的接口
  - `user.js`：用户相关接口
  - `cart.js`：购物车相关接口
  - `order.js`：订单相关接口

## 4. 开发规范
1. 组件命名：大驼峰式命名法
2. 视图目录：页面级组件统一放在views目录
3. 接口管理：按业务模块拆分service文件
4. 状态管理：使用Pinia进行状态管理
5. 样式规范：使用Less预处理，配合Vant主题定制

## 5. 构建流程
```bash
# 开发模式
npm run dev

# 生产构建
npm run build

# 预览构建
npm run preview
```