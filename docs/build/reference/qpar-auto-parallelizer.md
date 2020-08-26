---
title: /Qpar (Otomatik Paralel Hale Getirici)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableParallelCodeGeneration
ms.assetid: 33ecf49d-c0d5-4f34-bce3-84ff03f38918
ms.openlocfilehash: effe1ad7799022ea85184513de1dc48c72d6bfcb
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839445"
---
# <a name="qpar-auto-parallelizer"></a>/Qpar (Otomatik Paralel Hale Getirici)

Derleyicinin otomatik [paralelleştirme](../../parallel/auto-parallelization-and-auto-vectorization.md) özelliğinin kodunuzda otomatik olarak paralel hale getirmek döngüleri sağlar.

## <a name="syntax"></a>Syntax

```
/Qpar
```

## <a name="remarks"></a>Açıklamalar

Derleyici, koddaki döngüleri otomatik olarak paralelleştirirken, birden çok işlemci çekirdekleri arasında hesaplamayı yayar. Bir döngü, yalnızca derleyici meşru olduğunu belirlerse ve bu paralelleştirme performansı iyileştirecağından paralelleştirilebilir.

En `#pragma loop()` iyi duruma getirme paralel hale getirmek belirli döngülere yardımcı olacak yönergeler sunulmaktadır. Daha fazla bilgi için bkz. [Loop](../../preprocessor/loop.md).

Otomatik paralelleştirme için çıkış iletilerinin nasıl etkinleştirileceği hakkında bilgi için bkz. [/Qpar-report (otomatik paralel hale getirici raporlama düzeyi)](qpar-report-auto-parallelizer-reporting-level.md).

### <a name="to-set-the-qpar-compiler-option-in-visual-studio"></a>Visual Studio 'da/Qpar derleyici seçeneğini ayarlamak için

1. **Çözüm Gezgini**' de, proje için kısayol menüsünü açın ve ardından **Özellikler**' i seçin.

1. **Özellik sayfaları** iletişim kutusundaki **C/C++** altında **komut satırı**' nı seçin.

1. **Ek seçenekler** kutusuna yazın `/Qpar` .

### <a name="to-set-the-qpar-compiler-option-programmatically"></a>Programlı olarak/Qpar derleyici seçeneğini ayarlamak için

- İçindeki kod örneğini kullanın <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> .

## <a name="see-also"></a>Ayrıca bkz.

[/Q seçenekler (düşük düzey Işlemler)](q-options-low-level-operations.md)<br/>
[/Qpar-report (otomatik paralel hale getirici raporlama düzeyi)](qpar-report-auto-parallelizer-reporting-level.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)<br/>
[#pragma döngüsü ()](../../preprocessor/loop.md)<br/>
[Visual Studio 'da yerel kod vektörleştirme](/archive/blogs/nativeconcurrency/auto-vectorizer-in-visual-studio-2012-overview)
