---
title: -Qpar (otomatik paralel hale getirici) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableParallelCodeGeneration
dev_langs:
- C++
ms.assetid: 33ecf49d-c0d5-4f34-bce3-84ff03f38918
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a701183becc7a561ca778dea383fdb57181d8da4
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710781"
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

Çıktı iletilerini otomatik paralel hale getirici için etkinleştirme hakkında daha fazla bilgi için bkz: [/Qpar-report (otomatik paralel hale getirici raporlama düzeyi)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md).

### <a name="to-set-the-qpar-compiler-option-in-visual-studio"></a>Visual Studio'da /Qpar derleyici seçeneğini ayarlamak için

1. İçinde **Çözüm Gezgini**, proje için kısayol menüsünü açın ve ardından **özellikleri**.

1. İçinde **özellik sayfaları** iletişim kutusunun **C/C++** seçin **komut satırı**.

1. İçinde **ek seçenekler** kutusuna `/Qpar`.

### <a name="to-set-the-qpar-compiler-option-programmatically"></a>/Qpar derleyici seçeneğini program üzerinden ayarlamak için

- Aşağıdaki kod örneğinde kullanmak <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[/Q Seçenekler (düşük düzey işlemler)](../../build/reference/q-options-low-level-operations.md)
[(otomatik paralel hale getirici düzeyi raporlama) /Qpar-report](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md)
[derleyici seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[#pragma loop()](../../preprocessor/loop.md)
[yerel kodda paralel programlama](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/04/12/auto-vectorizer-in-visual-studio-2012-overview/)