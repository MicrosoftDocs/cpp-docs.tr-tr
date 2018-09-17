---
title: -Qvec-report (otomatik vektör hale getirici raporlama düzeyi) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 4778c9a3-0692-4085-9b05-1bfeadf4c74a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c11beb3f8a5b9b189fff237012580765f8858fc0
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717567"
---
# <a name="qvec-report-auto-vectorizer-reporting-level"></a>/Qvec-report (Otomatik Vektör Hale Getirici Raporlama Düzeyi)

Raporlama özelliği derleyicinin sağlar [otomatik vektör hale getirici](../../parallel/auto-parallelization-and-auto-vectorization.md) ve derleme sırasında bilgi iletilerini çıktı düzeyini belirtir.

## <a name="syntax"></a>Sözdizimi

```
/Qvec-report:{1}{2}
```

## <a name="remarks"></a>Açıklamalar

**/ Qvec-report: 1**<br/>
Bir bilgi iletisidir vektörleştirildi döngüler için çıkarır.

**/ Qvec-report: 2**<br/>
Bir bilgi iletisidir ve, bir neden kodu ile birlikte vektörleştirilmedi döngüler vektörleştirildi döngüler için çıkarır.

Neden kodları ve iletiler hakkında daha fazla bilgi için bkz. [vektör yapıcı ve paralel hale getirici iletileri](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).

### <a name="to-set-the-qvec-report-compiler-option-in-visual-studio"></a>Visual Studio'da /Qvec-report derleyici seçeneğini ayarlamak için

1. İçinde **Çözüm Gezgini**, proje için kısayol menüsünü açın ve ardından **özellikleri**.

1. İçinde **özellik sayfaları** iletişim kutusunun **C/C++** seçin **komut satırı**.

1. İçinde **ek seçenekler** kutusuna `/Qvec-report:1` veya `/Qvec-report:2`.

### <a name="to-set-the-qvec-report-compiler-option-programmatically"></a>/Qvec-report derleyici seçeneğini program üzerinden ayarlamak için

- Aşağıdaki kod örneğinde kullanmak <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[/Q Seçenekler (düşük düzey işlemler)](../../build/reference/q-options-low-level-operations.md)
[derleyici seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[Yerel kodda paralel programlama](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/04/12/auto-vectorizer-in-visual-studio-2012-overview/)