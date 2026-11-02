# 文档工具箱（纯前端）

三个本地工具，全部在你的浏览器里跑，文件不上传任何服务器。

| 页面 | 用途 |
|---|---|
| `index.html` | 图片 PDF → 文本（OCR）+ 自动脱敏 |
| `img2pdf.html` | 图片 → 拼成一个 PDF |
| `letter.html` | 按 xlsx 清单批量生成律师函 PDF |

## 部署

这是纯静态站点（无后端、无构建步骤）：把仓库根目录当静态站点发布即可（GitHub Pages 选 main / root）。
`coi-serviceworker.js` 用来补 COOP/COEP 头，让 WASM 多线程生效；删掉它也能跑，只是慢 2~3 倍。

## 依赖与许可

- OCR：PP-OCRv6 small（ONNX）经 onnxruntime-web 在浏览器 WASM 里跑；模型文件随仓库分发。
- PDF 生成：pdf-lib。
- docx → PDF：reamkit（MIT）。
- xlsx 解析：SheetJS 社区版（Apache-2.0）。
- 内置中文字体：LXGW 文楷（SIL OFL 1.1）。律师函页可临时换成本机字体（只在本机内存里用）。
