---
title: /DEPENDENTS
ms.date: 07/15/2019
f1_keywords:
- /dependents
helpviewer_keywords:
- -DEPENDENTS dumpbin option
- /DEPENDENTS dumpbin option
- DEPENDENTS dumpbin option
ms.assetid: 9b31da2a-75ac-4bbf-a3f1-adf8b0ecbbb4
ms.openlocfilehash: 88f0062a6bbca3f9199a12f739c2ade5f9d912cd
ms.sourcegitcommit: 7f5b29e24e1be9b5985044a030977485fea0b50c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/17/2019
ms.locfileid: "68299741"
---
# <a name="dependents"></a>/DEPENDENTS

Görüntünün içe aktardığı dll 'lerin adlarını döker. Uygulamanızı hangi dll 'Lere yeniden dağıtabileceğinizi veya eksik bağımlılığın adını bulmak için listeyi kullanabilirsiniz.

## <a name="syntax"></a>Sözdizimi

> **/DEPENDENTS**

Bu seçenek, komut satırında belirtilen tüm yürütülebilir dosyalar için geçerlidir. Herhangi bir bağımsız değişken almaz.

## <a name="remarks"></a>Açıklamalar

**/Bağımlılar** seçeneği, görüntünün işlevlerini Içeri aktardığı dll 'lerin adlarını çıkışa ekler. Bu seçenek, içeri aktarılan işlevlerin adlarının dökümünü yapmaz. İçeri aktarılan işlevlerin adlarını görmek için [/Imports](imports-dumpbin.md) seçeneğini kullanın.

[/GL](gl-whole-program-optimization.md) derleyici seçeneği ile oluşturulan dosyalarda yalnızca [/Headers](headers.md) dumpbin seçeneği kullanılabilir.

## <a name="example"></a>Örnek

Bu örnekte, yerleşik olarak bulunan [istemci yürütülebilir dosyasının **/bağımlılılar** seçeneğinin dumpbin çıkışı gösterilmektedir: Kendi dinamik bağlantı kitaplığınızı](../walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)oluşturun ve kullanın:

```cmd
C:\Users\username\Source\Repos\MathClient\Debug>dumpbin /DEPENDENTS MathClient.exe
Microsoft (R) COFF/PE Dumper Version 14.16.27032.1
Copyright (C) Microsoft Corporation.  All rights reserved.


Dump of file MathClient1322.exe

File Type: EXECUTABLE IMAGE

  Image has the following dependencies:

    MathLibrary.dll
    MSVCP140D.dll
    VCRUNTIME140D.dll
    ucrtbased.dll
    KERNEL32.dll

  Summary

        1000 .00cfg
        1000 .data
        2000 .idata
        1000 .msvcjmc
        3000 .rdata
        1000 .reloc
        1000 .rsrc
        8000 .text
       10000 .textbss
```

## <a name="see-also"></a>Ayrıca bkz.

[DUMPBIN Seçenekleri](dumpbin-options.md)
