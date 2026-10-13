# 文档文字识别 · Doc-OCR

> Turn PDFs, scans and photos into editable text with local macOS Vision OCR — nothing is uploaded.

PDF / 扫描件 / 图片 → 可编辑文字。有文字层的 PDF 直接抽取，扫描件走 **macOS Vision 自带 OCR（中英文）**，文件不出本机。

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Skills](https://img.shields.io/badge/format-Agent%20Skill-2f6fed)](#install)
[![Part of](https://img.shields.io/badge/also%20in-hermes--skills%20collection-555)](https://github.com/jiawood2006/hermes-skills)

## Install

```bash
# 1) Agent Skills CLI (works with 50+ agent hosts)
npx skills add jiawood2006/doc-ocr

# 2) Claude Code / any host that reads ~/.claude/skills
git clone https://github.com/jiawood2006/doc-ocr.git ~/.claude/skills/doc-ocr

# 3) Hermes Agent
git clone https://github.com/jiawood2006/doc-ocr.git ~/.hermes/skills/utilities/doc-ocr
```

No build step, no account, no telemetry.

## Usage

```bash
python3 scripts/dococr.py 合同.pdf                 # single file → text
python3 scripts/dococr.py 发票.jpg                 # image / scan
python3 scripts/dococr.py 书.pdf --md              # Markdown output
python3 scripts/dococr.py ./扫描件/ -o 全部.txt     # batch a folder
```
Ask your agent: *"把这份扫描合同转成文字"* and it runs the OCR for you.

## Requirements

macOS (Vision framework) + Python 3.9+

```bash
pip3 install pymupdf pyobjc-framework-Vision
```

## Notes

Text-layer PDFs are extracted directly (fast, exact); only scanned pages go through OCR. Chinese and English are handled out of the box.

## License

MIT — see [LICENSE](LICENSE). Issues and PRs welcome.
Part of the [hermes-skills](https://github.com/jiawood2006/hermes-skills) collection.
