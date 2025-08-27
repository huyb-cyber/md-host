\## 介绍：

Android 文档：[https://github.com/wendux/DSBridge-Android](https://github.com/wendux/DSBridge-Android)<br />IOS 文档：[https://github.com/wendux/DSBridge-IOS](https://github.com/wendux/DSBridge-IOS)<br />H5桥接测试地址：[https://testh5.transspay.net/next-cli/bridge](https://testh5.transspay.net/next-cli/bridge)<br />来源：统一采用第三方的 dsBridge 接入，进行二次封装<br />统一注册唯一桥接方法：**bridgeToNative**， 示列：

\```javascript

dsBridge.call(

  "bridgeToNative", {    

​    "group" : "storage",

​    "id" : "get",

​    "args" : {

​      "key" : "sp_token"

​    }

  }, function (v) { })

\```

二次封装，统一暴露桥接对象 **PPBridge**，示例：

\```javascript

const response =  await PPBridge.getAppInfo(null)

const headers = response.entry || {}

\```

\## 目录：

PS： 划线的，暂不在一期实现。

| **序号** | **分组** | **桥接方法** | **桥接描述** | **平台** | **图片** |

| --- | --- | --- | --- | --- | --- |

| 1 | 本地缓存 | PPBridge.getPreferences(params) | 获取本地缓存 |  |  |

| 2 |  | PPBridge.setPreferences(params) | 存储本地缓存 |  |  |

| 3 | 基础信息 | PPBridge.getAppInfo(params) | 获取 App 信息 |  |  |

| 4 |  | PPBridge.getUserInfo() | 获取当前用户信息 |  |  |

| 5 |  | PPBridge.getContactInfo() | 获取通讯录联系人信息 |  |  |

|  |  | PPBridge.getVersion() | 获取 App 版本信息 |  |  |

| 6 | 图片 | PPBridge.uploadPhoto(params) | 上传图片 | 主要给RN |  |

| 7 |  | PPBridge.savePhoto(params) | 保存图片至相册 |  |  |

| 8 | 跳转 | PPBridge.openPage(params) | 跳转页面 |  |  |

| 9 |  | ~~PPBridge.~~~~backPage~~~~()~~ | ~~Webview 返回上一级~~ | 废弃 |  |

| 10 |  | PPBridge.closePage() | 关闭 Webview |  |  |

| 12 |  | PPBridge.openBroswer(params) | 端外默认浏览器打开页面 |  |  |

| 13 |  | PPBridge.upgrade() | 升级 App: 跳转 App 商城页面 |  |  |

| 14 |  | PPBridge.openChat(params) | 打开客服 Chat |  |  |

| 15 |  | PPBridge.openFaceCapture(params) | 打开人脸识别 |  |  |

| 16 | 定位 | PPBridge.getLocation() | 获取当前定位 |  |  |

| 17 |  | PPBridge.openGoogleMap(params) | 打开 Google 地图并定位 |  |  |

| 18 | 分享 | PPBridge.share(params) | 通用分享（包含图片） |  |  |

| 20 | 设置 | PPBridge.getStatusBarHeight() | 获取电池栏高度 |  |  |

| 21 |  | PPBridge.setStatusBarTheme(params) | 设置电池栏主题色 |  |  |

| 22 | 请求 | PPBridge.request(params) | 统一请求 |  |  |

| 23 | 组件 | PPBridge.cascadePicker(params) | 级联 Picker | RN | ![7b99c4ac54740a8f0d6730c794047568.png](https://cdn.nlark.com/yuque/0/2023/png/29290358/1690269835705-4f4205fc-8d43-4aab-bff9-9f5309c0f0e8.png#averageHue=%23b4b4b4&clientId=uc7693b6c-b483-4&from=paste&height=668&id=u1073bf7e&originHeight=668&originWidth=679&originalType=binary&ratio=1&rotation=0&showTitle=false&size=32483&status=done&style=none&taskId=u7b9d90dd-dc17-405b-a402-82e8d7334cd&title=&width=679) |

| 24 |  | PPBridge.datePicker(params) | 打开日期选择器 | RN | ![image.png](https://cdn.nlark.com/yuque/0/2023/png/29290358/1690271202673-b0969ee3-1912-4297-b751-4ff0e7138683.png#averageHue=%23f6f7f7&clientId=uc7693b6c-b483-4&from=paste&height=600&id=uc24c3add&originHeight=600&originWidth=333&originalType=binary&ratio=1&rotation=0&showTitle=false&size=13897&status=done&style=none&taskId=uc91fb022-61b4-4251-8574-04bd95eca62&title=&width=333) |

| 25 |  | ~~PPBridge~~~~.timePicker~~~~(params)~~ | ~~打开时间选择器~~ | ~~RN~~ | ![52e78b412f61d0dbf365be44addf7ee2.png](https://cdn.nlark.com/yuque/0/2023/png/29290358/1690271026192-2dfa9bd6-7f58-497b-a160-dbc2297271b5.png#averageHue=%23dadcdf&clientId=uc7693b6c-b483-4&from=paste&height=275&id=uc6a9a64f&originHeight=275&originWidth=222&originalType=binary&ratio=1&rotation=0&showTitle=false&size=9250&status=done&style=none&taskId=u311f0f2b-8ad2-498b-92ff-7a32fdb5b50&title=&width=222) |

| 26 |  | ~~PPBridge~~~~.calendarPicker~~~~(params)~~ | ~~打开日历选择器~~ | ~~RN~~ | ![edc56ba7f18ae54d32c2b4f79c969517.png](https://cdn.nlark.com/yuque/0/2023/png/29290358/1690271039103-5e56b7e7-923a-450b-8bc5-efcc95e669d9.png#averageHue=%23f3f4f4&clientId=uc7693b6c-b483-4&from=paste&height=326&id=u4d6edd5a&originHeight=326&originWidth=198&originalType=binary&ratio=1&rotation=0&showTitle=false&size=12719&status=done&style=none&taskId=u843dc954-2234-48c5-88f4-3c68d81f38d&title=&width=198) |

| 27 |  | ~~PPBridge~~~~.somePicker~~~~(params)~~ | ~~打开星期几或每月几号选择器~~ | ~~RN~~ | ![8eadc5b11968e0014e04d2415d644671.png](https://cdn.nlark.com/yuque/0/2023/png/29290358/1690271010212-119f4587-9885-49b8-88e9-e6954c8da8ec.png#averageHue=%2374b6ea&clientId=uc7693b6c-b483-4&from=paste&height=262&id=ue81066ee&originHeight=262&originWidth=395&originalType=binary&ratio=1&rotation=0&showTitle=false&size=17528&status=done&style=none&taskId=uc6b271f3-a5eb-474c-8c60-7d35102799a&title=&width=395) |

| 28 |  |  |  |  |  |

| 29 |  |  |  |  |  |

| 30 |  |  |  |  |  |

| 31 |  |  |  |  |  |

| 32 |  |  |  |  |  |

\##  桥接文档：

响应对象统一规范化：

\```json

{

  "code": 0, // 0: 成功，1: 失败，2: 当前版本没有实现该桥接，3： 无权限，4： 参数异常 -1:取消（部分场景使用）

  "msg": "Successful", // 消息

  "entry": *** // 响应数据，泛型，根据不同业务，返回类型不同。

}

\```

| **桥接方法** | **请求参数** | **响应** | **dsBridge 调用参数** |

| --- | --- | --- | --- |

| 获取本地缓存：<br />PPBridge.getPreferences(params) | ```json

{

  "key": "***"

}

\```

\#### Request 参数说明：

缓存字段的 key 值 | ```json

{

  "code": 0,

  "msg": "success",

  "entry": ***

}

\```

 | ```json

{

  "group": "preferences",

  "id": "get",

  "args": {

​    "key": "***"

  }

}

\```

 |

| 存储本地缓存：<br />PPBridge.setPreferences(params) | ```json

{

  "key": "***",

  "value": ""

}

\```

\#### Request 参数说明：

key: 存储键<br />value: 存储值 | ```json

{

  "code": 0,

  "msg": "success",

  "entry": null

}

\```

 | ```json

{

  "group": "preferences",

  "id": "set",

  "args": {

​    "key": "***",

​    "value":""

  }

}

\```

<br /> |

| 获取 App 信息：<br />PPBridge.getAppInfo(params) | #### Request 参数说明：

请求接口时，传递的 data 对象，通过 app 获取得到签名：```json

{

  "key1": "value1",

  "key2": "value2",

  ...

}

\```

 | ```json

{

  "code": 0,

  "msg": "success",

  "entry": {

​    "PP_DEVICE_ID": "",

​    "PP_DEVICE_TYPE": "",

​    "PP_CLIENT_VER": "",

​    "PP_TIMESTAMP": "",

​    "PP_TOKEN": "",

​    "PP_REQ_SIGN": "",

​    "PP_REQ_SIGN_2": "",

​    "PP_COUNTRY_CODE": "",

​    "PP_CLIENT_VER_CODE": "",

  }

}

\```

 | ```json

{

  "group": "appInfo",

  "id": "get",

  "args": {

​    "key1": "value1",

​    "key2": "value2",

​    ...

  }

}

\```

 |

| 获取当前用户信息：<br />PPBridge.getUserInfo() | 无 | ```json

{

  "code": 0,

  "msg": "success",

  "entry": {

​    "memberId": "",

​    "firstName": "",

​    "middleName": "",

​    "lastName": "",

​    "nickName": "",

​    "fullName": "",

​    "birthday": "",

​    "gender": "",

​    "phoneNumber": "",

​    "email": "",

​    "avatar": "",

  }

}

\```

 | ```json

{

  "group": "userInfo",

  "id": "get",

  "args": null

}

\```

 |

| 获取通讯录联系人信息：<br />PPBridge.getContactInfo() | 无 | ```json

{

  "code": 0,

  "msg": "success",

  "entry": {

​    "phoneNumber": "",

​    "name": "",

  }

}

\```

\#### Response 参数说明：

phoneNumber: 联系人手机号<br />name: 联系人名字 | ```json

{

  "group": "contactInfo",

  "id": "get",

  "args": null

}

\```

 |

| 获取 App 版本信息：<br />PPBridge.getVersion() | 无 | ```json

{

  "code": 0,

  "msg": "success",

  "entry": {

​    version: '4.14.0',

​    versionCode: 510250000,

​    deviceId: ''

  }

}

\```

 | ```json

{

  "group": "version",

  "id": "get",

  "args": null

}

\```

 |

| 上传图片：<br />PPBridge.uploadPhoto(params) | ```json

{

  "type": 0,

  "private": false

}

\```

\#### Request 参数说明：

type:  0: 只允许拍照，1: 拍照+相册<br />private: 公开或私有 | ```json

{

  "code": 0,

  "msg": "success",

  "entry": {

​    "photoUrl": "",

​    "filePath": "",

  }

}

\```

\#### Response 参数说明：

photoUrl: 图片上传成功后的地址或key值<br />filePath: 图片在相册的本地文件地址，方便前端直接预览图片 | ```json

{

  "group": "photo",

  "id": "upload",

  "args": {

​    "type": 0,

​    "private": false

  }

}

\```

 |

| 保存图片至相册：<br />PPBridge.savePhoto(params) | ```json

{

  "type": 0,

  "images": []

}

\```

\#### Request 参数说明：

type: 0(保存base64 string本地图片)，1(传url native去下载并保存到相册)<br />images: 字符串数组，远程的话传[url]  | ```json

{

  "code": 0,

  "msg": "success",

  "entry": null

}

\```

\#### 

 | ```json

{

  "group": "photo",

  "id": "save",

  "args": {

​    "type": 0,

​    "images": []

  }

}

\```

 |

| 跳转页面：<br />PPBridge.openPage(params) | ```json

{

  "path": "",

  "params": ***,

}

\```

\#### Request 参数说明：

path: 原生页面地址<br />params: 跳转页面所需参数（可选，根据实际页面需要） | ```json

{

  "code": 0,

  "msg": "success",

  "entry": ***

}

\```

\#### Response 参数说明：

可不回调响应 | ```json

{

  "group": "page",

  "id": "open",

  "args": {

​    "path": "",

​    "params": ***,

  }

}

\```

 |

| Webview 返回上一级：<br />PPBridge.backPage() | 无 | 无 | ```json

{

  "group": "page",

  "id": "back",

  "args": null

}

\```

 |

| 关闭 Webview：<br />PPBridge.closePage() | 无 | 无 | ```json

{

  "group": "page",

  "id": "close",

  "args": null

}

\```

 |

| 端外默认浏览器打开页面：<br />PPBridge.openBroswer(params) | ```json

{

  "url": "",

}

\```

\#### Request 参数说明：

url: h5 页面完整地址 | ```json

{

  "code": 0,

  "msg": "success",

  "entry": null

}

\```

\#### Response 参数说明：

可不回调响应 | ```json

{

  "group": "page",

  "id": "browser",

  "args": {

​    "url": "",

  }

}

\```

 |

| 升级 App: 跳转 App 商城页面：<br />PPBridge.upgrade() | 无 | ```json

{

  "code": 0,

  "msg": "success",

  "entry": null

}

\```

\#### Response 参数说明：

可不回调响应 | ```json

{

  "group": "page",

  "id": "store",

  "args": null

}

\```

 |

| 打开客服 Chat：<br />PPBridge.openChat(params) | ```json

{

  "url": "",

}

\```

\#### Request 参数说明：

url: 客服 chat 地址 | ```json

{

  "code": 0,

  "msg": "success",

  "entry": null

}

\```

\#### Response 参数说明：

可不回调响应 | ```json

{

  "group": "page",

  "id": "chat",

  "args": {

​    "url": "",

  }

}

\```

 |

| 打开人脸识别：<br />PPBridge.openFaceCapture(params) | ```json

{

  "scene": "3",

  "skip": false,

  "closeWhenComplete": true,

}

\```

\#### Request 参数说明：

scene:  场景码，默认是 "3", 需要人脸与BVN后台匹配<br />skip: 是否可跳过，默认不展示（false）,设为true时，则展示skip按钮<br />closeWhenComplete: 成功后是否关闭当前页面，默认是true，可不传 | ```typescript

{

  "code": 0,

  "msg": "success",

  "entry": {

​    "status": 0,

​    "faceToken": "",

​    "imageURL": "",

  }

}

\```

\#### Response 参数说明：

status: 1：认证成功，2: 未进行认证，直接回退，3：跳过<br />faceToken:  活体验证的token<br />imageUrl: 活体采集图片 | ```json

{

  "group": "faceCapture",

  "id": "open",

  "args": null

}

\```

 |

| 获取当前定位：<br />PPBridge.getLocation() | 无 | ```typescript

{

  "code": 0,

  "msg": "success",

  "entry": {

​    "latitude": "",

​    "longitude": ""

  }

}

\```

\#### Response 参数说明：

latitude: 纬度<br />longitude: 经度<br />PS: 没有权限时，直接code返回3 | ```json

{

  "group": "location",

  "id": "get",

  "args": null

}

\```

 |

| 打开 Google 地图并定位：<br />PPBridge.openGoogleMap(params) | ```json

{

   "latitude": "",

   "longitude": ""

}

\```

\#### Request 参数说明：

latitude: 纬度<br />longitude: 经度 | ```json

{

  "code": 0,

  "msg": "success",

  "entry": null

}

\```

\#### Response 参数说明：

可不回调响应 | ```typescript

{

  "group": "googleMap",

  "id": "open",

  "args": {

​     "latitude": "",

​     "longitude": ""

  }

}

\```

 |

| 通用分享：<br />PPBridge.share(params) | ```json

{

   "title": "",

   "content": "",

   "url": "",

   "save": false,

}

\```

\#### Request 参数说明：

title: 分享框标题（ios没有）<br />content: 分享内容<br />url: 图片 Url<br />sasve: 是否保存图片到本地相册，默认 false | ```json

{

  "code": 0,

  "msg": "success",

  "entry": null

}

\```

\#### Response 参数说明：

可不回调响应 | ```typescript

{

  "group": "share",

  "id": "open",

  "args": {

​     "title": "",

​     "content": "",

​     "url": "",

​     "save": false,

  }

}

\```

 |

| 获取电池栏高度：<br />PPBridge.getStatusBarHeight() | 无 | ```json

{

  "code": 0,

  "msg": "success",

  "entry": 24

}

\```

\#### Response 参数说明：

height: 电池栏高度 | ```json

{

  "group": "statusBar",

  "id": "getHeight",

  "args": null

}

\```

 |

| 设置电池栏主题色：<br />PPBridge.setStatusBarTheme(params) | ```json

{

   "theme": "",

}

\```

\#### Request 参数说明：

theme: 'black' 或者 'white' | ```json

{

  "code": 0,

  "msg": "success",

  "entry": null

}

\```

\#### Response 参数说明：

可不回调响应 | ```typescript

{

  "group": "statusBar",

  "id": "setTheme",

  "args": {

​     "theme": "",

  }

}

\```

 |

| 统一请求：<br />PPBridge.request(params) | ```json

{

  apiUrl: "",

  postData: {

​    ...

  }

}

\```

\#### Request 参数说明：

apiUrl: 后端接口路径<br />postData：后台请求参数，是个泛型的对象，以实际接口请求所需参数为准。 | ```json

{

  "code": 0,

  "msg": "success",

  "entry": {

​     ...

  }

}

\```

\#### Response 参数说明：

后台接口响应：是个泛型的对象，以实际接口响应返回为准。 | ```typescript

{

  "group": "request",

  "id": "fetch",

  "args": {

​      apiUrl: "",

​      postData: {

​        ...

​      }

  }

}

\```

 |

| 级联 Picker：<br />PPBridge.cascadePicker(params) | ```json

{

  title: "",

  data: [

​    {

​      name : "",

​      code : 2134,

​      children : [

​        {

​          name : "",

​          code : 343,

​          children : []

​        },

​        ...

​      ]

​    },

​    ...

  ]

}

\```

\#### Request 参数说明

title: 对应的选择框标题<br />data：是个嵌套列表，最多支持三级。 | ```json

{

  "code": 0,

  "msg": "success",

  // 数组索引对应第几列，数组中的值代表对应列选中的行

  "entry": [1, 2, 3]

}

\```

\#### Response 参数说明：

返回三个列表对应的索引。 | ```typescript

{

  "group": "picker",

  "id": "cascade",

  "args": {

​      title: "",

​      data: [

​        {

​          name : "",

​          code : 2134,

​          children : [

​            {

​              name : "",

​              code : 343,

​              children : []

​            },

​            ...

​          ]

​        },

​        ...

​      ]

​    }

  }

}

\```

 |

| 打开日期选择器：<br />PPBridge.datePicker(params) | ```json

{

  min: '',

  max: '',

  defaultValue: ''

}

\```

\#### Request 参数说明

min: 最小选中的日期<br />max: 最大选中的日期<br />defaultValue：默认选中的日期 | ```json

{

  "code": 0,

  "msg": "success",

  "entry": ''

}

\```

\#### Response 参数说明：

返回日期字符串 | ```typescript

{

  "group": "picker",

  "id": "date",

  "args": {

​      min: '',

​      max: '',

​      defaultValue: ''

​    }

  }

}

\```

 |

| 打开时间选择器：<br />PPBridge.timePicker(params) | ```json

{

  defaultValue: ''

}

\```

\#### Request 参数说明

defaultValue：默认选中的时间 | ```json

{

  "code": 0,

  "msg": "success",

  "entry": ''

}

\```

\#### Response 参数说明：

返回时间字符串 | ```typescript

{

  "group": "picker",

  "id": "time",

  "args": {

​      defaultValue: ''

​    }

  }

}

\```

 |

| 打开日历选择器：<br />PPBridge.calendarPicker(params) | ```json

{

  defaultValue: ''

}

\```

\#### Request 参数说明

defaultValue：默认选中的日期 | ```json

{

  "code": 0,

  "msg": "success",

  "entry": ''

}

\```

\#### Response 参数说明：

返回日期字符串 | ```typescript

{

  "group": "picker",

  "id": "calendar",

  "args": {

​      defaultValue: ''

​    }

  }

}

\```

 |

| 打开星期几或每月几号选择器：<br />PPBridge.somePicker(params) | ```json

{

  defaultType: 1,

  defaultValue: ''

}

\```

\#### Request 参数说明

defaultType: 1(星期)，2(某天)<br />defaultValue：默认选中的日期 | ```json

{

  "code": 0,

  "msg": "success",

  "entry": {

​    "type": 1,

​    "value": 1,

  }

}

\```

\#### Response 参数说明：

type: 1： 1(星期)，2(某天)<br />value: 当前选中的值（星期几或几号） | ```typescript

{

  "group": "picker",

  "id": "some",

  "args": {

​      defaultType: 1,

​      defaultValue: ''

​    }

  }

}

\```

 |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

方法调用逻辑：<br />![](https://cdn.nlark.com/yuque/0/2023/jpeg/29290358/1689162562713-a490015f-cb3b-4696-9812-1e259d7047ae.jpeg)

\## 桥接管理规范：

\1. 桥接不做版本管理，桥接上线后，就固定了。都是通过新增桥接，来升级原来的桥接。

\2. 桥接承接统一负责人：林歆泉、涂图、李罡