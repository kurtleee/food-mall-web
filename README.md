# food-mall-web
food-mall-webmall-admin-web是一个电商后台管理系统的前端项目，基于Vue+Element实现。 主要包括商品管理、订单管理、会员管理、促销管理、运营管理、内容管理、统计报表、财务管理、权限管理、设置等功能。
### 电商 Web 管理平台项目开发手册

#### 项目介绍

本项目是一个基于 Vue.js 和 Element UI 的前后端分离的电商管理系统前端部分。该项目采用现代前端技术栈，提供了丰富的功能模块，适用于快速开发和扩展电商管理系统。

#### 项目结构

```
woniu-mall-app-web/
├── build/
├── config/
├── node_modules/
├── src/
│   ├── api/
│   ├── assets/
│   ├── components/
│   ├── icons/
│   ├── router/
│   ├── store/
│   ├── styles/
│   ├── utils/
│   ├── views/
│   ├── App.vue
│   ├── main.js
│   ├── permission.js
├── static/
├── .babelrc
├── package.json
├── README.md
```

### src目录说明

```
src -- 源码目录
├── api -- axios网络请求定义
├── assets -- 静态图片资源文件
├── components -- 通用组件封装
├── icons -- svg矢量图片文件
├── router -- vue-router路由配置
├── store -- vuex的状态管理
├── styles -- 全局css样式
├── utils -- 工具类
└── views -- 前端页面
    ├── home -- 首页
    ├── layout -- 通用页面加载框架
    ├── login -- 登录页
    ├── oms -- 订单模块页面
    ├── pms -- 商品模块页面
    └── sms -- 营销模块页面
```

**特别注意**：

- 访问在线接口无需搭建后台环境，只需将`config/dev.env.js`文件中的`BASE_API`改为[https://admin-api.macrozheng.com](https://admin-api.macrozheng.com/)即可;
- 若需要与后端接口进行调试，需将`config/dev.env.js`文件中的`BASE_API`改为**后端地址**，例如 SpringBoot 服务器运行在 `localhost:8088`, `BASE_API` 需要修改为 `http://localhost:8088`

**如何运行？**

- Node.js 版本 -> v12.4.0
- 在IDEA命令行中运行命令：`npm install`,下载相关依赖;
- 在IDEA命令行中运行命令：`npm run dev`,运行项目;
- 访问地址：[http://localhost:8090](http://localhost:8090/) 即可打开后台管理系统页面;

#### `build/`

构建工具和脚本，用于项目的打包和构建。

#### `config/`

项目的配置文件，包括开发环境和生产环境的配置。

#### `node_modules/`

项目依赖的第三方库和模块。

#### `src/`

项目的主要源码目录：

- **`api/`**：API 请求模块，存放所有与后端接口交互的请求文件。
- **`assets/`**：静态资源，包括图片、字体等。
- **`components/`**：通用组件，存放项目中使用的各种 Vue 组件。
- **`icons/`**：项目使用的图标文件。
- **`router/`**：前端路由配置文件。
- **`store/`**：Vuex 状态管理相关文件。
- **`styles/`**：全局样式文件。
- **`utils/`**：工具函数和通用方法。
- **`views/`**：页面组件，存放项目中的各个页面。
- **`App.vue`**：根组件。
- **`main.js`**：项目的入口文件，初始化 Vue 实例。
- **`permission.js`**：权限控制逻辑。

#### `static/`

不需要 Webpack 处理的静态资源文件。

#### `.babelrc`

Babel 配置文件，用于 JavaScript 语法转换。

#### `package.json`

项目的配置文件，包括项目名称、版本、依赖项等。

#### `README.md`

项目的自述文件，包含项目的简介、安装使用说明等。

### 开发手册

#### 1. 修改具体组件

假设我们要修改 `Breadcrumb` 组件和 `Upload` 组件。

##### `Breadcrumb` 组件

- **文件位置**：`src/components/Breadcrumb`
- **主要文件**：
  - `Breadcrumb.vue`：组件主文件，定义了面包屑导航的结构和样式。
  - `index.js`：组件的入口文件，便于按需引入。

**修改步骤**：

1. 打开 `Breadcrumb.vue` 文件，根据需求修改组件的结构和样式。
2. 如需增加新的功能，可以在 `methods` 中添加新的方法。
3. 更新 `index.js` 文件以反映新的组件接口。

##### `Upload` 组件

- **文件位置**：`src/components/Upload`
- **主要文件**：
  - `Upload.vue`：组件主文件，定义了文件上传的结构和样式。
  - `index.js`：组件的入口文件，便于按需引入。

**修改步骤**：

1. 打开 `Upload.vue` 文件，根据需求修改组件的结构和样式。
2. 如需支持更多文件格式，可以在 `accept` 属性中增加格式。
3. 如需增加新的功能，可以在 `methods` 中添加新的方法。
4. 更新 `index.js` 文件以反映新的组件接口。

#### 2. 修改 API

- **文件位置**：`src/api`
- **说明**：API 目录下存放的是与后端进行交互的请求文件。根据不同的模块，API 文件进行了分类。

**修改步骤**：

1. 根据需求找到相应的 API 文件，例如 `product.js` 处理商品相关的 API 请求。
2. 在 API 文件中，找到需要修改的接口方法，更新请求的 URL 或参数。
3. 如需新增 API，可以在相应的文件中添加新的方法，并在组件中调用。

#### 3. 修改 Vuex 状态管理

- **文件位置**：`src/store`
- **说明**：Vuex 用于管理全局的应用状态，包括状态、突变、动作等。

**修改步骤**：

1. 如果需要增加新的状态管理模块，可以在 `src/store/modules` 目录下新建文件，例如 `product.js`。
2. 在新的模块文件中，定义状态、突变和动作。
3. 在 `src/store/index.js` 文件中，引入并注册新的模块。

#### 4. 修改路由

- **文件位置**：`src/router`
- **说明**：路由目录下存放的是项目的路由配置文件。

**修改步骤**：

1. 打开 `index.js` 文件，找到需要修改的路由配置。
2. 根据需求添加、修改或删除路由。
3. 如果新增了页面组件，需要在 `views` 目录下创建相应的 Vue 组件，并在路由配置中引入。

# ----------------

# 1. 组件和页面的修改步骤指南

#### 目标

假设我们需要新增一个名为 "ProductList" 的页面，同时定义新的 API 接口，并与后端对接。具体步骤如下：

### 1. 新增页面组件

#### 文件位置

`src/views`

#### 操作步骤

1. **创建组件文件夹**：
   - 在 `src/views` 目录下新建文件夹 `ProductList`。
   - 在 `ProductList` 文件夹下创建文件 `ProductList.vue`。

2. **编写页面组件**：
   - 打开 `ProductList.vue`，编写页面的结构、样式和逻辑。例如：

```vue
<template>
  <div class="product-list">
    <el-table :data="products">
      <el-table-column prop="id" label="ID"></el-table-column>
      <el-table-column prop="name" label="Product Name"></el-table-column>
      <el-table-column prop="price" label="Price"></el-table-column>
    </el-table>
  </div>
</template>

<script>
import { fetchProducts } from '@/api/product';

export default {
  name: 'ProductList',
  data() {
    return {
      products: []
    };
  },
  created() {
    this.getProducts();
  },
  methods: {
    async getProducts() {
      try {
        const response = await fetchProducts();
        this.products = response.data;
      } catch (error) {
        console.error('Failed to fetch products:', error);
      }
    }
  }
};
</script>

<style scoped>
.product-list {
  padding: 20px;
}
</style>
```

### 2. 定义新的 API 接口

#### 文件位置

`src/api`

#### 操作步骤

1. **创建 API 文件**：
   - 在 `src/api` 目录下新建文件 `product.js`。

2. **编写 API 请求方法**：
   - 打开 `product.js` 文件，定义 API 请求方法。例如：

```javascript
import request from '@/utils/request';

export function fetchProducts() {
  return request({
    url: '/products',
    method: 'get'
  });
}
```

### 3. 配置路由

#### 文件位置

`src/router`

#### 操作步骤

1. **修改路由配置文件**：
   - 打开 `src/router/index.js` 文件，添加新的路由配置。例如：

```javascript
import Vue from 'vue';
import Router from 'vue-router';
import ProductList from '@/views/ProductList/ProductList.vue';

Vue.use(Router);

const routes = [
  {
    path: '/products',
    name: 'ProductList',
    component: ProductList
  }
  // 其他路由配置
];

export default new Router({
  routes
});
```

### 4. 注册全局组件（如果需要）

#### 文件位置

`src/main.js`

#### 操作步骤

1. **修改主入口文件**：
   - 打开 `src/main.js` 文件，如果需要全局注册组件，可以在此文件中进行。例如：

```javascript
import Vue from 'vue';
import App from './App.vue';
import router from './router';
import store from './store';
import ProductList from '@/views/ProductList/ProductList.vue';

Vue.config.productionTip = false;

// 全局注册组件
Vue.component('ProductList', ProductList);

new Vue({
  router,
  store,
  render: h => h(App)
}).$mount('#app');
```

### 5. 配置后端接口（后端使用 Spring Boot）

#### 文件位置

`src/main/java/com/example/mall/controller`

#### 操作步骤

1. **创建控制器**：
   - 在后端的 `controller` 目录下新建 `ProductController.java`。

2. **编写控制器方法**：
   - 打开 `ProductController.java`，编写 API 接口方法。例如：

```java
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;
import java.util.List;
import com.example.mall.service.ProductService;
import com.example.mall.model.Product;

@RestController
@RequestMapping("/products")
public class ProductController {

  private final ProductService productService;

  public ProductController(ProductService productService) {
    this.productService = productService;
  }

  @GetMapping
  public List<Product> getAllProducts() {
    return productService.getAllProducts();
  }
}
```

### 6. 测试和调试

1. **启动后端服务**：确保后端服务正常运行，并且 API 接口能够正确返回数据。
2. **启动前端项目**：运行前端项目，访问 `/products` 路由，查看是否能正确展示产品列表。

### 结语

通过上述步骤，我们可以在项目中新增页面组件、定义新的 API 接口并与后端对接。

# ---------------

# 2. API 文件配置指南

配置的 API 接口需要在组件中进行调用，以获取数据并在页面上显示。以下是详细的步骤，展示如何在组件中应用配置的 API 接口。

### 1. 确保 API 文件已正确配置

假设我们有一个新的 API 接口文件 `product.js`，其中定义了 `fetchProducts` 方法：

```javascript
// src/api/product.js
import request from '@/utils/request';

export function fetchProducts() {
  return request({
    url: '/products',
    method: 'get'
  });
}
```

### 2. 在组件中引入并调用 API

接下来，我们在需要使用这个 API 的组件中引入并调用它。假设我们要在 `ProductList.vue` 组件中使用这个 API 接口。

#### 文件位置

`src/views/ProductList/ProductList.vue`

#### 操作步骤

1. **引入 API 接口**：
   - 在组件中引入 `fetchProducts` 方法。

2. **调用 API 并处理数据**：
   - 在组件的生命周期钩子（如 `created`）中调用 API，并将返回的数据存储在组件的 `data` 属性中，以便在模板中使用。

以下是完整的代码示例：

```vue
<template>
  <div class="product-list">
    <el-table :data="products">
      <el-table-column prop="id" label="ID"></el-table-column>
      <el-table-column prop="name" label="Product Name"></el-table-column>
      <el-table-column prop="price" label="Price"></el-table-column>
    </el-table>
  </div>
</template>

<script>
import { fetchProducts } from '@/api/product';  // 引入 API 接口

export default {
  name: 'ProductList',
  data() {
    return {
      products: []  // 定义存储产品列表的数据属性
    };
  },
  created() {
    this.getProducts();  // 在组件创建时调用获取产品列表的方法
  },
  methods: {
    async getProducts() {
      try {
        const response = await fetchProducts();  // 调用 API 接口获取数据
        this.products = response.data;  // 将数据存储在组件的 data 属性中
      } catch (error) {
        console.error('Failed to fetch products:', error);  // 处理可能的错误
      }
    }
  }
};
</script>

<style scoped>
.product-list {
  padding: 20px;
}
</style>
```

### 3. 调试和测试

1. **启动后端服务**：确保后端服务运行正常，API 接口能够正确返回数据。
2. **启动前端项目**：运行前端项目，并访问相应的路由（如 `/products`），查看页面是否能正确显示产品列表。



# -------------------

# 3. router/index.js 文件配置指南

### 文件功能解释

文件位于/src/router/index.js。这个文件定义了 Vue 项目的路由配置，使用 Vue Router 来管理应用的路由。路由配置分为两部分：`constantRouterMap` 和 `asyncRouterMap`。这些配置定义了应用中各个页面的路由规则，并提供了导航栏的菜单项。

#### 主要部分解析

1. **引入 Vue 和 Vue Router**：

   ```javascript
   import Vue from 'vue'
   import Router from 'vue-router'
   Vue.use(Router)
   ```

2. **引入布局组件**：

   ```javascript
   import Layout from '../views/layout/Layout'
   ```

3. **路由元信息说明**：
   注释部分解释了路由的各种元信息的作用，如 `hidden`、`alwaysShow`、`redirect`、`name` 和 `meta` 属性。

4. **`constantRouterMap`**：
   定义了不需要权限校验的静态路由，包含登录页、404页和首页。

   ```javascript
   export const constantRouterMap = [
     { path: '/login', component: () => import('@/views/login/index'), hidden: true },
     { path: '/404', component: () => import('@/views/404'), hidden: true },
     {
       path: '',
       component: Layout,
       redirect: '/home',
       meta: { title: '首页', icon: 'home' },
       children: [{
         path: 'home',
         name: 'home',
         component: () => import('@/views/home/index'),
         meta: { title: '仪表盘', icon: 'dashboard' }
       }]
     }
   ]
   ```

5. **`asyncRouterMap`**：
   定义了需要权限校验的动态路由，包含商品管理、订单管理、营销活动、权限管理等模块。

   ```javascript
   export const asyncRouterMap = [
     {
       path: '/pms',
       component: Layout,
       redirect: '/pms/product',
       name: 'pms',
       meta: { title: '商品', icon: 'product' },
       children: [ ... ]
     },
     ...
     { path: '*', redirect: '/404', hidden: true }
   ]
   ```

6. **创建并导出 Vue Router 实例**：

   ```javascript
   export default new Router({
     // mode: 'history', //后端支持可开
     scrollBehavior: () => ({ y: 0 }),
     routes: constantRouterMap
   })
   ```

### 自定义导航栏（重要）

#### 1. 自定义导航栏菜单项

假设我们要添加一个新的页面 "报告管理"（Report Management）到导航栏中。我们需要进行以下几个步骤：

##### 创建新页面组件

在 `src/views` 目录下创建新的页面组件文件夹和组件文件：

```sh
mkdir -p src/views/report
touch src/views/report/Report.vue
```

在 `Report.vue` 中编写页面内容：

```vue
<template>
  <div class="report">
    <h1>Report Management</h1>
    <p>This is the report management page.</p>
  </div>
</template>

<script>
export default {
  name: 'Report'
}
</script>

<style scoped>
.report {
  padding: 20px;
}
</style>
```

##### 修改路由配置

在 `src/router/index.js` 文件中，添加新的路由配置：

1. **引入新组件**：

   ```javascript
   const Report = () => import('@/views/report/Report.vue')
   ```

2. **在 `asyncRouterMap` 中添加新路由**：

   ```javascript
   export const asyncRouterMap = [
     {
       path: '/report',
       component: Layout,
       redirect: '/report/index',
       name: 'report',
       meta: { title: '报告管理', icon: 'report' },
       children: [
         {
           path: 'index',
           name: 'reportIndex',
           component: Report,
           meta: { title: '报告管理', icon: 'report' }
         }
       ]
     },
     ...
   ]
   ```

备注：

**`constantRouterMap`**：定义静态路由，适用于无需权限控制的公共页面。通常，这些路由在应用初始化时就会加载和显示，例如登录页、404 页、首页等。任何用户都可以访问这些路由，无需进行权限验证。

#### 常见场景：

- 登录页面 (`/login`)
- 404 错误页面 (`/404`)
- 公共页面或欢迎页面



**`asyncRouterMap`**：定义动态路由，适用于需要根据用户权限动态加载的页面。

#### 常见场景：

- 用户管理页面
- 商品管理页面
- 订单管理页面
- 任何需要特定权限的页面

我们自己写的组件，统一定义在asyncRouterMap动态路由当中。



#### 2. 修改布局组件

如果导航栏是在 `Layout` 组件中定义的，我们也可能需要修改 `Layout` 组件中的菜单配置。 `Layout` 组件在 `src/views/layout/Layout.vue` 中：

```vue
<template>
  <div>
    <el-menu :default-active="$route.path" class="el-menu-vertical-demo">
      <el-menu-item v-for="route in $router.options.routes" :key="route.path" :index="route.path" v-if="!route.hidden">
        <i :class="`el-icon-${route.meta.icon}`"></i>
        <span slot="title">{{ route.meta.title }}</span>
      </el-menu-item>
    </el-menu>
  </div>
</template>

<script>
export default {
  name: 'Layout'
}
</script>
```

这个模板会根据路由配置自动生成菜单项，因此我们不需要在这里做额外修改。

### 结语

通过以上步骤，添加新的页面和 API 接口，并将它们集成到项目中。

# ----------------

# 4. Vuex 备注

### Vuex 的作用

Vuex 是一个专为 Vue.js 应用程序开发的状态管理模式。它采用集中式存储管理应用的所有组件的状态，并以相应的规则保证状态以一种可预测的方式发生变化。Vuex 提供了一个机制来在组件之间共享状态，使状态管理更加规范和可维护。

备注：`src/store`目录中找到 Vuex 的模块文件，通常会有一个 `app.js` 或 `menu.js` 模块来管理应用的状态。这就是Vuex的模块文件。

### 仅仅是改动一个菜单栏的 Vue 组件，是否需要改动 Vuex？

如果你只是改动菜单栏的 Vue 组件，例如修改菜单项的显示内容、布局或样式，通常 **不需要** 修改 Vuex（`app.js` 或 `permission.js`）。

**结论**：Vuex 在本项目中不做改动。



### 结语

通过上述开发手册，我门可以对 `woniu-mall-app-web` 项目的结构和各个模块有一个全面的了解，并根据需求对具体组件和 API 进行修改。
