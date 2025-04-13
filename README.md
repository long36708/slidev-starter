# Welcome to [Slidev](https://github.com/slidevjs/slidev)!

开始幻灯片播放:

- `pnpm install`
- `pnpm dev`
- 访问 <http://localhost:3030>

编辑 [slides.md](./slides.md) 查看变化.

了解更多关于Slidev的信息 [documentation](https://sli.dev/).

https://cn.sli.dev/custom/#headmatter

# 常用技巧总结

## 颜色

### 字体颜色

绿色字体
```vue
 <span font-hand text-1.2em text-green v-click>Made Easy</span>
```

紫色字体
```vue
 <span flex="~ gap-2 items-center" text-hex-8080f2>
    <div i-logos-eslint />
    ESLint
  </span>
```

## 字体
### 加粗

`b`标签为加粗标签

```markdown
<b v-click font-800>Formatter</b>
```
## 点击进入下一页

```vue

<div @click="$slidev.nav.next" class="mt-12 py-1" hover:bg="white op-10">
  Press Space for next page
  <carbon:arrow-right/>
</div>
```

## 目录

```vue

<Toc text-sm minDepth="1" maxDepth="2"/>
```

## 点击一个个的出现

```
<v-clicks>
<div abs-br mx-50 mb-22> ^1.0.0 、~1.0.0 、 >=1.0.0 有什么区别？ </div>
<div abs-tr mt-32 mr-30> 指定版本和安装版本一定相同吗？ </div>
<div abs-tl mt-82 ml-30> 语义化版本和依赖版本的区别？ </div>
</v-clicks>

```

## bash

```markdown
<div mt-4 />
<v-click>

    ```bash
    eslint --inspect-config
    ```

</v-click>
<div mt-4 />
```
## v-mark 下划线或者圈出文字

https://cn.sli.dev/features/rough-marker#v-mark-%E6%8C%87%E4%BB%A4

> 绿色下划线，标识出 `Powerful and customizable as ESLint.`
```vue
<div v-click class="slidev-vclick-target">
  <div i-ph-check-circle-duotone text-green inline-block translate-y-2px />
  
  <span v-mark.green.delay400="5">
    Powerful and customizable as ESLint.
  </span>
</div>

```

圈出`版本范围`

```markdown
<div v-mark.circle.red w-30 text-green v-drag absolute right-65> 版本范围</div>
```

一定要设置延迟时间以及=点击数时触发，否则定位可能不对
```markdown
<div v-click>

**语义化版本** 不仅仅局限于前端开发，而是一个<div inline-block v-mark.orange.delay600="4">广泛应用于软件管理领域</div>的一个概念。

</div>
```

## github 图标

```vue
  <a href="https://github.com/slidevjs/slidev" target="_blank" class="slidev-icon-btn">
  <carbon:logo-github/>
</a>
```

或者

```vue

<div i-simple-icons-github/>
```

npm 图标

```text
<div w-60 text-10em i-logos-npm></div>
<div w-60 text-10em i-devicon-npm-wordmark></div>
```

## 所有字母转大写

```vue

<div uppercase tracking-widest op50>
  Anthony Fu
</div>
```

## 基线上下的文字

sup 表示基线之上

```text
# 版本范围 <sup op-50>Version Range</sup>
```

sub 表示基线之下

```text
# 版本范围 <sub op-50>Version Range</sub>
```

### 右上角紫色字，背景浅紫色
```md
## Config Inspector <sup text-purple bg-purple:15 px1.5 rounded text-sm>Official</sup>
```

### 右上角绿色字，背景浅绿色

```md
## Flat Config Utils <sup text-teal bg-teal:15 px1.5 rounded text-sm>Community</sup>
```
## 将 do 划掉 改为 try to

```vue
<h1 class="text-5xl!" v-click="1" w-200>I <span transition-all duration-300
                                                :class="$clicks === 4 ? 'line-through op50' : ''">do</span> <span
    v-click="4">try to</span></h1>
<h1 class="text-5xl! font-bold" v-click="2">Inbox-Zero</h1>
<h1 class="text-5xl!" v-click="3">Everyday</h1>
```

## 删除线

先给出一个错误的概念，然后进行否定

```vue
---
layout: fact
glowY: 120
glowSize: 1.5
clicks: 1
---

<h1 :class="$clicks === 1 ? 'line-through op50!' : ''"><span text-transparent text-8xl bg-clip-text bg-gradient-to-r
                                                             from-rose-400 to-pink-600>TURN OFF</span> Notifications
</h1>

<p :class="$clicks === 1 ? 'line-through op20!' : ''">and call it a day</p>
```

```vue
---
layout: center
glowX: 50
glowY: 35
glowSize: 0.6
clicks: 2
---

<div flex="~ col items-center gap-2" p4>
  <div v-click="1" :class="$clicks >= 2 ? 'line-through op50' : ''" transition>Vue 专用工具</div>
  <div i-carbon-arrow-down op50 v-click="2"/>
  <div v-click="2">框架无关的前端工具链</div>
</div>
```

## 数字背景

用于分点描述,例如第一点，第二点...

```vue
---
layout: fact
glowX: 50
glowY: 0
glowSize: 1.5
---

# 减少通知的创建
投稿指南、发行表格/模板等

<div class="number-bg">0</div>
```

```vue
---
layout: fact
glowX: 50
glowY: 0
glowSize: 1.5
---

# 寻求通知
不要让他们来找你

<div class="number-bg">1</div>
```

```vue
---
layout: fact
glowX: 0
glowY: 50
glowSize: 1.5
---

# 将通知分组
按存储库，而不是按时间

<div class="number-bg">2</div>
```

```vue
---
layout: fact
glowX: 90
glowY: 90
glowSize: 1.5
---

# 关注什么
过滤掉杂音，分清轻重缓急

<div class="number-bg">3</div>
```

## 图片

```vue
<img src="/dot-github-repo.png" w-100 rounded-md border="~ main"/>
```

纯图片展示

```vue
---
layout: center
---

![](/i18n-ally-hover.png){.h-100.contrast-110}
```

```vue
<v-clicks>

![](/eslint-typegen.png){.w-200.rounded-lg.shadow.border.border-main}

</v-clicks>
```
## 视频

```vue

<VideoDemo src="/devtools/0-intro.mp4" mt--2/>
```

```vue
<video src="/eslint-plugin-command-half.mov" mt-4 w-130 saturate-110 rounded shadow border="~ main" controls />
```
## 表格
```vue
<div scale-75 origin-left-top mb--28 mt--3 class="[&_td]:py1 [&_table]:w-130%" v-click="2">
  <v-clicks>

    | Language | Plugin | Maintainers |
    | --- | --- | --- |
    | <span i-logos-typescript-icon inline-block align-middle /> TypeScript | [`@typescript-eslint`](https://typescript-eslint.io) | {@typescript-eslint} {@bradzacher} {@JoshuaKGoldberg} |
    | <span i-logos-vue inline-block align-middle /> Vue | [`eslint-plugin-vue`](https://github.com/vuejs/eslint-plugin-vue) | {@ota-meshi} {@vuejs} |
    | <span i-logos-svelte-icon inline-block align-middle /> Svelte | [`eslint-plugin-svelte`](https://github.com/sveltejs/eslint-plugin-svelte) | {@ota-meshi} {@sveltejs} |
    | <span i-logos-astro-icon invert hue-rotate-180 inline-block align-middle /> Astro | [`eslint-plugin-astro`](https://github.com/ota-meshi/eslint-plugin-astro) | {@ota-meshi} |
    | <span i-logos-json invert inline-block align-middle /> JSON | [`eslint-plugin-jsonc`](https://github.com/ota-meshi/eslint-plugin-jsonc) | {@ota-meshi} |
    | <span i-vscode-icons-file-type-light-yaml inline-block align-middle /> YAML | [`eslint-plugin-yml`](https://github.com/ota-meshi/eslint-plugin-yaml) | {@ota-meshi} |
    | <span i-logos-toml invert hue-rotate-180 inline-block align-middle /> TOML | [`eslint-plugin-toml`](https://github.com/ota-meshi/eslint-plugin-toml) | {@ota-meshi} |
    | <span i-logos-graphql inline-block align-middle /> GraphQL | [`graphql-eslint`](https://github.com/dimaMachina/graphql-eslint) | {@dimaMachina} |
    | <span i-vscode-icons-file-type-html inline-block align-middle /> HTML | [`html-eslint`](https://github.com/yeonjuan/html-eslint) | {@yeonjuan} |
    | <span i-vscode-icons-file-type-mdx inline-block align-middle /> MDX | [`eslint-mdx`](https://github.com/mdx-js/eslint-mdx) | {@JounQin} |
    | <span i-logos-prettier inline-block align-middle /> Other formats* | [`eslint-plugin-format`](https://github.com/antfu/eslint-plugin-format) | {@antfu} |

  </v-clicks>
</div>
```

## 箭头

```vue

<Arrow x1="600" y1="200" x2="550" y2="75" text-lime shadow v-if="$clicks === 1"/>
```

右箭头

表示左边变到右边

```vue

<div i-carbon-arrow-right text-xl op50 v-click/>
```

```vue
---
glowX: 110
glowY: -10
clicks: 2
---

<img absolute left-10 top-10 v-click="0" src="/notifications-raw.png" w-150 mix-blend-plus-lighter/>
<Arrow x1="600" y1="200" x2="550" y2="75" text-lime shadow v-if="$clicks === 1"/>
<img absolute left-10 top-10 v-click="2" src="/notifications-grouped.png" w-150/>
```

箭头指向图上的折线图的点

```vue
---
layout: center
glow: topmost
---

![](/stars.png){.w-150.mix-blend-lighten}


:arrow{x1=316 y1=285 x2=345 y2=375 width=1.2 .text-amber v-click=""}
"重写"{.absolute.left-72.top-61.text-amber.text-sm v-after}
```

## 强调某个单词

```vue
<b text-hex-a371f7>Colorize</b> notifications type
```

## 渐变色

```vue

<div text-5xl mt3 v-click text-transparent bg-clip-text bg-gradient-to-r from-yellow via-green
     to-blue>优秀软件的关键</div>
```

## 文字右上角显示`实验性`浅色标识

```vue
- <img src="/pheno.png" h-2em w-2em inline-block align-middle scale-130 mr2/> <a
    href="https://github.com/pheno-agency/vite-plugin-devtools">pheno-agency/vite-plugin-devtools</a> <sup op50>experimental</sup>
```

## 词云

开始中央显示出一个中心词

然后每次按一下，出来一个关键词

再然后，每次按下出来多个次要词

```vue
---
layout: center
glowX: 50
glowY: 50
---

<h1 font-bold class="text-5xl!">Developer Experience</h1>

<div absolute left-100 top-80 v-click>File-based Routing</div>
<div absolute left-52 top-50 v-click>Modules Ecosystem</div>
<div absolute left-100 top-50 v-click>Hot Module Replacement</div>
<div absolute left-50 top-80 v-click>Server-side Rendering</div>

<v-click>

  <div absolute left-158 top-50>Nitro</div>
  <div absolute left-145 top-80>ESM First</div>
  <div absolute left-170 top-80>Vite Powered</div>
  <div absolute left-60 top-90 op80>Zero-config</div>
  <div absolute left-90 top-90>Edge Rendering</div>

</v-click>
<v-click>

  <div absolute left-85 top-40>Hybrid Rendering</div>
  <div absolute left-130 top-90>Components Auto Imports</div>
  <div absolute left-125 top-40 op70>Composables Auto Imports</div>
  <div absolute left-55 top-40 op70>Middleware</div>
  <div absolute left-175 top-50 op70>SEO</div>

</v-click>
<v-click>

  <div absolute left-145 top-100 op60>Server API</div>
  <div absolute left-100 top-30 op70>Serverless</div>
  <div absolute left-70 top-30 op70>TypeScript</div>
  <div absolute left-130 top-30 op70>Server Components</div>
  <div absolute left-120 top-100 op70>Layouts</div>
  <div absolute left-70 top-100 op60>Static Site Generation</div>

</v-click>
```

### 强调特性

自动展示 词云

```
---
layout: center
glowX: 50
glowY: 100
---

<FeatureList />
```

## 项目图标列表

```vue
---
glowX: 100
glowY: 50
---

# Community Modules

已经集成了next DevTools 的开源项目

<ModulesIcons/>
```

## 单词变灰动效

```vue

<div v-click transition-all duration-500
     :class="$clicks === 0 ? 'op0' : $clicks > 1 ? 'op50 text-2xl' : 'translate-y-10 text-4xl'">Introducing
</div>
```

## 1.0 版本 发布推出

```vue

<div class="springing" v-click relative>
  <div
      text-25em font-900 font-number
      op20 z--1 pos="absolute left-1/2 top-3/10" translate="x--1/2 y--8.5/15"
  ><span>1.0</span></div>
</div>
```

## 数字说明

比如某个npm包的使用情况

```vue
---
glowX: 100
glowY: 100
class: ml-20 mt-5
---

## State of Nuxt DevTools

###### As of October 10th, 2023

<div grid="~ cols-[auto_1fr] gap-x-4 gap-y-2" items-center my6>
  <v-clicks :every="2">
    <div text-right text-4xl font-bold color="[#BD3E53]">504K</div>
    <div text-left text-lg op80>Monthly downloads on NPM</div>
    <div text-right text-4xl font-bold color="[#BD7C3E]">24%</div>
    <div text-left text-lg op80>Downloads of Nuxt 3</div>
    <div text-right text-4xl font-bold color="[#A9BD3E]">16K</div>
    <div text-left text-lg op80>Open Source projects dependents</div>
    <div text-right text-4xl font-bold color="[#54BD3E]">2.3K</div>
    <div text-left text-lg op80>Stars on GitHub</div>
    <div text-right text-4xl font-bold color="[#3EBD7C]">18</div>
    <div text-left text-lg op80>Builtin tabs</div>
    <div text-right text-4xl font-bold color="[#3EAABD]">53</div>
    <div text-left text-lg op80>Contributors</div>
    <div text-right text-4xl font-bold color="[#3E55BD]">20+</div>
    <div text-left text-lg op80>Nuxt Modules integrates Nuxt DevTools</div>
  </v-clicks>
</div>
```

## Demo time

```vue
---
layout: center
class: text-center
glowX: 50
glowY: 50
glowSize: 0.4
---

<h1>Demo time!</h1>
```

## Q&A

```vue
---
layout: center
class: text-center
glowX: 50
glowY: -20
---

# Q&A
```

## 以感谢结束

```vue
---
layout: intro
class: text-center pb-5
glowX: 50
glowY: 120
---

# Thank You!
```

## 布局

### 距离上方4px

用于控制上下间距
```markdown
<div mt-4 />
```

### 一行文字+图标
```vue
<div flex="~ gap-2 items-center">
  Configs in <div i-logos-visual-studio-code inline-block /> VS Code
</div>
```
star图标 + 文字
```vue
<span flex="~ inline gap-0.5 items-center" text-amber bg-amber:15 px1 rounded text-xs><div i-carbon-star-filled text="[0.8em]" /> 4.1k</span>
```

一行 紫色图标+文字
```vue
<span flex="~ gap-2 items-center" text-hex-8080f2>
    <div i-logos-eslint />
    ESLint
</span>
```
### 左上角标题+下边一行灰色图标+字
```vue
---

# Project-aware Configs

<div text-gray flex="~ items-center gap-1" v-click>
Example: <div i-logos-nuxt-icon inline-block /> Nuxt ESLint
</div>
```

### 左上角标题 

```md
# <span op50>ESLint can be a...</span> <b v-click font-800>Codemod</b>
```

### 中间二行文字

```vue
---
layout: fact
---

# One for All{.important-text-3em}
One config for all projects
```
### 一列居中
```markdown
---
layout: center
glow: bottom
---

<div flex="~ col items-center justify-center w-full">
  
</div>
```
### 上下布局

```vue
<div flex="~ col items-center justify-center">
  <img src="/eslint-stylistic.png" w-80 v-click />

  <div op75 text-lg v-click>
    Collection of stylistic ESLint rules.<br>Formatting and linting in one go.
  </div>

  <a href="https://eslint.style" text-sm v-click>eslint.style</a>
</div>7
```
### 左右布局

```text
---
layout: two-cols
layoutClass: important-p0
---

我是`左`侧的内容
 
::right::

<div>
 我是右侧的内容
</div>
```
#### 使用 grid + cols-2
```vue
<div grid="~ cols-2 gap-8">
  <div flex="~ col gap-2">
    ### Legacy Config
    ```json {*|3-7|*|10-14|*}{at:1}
    ```
  </div>

  <div flex="~ col gap-2">
    ### Flat Config

    ```ts {*|4-5|*|6-8|*}{at:1}
    ```

    <div flex="~ col gap-2" mt-3>
      <div v-click class="slidev-vclick-target" :class="$clicks === 1 ? 'text-green' : ''">
        <div i-ph-check-circle-duotone text-green inline-block translate-y-2px />
        Shared configs can take user options.
      </div>
    </div>  
  </div>
</div>
```
#### 自定义高度
- 左侧是图片+网站链接，上下布局
- 右侧是代码片段
- 同时具有动效，先将左侧的内容居中显示，然后左侧的内容居左2，右侧的内容显示出来
```vue
<div grid="~ cols-2 gap-4" h="80%">
  <div
      v-click="1"
      flex="~ col gap-2 items-center justify-center"
      transition duration-500
      :class="$clicks < 2 ? 'scale-130 translate-x-55' : ''"
  >
    <img src="/nuxt-eslint.png" w-90 rounded-lg shadow border="~ main" />
    <a href="https://eslint.nuxt.com" text-sm>eslint.nuxt.com</a>
  </div>
  
  <div flex="~ col items-center justify-center" forward:delay-500 pb-10 v-click>

    ```ts
    // Generated by Nuxt based on your project
    import withNuxt from './.nuxt/eslint.config.mjs'
    
    export default withNuxt(
      // your custom config goes here
    )
    ```
    
    </div>
</div>
```

#### 左右布局
```vue
---
class: "grid grid-cols-[1fr_1fr] p0 h-full"
clicks: 1
glow: left
---

<div p4 flex="~ col gap-1 items-center justify-center" transition duration-500 :class="$clicks >= 1 ? '' : 'translate-x-65'">

</div>

<div
    bg-hex-5552 p8 border="l main" transition duration-500
    :class="$clicks >= 1 ? '' : 'translate-x-100%'"
>
</div>
```
### 左中右布局

> 左侧变到右侧，中间是向右的箭头

```
<div grid="~ cols-[1fr_max-content_1fr] gap-4" mt-4 v-click>

    ```json
    // .eslintrc.json
    ```

<span i-carbon:arrow-right mt-40 />

    ```js
    // eslint.config.mjs
    ```

</div>
```

> `cols-[1fr_max-content_1fr]`:
    - 定义三列布局：
     - 第一列和第三列各占剩余空间的一部分（1fr）。
     - 第二列宽度由内容决定（max-content）

> gap-4:
  设置网格行与列之间的间距为 16px。  

```vue
<div grid="~ cols-[1fr_max-content_1fr] gap-4" mt2>
<div v-click>

    ```ts {*|*|7-9|10-17}{at:3}
        
    
    // (pesudo code for demo)
    ```

</div>
<span i-carbon:arrow-right ma v-click />
<div v-after>
  
    ```ts {*|1,7|8-10|11-21}{at:3}
    
    ```
</div>
</div>
```
### 右下角图片+日期

```vue
<div abs-br mx-10 my-11 flex="~ col items-center" text-left>
  <img src="/reactdayberlin.svg" alt="React Day Berlin" w30 mb1/>
  <div text-xs opacity-75>December 16, 2024</div>
</div>
```
### 缩放

整体缩放到70%,以左上角为中心2，指定宽度，距离下方 -100px,距离右侧 -40px
```vue
<div scale-70 origin-left-top w-160 mb--100 mr--40>

</div>
```

### iframe

```
<iframe v-click src="https://nuxt.com/modules?sortBy=downloads&version=3.x"
  onload="this.style.visibility = 'visible';"
  scale-50 origin-top-right absolute right-0 top-0 bottom-0 w="140%" h="200%"
  style="mix-blend-mode: lighten;filter:contrast(1.15);visibility:hidden;"
/>
```
## monaco

```vue
<v-click>

  <<< ./eslint.demo.config.ts {monaco-write}{height:'220px'}

</v-click>

<div v-show="false">
<!-- This block is for type discovery -->
    ```ts {monaco}
    import antfu from '@antfu/eslint-config'
    ```
</div>
```

## 动画特效

### 点击一下，一行变绿

```vue
 <div flex="~ col gap-2" mt-3>
  <div v-click class="slidev-vclick-target" :class="$clicks === 1 ? 'text-green' : ''">
    <div i-ph-check-circle-duotone text-green inline-block translate-y-2px />
    Shared configs can take user options.
  </div>
  <div v-click class="slidev-vclick-target" :class="$clicks === 2 ? 'text-green' : ''">
    <div i-ph-check-circle-duotone text-green inline-block translate-y-2px />
    One single config, adapts to all projects.
  </div>
</div> 
```

### 先出一行，然后第一行向上移动，变两行，

```markdown
<h2 flex="~ col" text-center>
<div text-center flex="~ col gap-2" transition duration-500 :class="$clicks < 2 ? 'translate-y-40' : ''">
  <span
    flex="~ gap-2 items-center justify-center"
    text-hex-8080f2 transition duration-500 text-1.5em
    :class="$clicks <  1 ? 'scale-150 translate-y' : ''"
  >
    <div i-logos-eslint />
    ESLint v9.0.0
  </span>
  <span v-click op75 forward:delay-400 text-2xl>released <TimeAgo date="2024-04-05" /></span>
</div>
</h2>
```

### 中间先出一个居中显示，然后调整到左侧，然后右侧显示出来

```markdown
<div grid="~ cols-2 gap-4" h="80%">
<div
  v-click="1"
  flex="~ col gap-2 items-center justify-center"
  transition duration-500
  :class="$clicks < 2 ? 'scale-130 translate-x-55' : ''"
>
  <img src="/nuxt-eslint.png" w-90 rounded-lg shadow border="~ main" />
  <a href="https://eslint.nuxt.com" text-sm>eslint.nuxt.com</a>
</div>

<div flex="~ col items-center justify-center" forward:delay-500 pb-10 v-click>

    ```ts
    // Generated by Nuxt based on your project
    import withNuxt from './.nuxt/eslint.config.mjs'
    
    export default withNuxt(
      // your custom config goes here
    )
    ```

</div>
</div>
```
