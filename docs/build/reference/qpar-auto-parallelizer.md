---
title: /Qpar (Otomatik Paralel Hale Getirici)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableParallelCodeGeneration
ms.assetid: 33ecf49d-c0d5-4f34-bce3-84ff03f38918
ms.openlocfilehash: c1ddea73c5aa8d3e7e70b45834cb04154bf3b4bb
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809567"
---
# <a name="qpar-auto-parallelizer"></a>/Qpar (Otomatik Paralel Hale Getirici)

Sağlar [otomatik paralel hale getirici](../../parallel/auto-parallelization-and-auto-vectorization.md) derleyicinin otomatik olarak kod döngüleri paralel hale getirmek için bir özelliğidir.

## <a name="syntax"></a>Sözdizimi

```
/Qpar
```

## <a name="remarks"></a>Açıklamalar

Derleyicinin otomatik olarak kod Döngülerde parallelizes, hesaplama arasında birden çok işlemci Çekirdeğinde yayar. Yalnızca Derleyici bunu yapmak için geçerlidir ve bu paralelleştirme performansını iyileştirecek belirlerse döngü paralelleştirildi.

`#pragma loop()` Yönergeleridir iyileştirici belirli bir döngü paralel hale getirmek amacıyla kullanılabilir. Daha fazla bilgi için [döngü](../../preprocessor/loop.md).

Çıktı iletilerini otomatik paralel hale getirici için etkinleştirme hakkında daha fazla bilgi için bkz: [/Qpar-report (otomatik paralel hale getirici raporlama düzeyi)](qpar-report-auto-parallelizer-reporting-level.md).

### <a name="to-set-the-qpar-compiler-option-in-visual-studio"></a>Visual Studio'da /Qpar derleyici seçeneğini ayarlamak için

1. İçinde **Çözüm Gezgini**, proje için kısayol menüsünü açın ve ardından **özellikleri**.

1. İçinde **özellik sayfaları** iletişim kutusunun **C/C++** seçin **komut satırı**.

1. İçinde **ek seçenekler** kutusuna `/Qpar`.

### <a name="to-set-the-qpar-compiler-option-programmatically"></a>/Qpar derleyici seçeneğini program üzerinden ayarlamak için

- Aşağıdaki kod örneğinde kullanmak <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Q Seçenekler (Düşük Düzey İşlemler)](q-options-low-level-operations.md)<br/>
[/Qpar-report (Otomatik Paralel Hale Getirici Raporlama Düzeyi)](qpar-report-auto-parallelizer-reporting-level.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)<br/>
[#pragma loop()](../../preprocessor/loop.md)<br/>
[Yerel kodda paralel programlama](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/04/12/auto-vectorizer-in-visual-studio-2012-overview/)
