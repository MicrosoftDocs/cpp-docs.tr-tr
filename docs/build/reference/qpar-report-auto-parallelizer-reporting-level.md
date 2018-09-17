---
title: -Qpar-report (otomatik paralel hale getirici raporlama düzeyi) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 562673b9-02da-4bf8-bb64-70bc25ef4651
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 847a93efc74c4e6111f49679219e1b26a70022f6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707522"
---
# <a name="qpar-report-auto-parallelizer-reporting-level"></a>/Qpar-rapor (Otomatik Paralel Hale Getirici Raporlama Düzeyi)

Derleyicinin uygulamasının raporlama özelliğini etkinleştirir [otomatik paralel hale getirici](../../parallel/auto-parallelization-and-auto-vectorization.md) ve derleme sırasında bilgi iletilerini çıktı düzeyini belirtir.

## <a name="syntax"></a>Sözdizimi

```
/Qpar-report:{1}{2}
```

## <a name="remarks"></a>Açıklamalar

**/ Qpar-report: 1**<br/>
Bir bilgi iletisidir paralel döngüler için çıkarır.

**/ Qpar-report: 2**<br/>
Bir bilgi iletisidir paralel döngüler için ve ayrıca, bir neden kodu ile birlikte paralelleştirilmedi döngüler çıkarır.

İletiler stdout raporlanır. Hiçbir bilgi iletilerini bildirilen, ardından hiçbir döngüler kodunu içerir ya da raporlama düzeyine paralel rapor döngüler için ayarlanmadı. Neden kodları ve iletiler hakkında daha fazla bilgi için bkz. [vektör yapıcı ve paralel hale getirici iletileri](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).

### <a name="to-set-the-qpar-report-compiler-option-in-visual-studio"></a>Visual Studio'da /Qpar-report derleyici seçeneğini ayarlamak için

1. İçinde **Çözüm Gezgini**, proje için kısayol menüsünü açın ve ardından **özellikleri**.

1. İçinde **özellik sayfaları** iletişim kutusunun **C/C++** seçin **komut satırı**.

1. İçinde **ek seçenekler** kutusuna `/Qpar-report:1` veya `/Qpar-report:2`.

### <a name="to-set-the-qpar-report-compiler-option-programmatically"></a>/Qpar-report derleyici seçeneğini program üzerinden ayarlamak için

- Aşağıdaki kod örneğinde kullanmak <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[/Q Seçenekler (düşük düzey işlemler)](../../build/reference/q-options-low-level-operations.md)
[derleyici seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[Yerel kodda paralel programlama](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/04/12/auto-vectorizer-in-visual-studio-2012-overview/)