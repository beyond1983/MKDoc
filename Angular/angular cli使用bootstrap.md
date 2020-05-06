## angular cli使用bootstrap

> angular是去jQuery化的，所以常规的直接引用css、js的做法在angular cli中是不推荐的做法。下面详细说明在angular cli下的推荐用法。

1. 使用npm安装bootstrap，此步是为了引用bootstrap的css

```powershell
npm install bootstrap
```

2. 使用npm安装angular-bootstrap

```powershell
npm install --save @ng-bootstrap/ng-bootstrap
```

3. 引用bootstrap样式

> 在应用根路径下的styles.css文件中添加样式引用

```css
@import '~bootstrap/dist/css/bootstrap.css';
```

4. 全局引用bootstrap组件

>在app.mudule.ts文件中添加引用

```typescript
import {NgbModule} from '@ng-bootstrap/ng-bootstrap';
```

> 导入组件，其它自定义组件即可使用bootstrap组件

```typescript
@NgModule({
  declarations: [AppComponent, ...],
  imports: [NgbModule, ...],  
  bootstrap: [AppComponent]
})
export class AppModule {
}
```

