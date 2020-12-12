---
description: Daha fazla bilgi edinin:/Qvec-report (otomatik Vektörleştirici raporlama düzeyi)
title: /Qvec-report (Otomatik Vektör Hale Getirici Raporlama Düzeyi)
ms.date: 11/04/2016
ms.assetid: 4778c9a3-0692-4085-9b05-1bfeadf4c74a
ms.openlocfilehash: 734dabffa3bf19ecaba42d35d208eb27ec7b2968
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225472"
---
# <a name="qvec-report-auto-vectorizer-reporting-level"></a>/Qvec-report (Otomatik Vektör Hale Getirici Raporlama Düzeyi)

Derleyici [Otomatik Vektörleştirici](../../parallel/auto-parallelization-and-auto-vectorization.md) 'in raporlama özelliğini sunar ve derleme sırasında çıkış için bilgi iletilerinin düzeyini belirtir.

## <a name="syntax"></a>Syntax

```
/Qvec-report:{1}{2}
```

## <a name="remarks"></a>Açıklamalar

**/Qvec-report: 1**<br/>
Vektörleştirilmiş döngüler için bilgilendirici bir ileti verir.

**/Qvec-report: 2**<br/>
Vektörleştirilmiş döngüler için ve bir neden koduyla birlikte vektörleştirilmiş döngüler için bilgilendirici bir ileti verir.

Neden kodları ve iletileri hakkında bilgi için bkz. [Vektörtorizer ve paralelleştirme iletileri](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).

### <a name="to-set-the-qvec-report-compiler-option-in-visual-studio"></a>Visual Studio 'da/Qvec-report derleyici seçeneğini ayarlamak için

1. **Çözüm Gezgini**' de, proje için kısayol menüsünü açın ve ardından **Özellikler**' i seçin.

1. **Özellik sayfaları** iletişim kutusundaki **C/C++** altında **komut satırı**' nı seçin.

1. **Ek seçenekler** kutusuna `/Qvec-report:1` veya yazın `/Qvec-report:2` .

### <a name="to-set-the-qvec-report-compiler-option-programmatically"></a>/Qvec-report derleyici seçeneğini programlı olarak ayarlamak için

- İçindeki kod örneğini kullanın <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> .

## <a name="see-also"></a>Ayrıca bkz.

[/Q seçenekler (düşük düzey Işlemler)](q-options-low-level-operations.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)<br/>
[Visual Studio 'da yerel kod vektörleştirme](/archive/blogs/nativeconcurrency/auto-vectorizer-in-visual-studio-2012-overview)
