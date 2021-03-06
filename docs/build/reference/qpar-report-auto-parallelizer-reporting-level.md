---
description: Daha fazla bilgi edinin:/Qpar-report (otomatik paralelleştirme raporlama düzeyi)
title: /Qpar-rapor (Otomatik Paralel Hale Getirici Raporlama Düzeyi)
ms.date: 11/04/2016
ms.assetid: 562673b9-02da-4bf8-bb64-70bc25ef4651
ms.openlocfilehash: 573ab7535b63ba8d3f19f2917c17709ac7726b38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225537"
---
# <a name="qpar-report-auto-parallelizer-reporting-level"></a>/Qpar-rapor (Otomatik Paralel Hale Getirici Raporlama Düzeyi)

Derleyicinin [Otomatik paralelleştirme](../../parallel/auto-parallelization-and-auto-vectorization.md) raporlama özelliğini sunar ve derleme sırasında çıkış için bilgilendirici ileti düzeyini belirtir.

## <a name="syntax"></a>Syntax

```
/Qpar-report:{1}{2}
```

## <a name="remarks"></a>Açıklamalar

**/Qpar-report: 1**<br/>
Paralelleştirilmiş döngüler için bilgilendirici bir ileti verir.

**/Qpar-report: 2**<br/>
Paralelleştirilmiş döngüler için, bir neden kodu ile birlikte paralelleştirilmiş döngüler için bilgilendirici bir ileti verir.

İletiler stdout 'a bildirilir. Bilgilendirici bir ileti bildirilmezse, kod döngü içermez ya da raporlama düzeyi paralelleştirilmiş olarak rapor döngüleri olarak ayarlanmadı. Neden kodları ve iletileri hakkında daha fazla bilgi için bkz. [Vektörtorizer ve paralelleştirme iletileri](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).

### <a name="to-set-the-qpar-report-compiler-option-in-visual-studio"></a>Visual Studio 'da/Qpar-report derleyici seçeneğini ayarlamak için

1. **Çözüm Gezgini**' de, proje için kısayol menüsünü açın ve ardından **Özellikler**' i seçin.

1. **Özellik sayfaları** iletişim kutusundaki **C/C++** altında **komut satırı**' nı seçin.

1. **Ek seçenekler** kutusuna `/Qpar-report:1` veya yazın `/Qpar-report:2` .

### <a name="to-set-the-qpar-report-compiler-option-programmatically"></a>/Qpar-report derleyici seçeneğini programlı olarak ayarlamak için

- İçindeki kod örneğini kullanın <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> .

## <a name="see-also"></a>Ayrıca bkz.

[/Q seçenekler (düşük düzey Işlemler)](q-options-low-level-operations.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)<br/>
[Visual Studio 'da yerel kod vektörleştirme](/archive/blogs/nativeconcurrency/auto-vectorizer-in-visual-studio-2012-overview)
