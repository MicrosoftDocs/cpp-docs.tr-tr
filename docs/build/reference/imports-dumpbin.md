---
title: /IMPORTS (DUMPBIN)
ms.date: 11/04/2016
f1_keywords:
- /imports
helpviewer_keywords:
- IMPORTS dumpbin option
- /IMPORTS dumpbin option
- -IMPORTS dumpbin option
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
ms.openlocfilehash: 9367457a8e7f6be1f372244f8288a994eb777071
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613792"
---
# <a name="imports-dumpbin"></a>/IMPORTS (DUMPBIN)

```
/IMPORTS[:file]
```

Bu seçeneği DLL'lerin listesini görüntüler (her ikisi de statik olarak bağlanan ve [Gecikmeli yüklendi](../../build/reference/linker-support-for-delay-loaded-dlls.md)), alma işlemi yürütülebilir bir dosya veya DLL ve tek tek tüm içe aktarmaları için her bu DLL'ler.

İsteğe bağlı `file` belirtimi yalnızca DLL için içeri aktarmalar görüntülenir belirtmenize olanak verir. Örneğin:

```
dumpbin /IMPORTS:msvcrt.dll
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek çıktıyı benzer [/EXPORTS](../../build/reference/dash-exports.md) çıktı.

Yalnızca [OPTIONAL](../../build/reference/headers.md) DUMPBIN seçeneği ile üretilen dosyalar kullanıma [/GL](../../build/reference/gl-whole-program-optimization.md) derleyici seçeneği.

## <a name="see-also"></a>Ayrıca Bkz.

[DUMPBIN Seçenekleri](../../build/reference/dumpbin-options.md)