# doc-viewer-plus

A React component for viewing various types of documents including Office files, PDFs, images, OFD files, and videos.

## Installation

```bash
npm install doc-viewer-plus
```

## Usage

```jsx
import { DocViewerPlus } from 'doc-viewer-plus';

function App() {
  const [visible, setVisible] = useState(false);

  return (
    <DocViewerPlus
      previewFile={{
        fileUrl: 'https://example.com/sample.pdf',
        fileName: 'sample.pdf'
      }}
      visibleViewerPlus={visible}
      onVisibleChange={() => setVisible(!visible)}
    />
  );
}
```

## Props

|
 Prop 
|
 Type 
|
 Description 
|
|
------
|
------
|
-------------
|
|
 previewFile 
|
 { fileUrl?: string; fileName?: string } 
|
 File information for preview 
|
|
 response 
|
 { url?: string } 
|
 Optional response object containing URL 
|
|
 visibleViewerPlus 
|
 boolean 
|
 Controls visibility of the viewer 
|
|
 onVisibleChange 
|
 () => void 
|
 Callback when visibility changes 
|

## Supported File Types

- Images (jpg, jpeg, png, gif)
- PDF files
- Office documents (doc, docx, xls, xlsx, ppt, pptx)
- OFD files
- Videos (mp4)