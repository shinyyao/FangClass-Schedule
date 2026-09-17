# 2026年秋学期南信大方班实验班课程表（LaTeX 版）

Copyright @Xuan Yao

这份目录是由原 Excel 课程表转换得到的可维护 LaTeX 版本，目标是尽量保留原表的横向 A4、蓝色期次标题、浅蓝交替行、8 列结构与辩论课合并单元格布局。

## 文件

- `main.tex`：版式、颜色、列宽、字体和宏定义。一般不需要频繁改。
- `schedule-data1.tex``schedule-data2.tex`：所有课程/报告内容。日常更新主要编辑这个文件。包含院士点评课及小班并行课。

## Overleaf

1. 新建 Blank Project。
2. 上传 `main.tex` 和 `schedule-data1.tex` 和 `schedule-data2.tex`。
3. Compiler 选择 **XeLaTeX**。
4. 主文件设置为 `main.tex`。

## 日常更新

普通报告行格式：

```tex
\ReportBlue{时间}{报告人}{题目}{论文编号}{辅导老师}{质疑同学}{提问老师}{巡回点评}
```

或白底：

```tex
\ReportWhite{...}
```

课间休息：

```tex
\BreakRow{19:40-19:50}{课间休息}
```

一期课程的标题、表头和报告行都在同一个 `tabularx` 块中。新增一期时，复制相邻一期作为模板即可。


## GitHub

GitHub 会直接显示 `.tex` 源码，方便多人审阅和提交 PR。若要生成 PDF，可在本地安装 TeX Live 后运行：

```bash
latexmk -xelatex main.tex
```


