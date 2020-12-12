---
description: Daha fazla bilgi edinin:/BAĞıMLıLAR
title: /DEPENDENTS
ms.date: 07/15/2019
f1_keywords:
- /dependents
helpviewer_keywords:
- -DEPENDENTS dumpbin option
- /DEPENDENTS dumpbin option
- DEPENDENTS dumpbin option
ms.assetid: 9b31da2a-75ac-4bbf-a3f1-adf8b0ecbbb4
ms.openlocfilehash: a0354f65dea51cb5db61b62d853392e32c14a3f2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192986"
---
# <a name="dependents"></a>/DEPENDENTS

Görüntünün içe aktardığı dll 'lerin adlarını döker. Uygulamanızı hangi dll 'Lere yeniden dağıtabileceğinizi veya eksik bağımlılığın adını bulmak için listeyi kullanabilirsiniz.

## <a name="syntax"></a>Syntax

> **/DEPENDENTS**

Bu seçenek, komut satırında belirtilen tüm yürütülebilir dosyalar için geçerlidir. Herhangi bir bağımsız değişken almaz.

## <a name="remarks"></a>Açıklamalar

**/Bağımlılar** seçeneği, görüntünün işlevlerini Içeri aktardığı dll 'lerin adlarını çıkışa ekler. Bu seçenek, içeri aktarılan işlevlerin adlarının dökümünü yapmaz. İçeri aktarılan işlevlerin adlarını görmek için [/Imports](imports-dumpbin.md) seçeneğini kullanın.

[/GL](gl-whole-program-optimization.md) derleyici seçeneği ile oluşturulan dosyalarda yalnızca [/Headers](headers.md) dumpbin seçeneği kullanılabilir.

## <a name="example"></a>Örnek

Bu örnek, istemci çalıştırılabilirinin yerleşik olarak bulunan [ve kendi dinamik bağlantı kitaplığınızı oluşturma ve kullanma](../walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)konusunda bulunan **/bağımlılar** seçeneğinin dumpbin çıkışını gösterir:

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
