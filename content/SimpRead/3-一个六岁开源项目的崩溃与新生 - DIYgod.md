---
url: https://diygod.cc/6-year-of-rsshub
title: 一个六岁开源项目的崩溃与新生 - DIYgod
date: 2024-09-19 19:28:26
tag: 
banner: "https://raw.githubusercontent.com/DIYgod/sponsors/main/sponsors.wide.svg"
banner_icon: 🔖
---
我有一个维护了六年的开源项目 —— RSSHub，它正在面临崩溃

## 背景[#](#user-content-背景)

表面上，它有接近 30k Stars、900 多 Contributors、每月 3 亿多次请求和数不清的用户、每月几十刀的赞助、有源源不断的 issue 和 pr、代码几乎每天更新，非常健康和充满活力，但在不可见的地方，持续数年高昂的维护时间成本、每月一千多刀的服务器费用、每天重复繁琐且逐渐积累的维护工作，都让它在崩溃的边缘反复横跳

项目是六年前开发的，不少当时以 Next Generation 为口号的时髦 Node.js 技术栈和依赖库已经成为时代眼泪，现在看非常陈旧，很多现在流行的新技术没法应用，比如 JSX、TypeScript、Serverless 等；它的架构也非常不合理，每个路由的信息散落在多个地方，开发或者变更一个路由需要多处修改，一个地方去注册路由，一个地方去编写路由脚本，一个地方去编写 Radar 规则，一个地方去编写文档...... 这增加了很多工作量，也很容易出错，之前路由少的时候并不是个问题，但现在已经变得难以忍受

在如此糟糕的基础架构下能保持现状已经是竭尽全力，开发新功能更是无本之木，只会增加以后更新的难度，所以我有时候脑子蹦出的新奇想法也很难实现

要解决这些问题，唯一的办法是使用现代化的框架和新设计的架构来重写内核，但随着路由越来越多，改造成本也越来越高，每个基础改动可能都需要多达数月的工作量，所以虽然问题越来越严重，但秉承着又不是不能用的原则一拖再拖

但这又是不得不做的事情，所以我抽空花了几个月的时间重新设计和重写了它

## 技术栈更新[#](#user-content-技术栈更新)

### koa -> Hono[#](#user-content-koa---hono)

第一步也是最基础和难度最大的是换掉之前使用的 Web 框架 [koa](https://github.com/koajs/koa)，作为六年前流行的下一代 Web 框架，作者早就弃坑了，调研之后决定换用对 JSX、TypeScript、Serverless 支持最好的 [Hono](https://github.com/honojs/hono)

它们的 API 差异很大，需要重写所有中间件和替换所有路由中使用的 koa API

主要改动：  
[https://github.com/DIYgod/RSSHub/pull/14295](https://github.com/DIYgod/RSSHub/pull/14295)

![[SimpRead/_resources/3-一个六岁开源项目的崩溃与新生 - DIYgod/6c8824dfe8f5c1da0178a51143cd0d08_MD5.webp]]

Hono 作者也很喜欢这个改造

### JavaScript -> TypeScript[#](#user-content-javascript---typescript)

改用 TypeScript 可以避免很多类型问题和低级错误，最重要的是可以保证数百名贡献者保持一致难以出错和后续贡献的路由代码质量不至于太糟糕

主要改动：

*   [https://github.com/DIYgod/RSSHub/pull/14295](https://github.com/DIYgod/RSSHub/pull/14295)
*   [https://github.com/DIYgod/RSSHub/pull/14632](https://github.com/DIYgod/RSSHub/pull/14632)

![[SimpRead/_resources/3-一个六岁开源项目的崩溃与新生 - DIYgod/904b46a0f388b91d9790dc0e38461861_MD5.webp]]

### CommonJS -> ESM[#](#user-content-commonjs---esm)

ESM 是几年前一些 Node.js 核心开发者强推的规范，它有一些优点，但最多的是与之前 CommonJS 不兼容带来的生态割裂和功能简化带来的诟病

经过这几年的发展，现在可以说大部分场景勉强可用了，[tsx](https://github.com/privatenumber/tsx) 也为 CommonJS 和 ESM 混用的场景提供了支持

虽然已经尽了最大努力，但还是有一些 CommonJS 代码暂时难以迁移，导致现在只能使用 tsx 运行，与一些 Serverless 比如 Vercel 没法兼容，但也有机会后续慢慢解决

主要改动：

*   [https://github.com/DIYgod/RSSHub/pull/14619](https://github.com/DIYgod/RSSHub/pull/14619)
*   [https://github.com/DIYgod/RSSHub/pull/14691](https://github.com/DIYgod/RSSHub/pull/14691)
*   [https://github.com/DIYgod/RSSHub/pull/14632](https://github.com/DIYgod/RSSHub/pull/14632)

![[SimpRead/_resources/3-一个六岁开源项目的崩溃与新生 - DIYgod/474967888aef7ccc3f2e953316f405d8_MD5.webp]]

![[SimpRead/_resources/3-一个六岁开源项目的崩溃与新生 - DIYgod/0e62c25555a1f243cc4b8baf5eeccba2_MD5.webp]]

### art-template -> JSX[#](#user-content-art-template---jsx)

[art-template](https://github.com/aui/art-template) 是一个支持 koa 的模板引擎，记得六年前还有一个更流行的模板引擎，但是不记得名字了，选用 art-template 是因为那个更流行的我当时没看懂，这个很简单

Hono 自带了 JSX 支持，JSX 就不用多介绍了，根正苗红的 JavaScript 的语法扩展，等同于用 React

主要改动：

*   [https://github.com/DIYgod/RSSHub/commit/3bfdf9427cb8cf063cf7d231ec621278495f5a44](https://github.com/DIYgod/RSSHub/commit/3bfdf9427cb8cf063cf7d231ec621278495f5a44)
*   [https://github.com/DIYgod/RSSHub/commit/94cf0742afa8bf18510ad9ded9b76dcd2ad52c90](https://github.com/DIYgod/RSSHub/commit/94cf0742afa8bf18510ad9ded9b76dcd2ad52c90)

### Jest -> Vitest[#](#user-content-jest---vitest)

Jest 是曾经流行的测试框架，但是在 ESM 时代到来之后就越来越不行了，对 ESM 的支持一直是实现性「experimental support」，现在更流行的是 Vitest 了

主要改动：  
[https://github.com/DIYgod/RSSHub/commit/38e42156a0622a2cd09f328d2d60623813b8df28](https://github.com/DIYgod/RSSHub/commit/38e42156a0622a2cd09f328d2d60623813b8df28)

### Got -> ?[#](#user-content-got---)

目前使用的 [Got](https://github.com/sindresorhus/got) 也已经是不积极维护的状态了，也没有找到好的替代品，后续也许会换成原生 Fetch 或者自封装的 Fetch，还没有动手

## 新路由标准[#](#user-content-新路由标准)

我自己能力还是不够的，在与社区开发者们讨论的过程中学习和改进了很多，过程很有意思：[https://github.com/DIYgod/RSSHub/issues/14685](https://github.com/DIYgod/RSSHub/issues/14685)

主要改动：  
[https://github.com/DIYgod/RSSHub/pull/14718](https://github.com/DIYgod/RSSHub/pull/14718)

![[SimpRead/_resources/3-一个六岁开源项目的崩溃与新生 - DIYgod/f20a090703037f7736f31a03b12d2f84_MD5.webp]]

### 历史[#](#user-content-历史)

新标准主要为了解决路由信息过于分散的问题，这次应该算第三版

第一版来自 RSSHub 开发阶段，当时没有预见到路由数量会有这么多，所以几乎没什么规划，所有路由在同一个文件中注册，然后再去增加路由脚本和文档，后来这个文件越来越大，很容易冲突，另外所有路由脚本都会在启动阶段被加载，程序性能越来越差

第二版来自 [NeverBehave](https://github.com/NeverBehave) 维护的时期，引入了命名空间，切割了 router.js、radar.js，同命名空间的路由集中在了一个同文件夹中和一个或多个 Markdown 文档中，还实现了懒加载，极大提升了可维护性和性能，但还是会分散在多个文件中，不同文件的信息也容易出现不一致导致错误

### 现在[#](#user-content-现在)

本次把路由文件分为了两类，namespace.ts 和任意名字的路由文件

namespace.ts 会通过导出名为 namespace 的对象来定义命名空间的信息

```
import type { Namespace } from '@/types';

export const namespace: Namespace = {
    // ...
};



```

namespace 包含的字段通过 TypeScript 限制为

```
interface Namespace {
    name: string;
    url?: string;
    categories?: string[];
    description?: string;
}


```

这些信息会经过编译后被文档和 RSSHub Radar 利用

路由文件会通过导出名为 route 的对象来定义路由的信息

```
import { Route } from '@/types';

export const route: Route = {
    // ...
};


```

route 包含的字段通过 TypeScript 限制为

```
interface Route {
    path: string | string[];
    name: string;
    url?: string;
    maintainers: string[];
    handler: (ctx: Context) => Promise<Data> | Data;
    example: string;
    parameters?: Record<string, string>;
    description?: string;
    categories?: string[];

    features: {
        requireConfig?: string[] | false;
        requirePuppeteer?: boolean;
        antiCrawler?: boolean;
        supportRadar?: boolean;
        supportBT?: boolean;
        supportPodcast?: boolean;
        supportScihub?: boolean;
    };
    radar?: {
        source: string[];
        target?: string;
    };
}


```

之前 route.js mantainer.js radar.js 和文档的信息都被集中在这一个文件中，减少了多处定义也减少了出错的可能

### 实现[#](#user-content-实现)

实现逻辑就是开发环境通过遍历整个 route 文件夹，找到所有 namespace.ts 和路由文件，读取信息，加载路由，在生成环境使用提前编译好的路径列表来避免遍历和不必要的加载过程，代码在：[https://github.com/DIYgod/RSSHub/blob/master/lib/registry.ts](https://github.com/DIYgod/RSSHub/blob/master/lib/registry.ts)

文档也是通过遍历 route 文件夹，找到所有需要的信息然后合成一系列的 Markdown 文件，不再需要手动维护，代码在：[https://github.com/DIYgod/RSSHub/blob/master/scripts/workflow/build-routes.ts](https://github.com/DIYgod/RSSHub/blob/master/scripts/workflow/build-routes.ts)

当然使用之前路由标准开发的路由都需要迁移到新标准而不是直接放弃掉，已经通过脚本批量抓取整理信息后做了替换，但特别是文档比较混乱也有很多错误，所以抓取的信息也有很多错误，只能在后续逐渐人工修改了

## 未来[#](#user-content-未来)

通过这一系列改进，RSSHub 终于能够扔掉历史包袱，安心开发新功能了，这里列出我积累的一些想法抛砖引玉：

*   既然 RSSHub 是一个数据集合，用途不一定只有 RSS，JSON 输出功能可以做一些增强，作为通用的 RESTful API 来使用，比如可以提供获取下一页接口或者输出类似 Twitter 关注数的非 feed 数据
*   用户系统和用户自定义配置，生成自己的私有订阅地址 [#14706](https://github.com/DIYgod/RSSHub/issues/14706)
*   路由错误通知和健康度检测 [#14712](https://github.com/DIYgod/RSSHub/issues/14712)
*   与 RSS3 节点的联动和加密货币收益共享 [https://twitter.com/rss3_/status/1731822029199094012](https://twitter.com/rss3_/status/1731822029199094012)
*   AI 翻译和摘要
*   更详细的实例数据分析及反向推导自动推荐的 Radar 规则
*   与本地浏览器或客户端绑定的 RSSHub 实例，有希望真正解决反爬难题
*   ...

最后，开源是一件很昂贵的事情，RSSHub 能活到现在离不开这些开发者的帮助

[![[SimpRead/_resources/3-一个六岁开源项目的崩溃与新生 - DIYgod/98008aa3d533cfe14da22f58d7402b75_MD5.png]]](https://github.com/DIYgod/RSSHub/graphs/contributors)

以及这些赞助的好心人

[![[SimpRead/_resources/3-一个六岁开源项目的崩溃与新生 - DIYgod/40344f7c3174a230c30e999ff82c0b92_MD5.svg]]](https://github.com/DIYgod/sponsors)

如果 RSSHub 正在帮助你，也希望你可以积极参与进来，为信息自由的未来贡献一份自己的微小力量