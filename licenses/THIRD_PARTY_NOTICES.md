# 第三方组件与来源

本工程通过 npm 锁定依赖。发布包包含对应 LICENSE 文件，完整清单由 scripts/licenses.mjs 生成。

| 组件 | 许可 | 官方来源 |
| --- | --- | --- |
| Vue 3、Vite | MIT | https://github.com/vuejs/core 、https://github.com/vitejs/vite |
| SQLite WASM | SQLite 公有领域，封装与 Emscripten 各有许可 | https://github.com/sqlite/sqlite-wasm |
| PaddleOCR.js | Apache-2.0 | https://github.com/PaddlePaddle/PaddleOCR/tree/main/paddleocr-js |
| RapidOCR PP-OCRv5 模型 | Apache-2.0 | https://www.modelscope.cn/models/RapidAI/RapidOCR |
| ONNX Runtime Web | MIT | https://github.com/microsoft/onnxruntime |
| OpenCV.js | Apache-2.0 | https://github.com/TechStark/opencv-js |
| PDF.js | Apache-2.0 | https://github.com/mozilla/pdf.js |
| zxing-wasm | MIT，ZXing C++ 为 Apache-2.0 | https://github.com/Sec-ant/zxing-wasm |
| UTIF.js | MIT | https://github.com/photopea/UTIF.js |
| ExcelJS | MIT | https://github.com/exceljs/exceljs |
| decimal.js、fflate、Lucide | MIT，Lucide 图标 ISC | https://github.com/MikeMcl/decimal.js 、https://github.com/101arrowz/fflate 、https://github.com/lucide-icons/lucide |

`src/ocr.worker.ts` 的透视裁切流程参考 PaddlePaddle Authors 的 PaddleOCR.js，保留 Apache-2.0 归属。官方 SDK 使用固定版本，其受保护模型接口由适配层访问，并通过浏览器模型加载与识别测试约束兼容性。方向分类沿用本项目原始 RapidOCR PP-LCNet 模型。

模型生成过程使用原始权重，不训练新模型。`public/models/manifest.json` 保留原模型下载地址、大小、SHA256 与生成资产哈希。模型权重与通用 WASM 资源按脚本准备，不包含任何发票、数据库或原件。
