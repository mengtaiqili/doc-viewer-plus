# doc-viewer-plus

一个基于 React 的文档预览组件，支持多种文件格式的在线预览，包括 Office 文档、PDF、图片、OFD 文件和视频等。

## 特性

- 支持多种文件格式预览
  - 图片：jpg, jpeg, png, gif
  - Office 文档：doc, docx, xls, xlsx, ppt, pptx
  - PDF 文件
  - OFD 文件
  - 视频文件（mp4）
- 支持文件下载
- 响应式设计
- 使用 Microsoft Office Online 预览 Office 文档
- 支持自定义预览窗口大小
- 简洁现代的界面设计

## 安装

```bash
npm install doc-viewer-plus

# 或使用 yarn
yarn add doc-viewer-plus

# 或使用 pnpm
pnpm add doc-viewer-plus
```

## 使用示例

```jsx
import React, { useState } from 'react';
import { DocViewerPlus } from 'doc-viewer-plus';

const App = () => {
  const [visible, setVisible] = useState(false);

  return (
    <div>
      <button onClick={() => setVisible(true)}>
        预览文档
      </button>
      
      <DocViewerPlus
        previewFile={{
          fileUrl: 'https://example.com/sample.pdf',
          fileName: 'sample.pdf'
        }}
        visibleViewerPlus={visible}
        onVisibleChange={() => setVisible(!visible)}
      />
    </div>
  );
};

export default App;
```

## API

### Props

| 属性 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| previewFile | `{ fileUrl?: string; fileName?: string }` | 是 | 预览文件的信息 |
| response | `{ url?: string }` | 否 | 下载链接（可选） |
| visibleViewerPlus | `boolean` | 是 | 控制预览器的显示/隐藏 |
| onVisibleChange | `() => void` | 是 | 预览器显示状态改变的回调函数 |

### 支持的文件类型

- 图片：jpg, jpeg, png, gif
- Office：doc, docx, xls, xlsx, ppt, pptx
- PDF：pdf
- OFD：ofd
- 视频：mp4

## 更多示例

### 图片预览

```jsx
<DocViewerPlus
  previewFile={{
    fileUrl: 'https://example.com/image.jpg',
    fileName: 'example.jpg'
  }}
  visibleViewerPlus={visible}
  onVisibleChange={handleVisibleChange}
/>
```

### PDF 预览

```jsx
<DocViewerPlus
  previewFile={{
    fileUrl: 'https://example.com/document.pdf',
    fileName: 'document.pdf'
  }}
  visibleViewerPlus={visible}
  onVisibleChange={handleVisibleChange}
/>
```

### Office 文档预览

```jsx
<DocViewerPlus
  previewFile={{
    fileUrl: 'https://example.com/document.docx',
    fileName: 'document.docx'
  }}
  visibleViewerPlus={visible}
  onVisibleChange={handleVisibleChange}
/>
```

## 环境要求

- React >= 16.8.0
- antd >= 4.0.0
- @ant-design/icons >= 4.0.0

## 常见问题

### Q: 为什么 Office 文件预览失败？
A: Office 文件预览需要文件 URL 可以公网访问。

### Q: 如何处理跨域问题？
A: 确保服务器允许跨域访问，或通过后端代理请求。

### Q: 如何自定义预览窗口大小？
A: 可以通过包裹一个指定尺寸的 div 来控制。

## 开发

```bash
# 安装依赖
npm install

# 构建
npm run build
```

## License

[MIT](./LICENSE)

---

Made with ❤️ by [limingming]