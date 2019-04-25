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
ms.openlocfilehash: c8b0f88b38eb657fe4d3916ef0df13972e985cbe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291850"
---
# <a name="imports-dumpbin"></a>/IMPORTS (DUMPBIN)

```
/IMPORTS[:file]
```

Bu seçeneği DLL'lerin listesini görüntüler (her ikisi de statik olarak bağlanan ve [Gecikmeli yüklendi](linker-support-for-delay-loaded-dlls.md)), alma işlemi yürütülebilir bir dosya veya DLL ve tek tek tüm içe aktarmaları için her bu DLL'ler.

İsteğe bağlı `file` belirtimi yalnızca DLL için içeri aktarmalar görüntülenir belirtmenize olanak verir. Örneğin:

```
dumpbin /IMPORTS:msvcrt.dll
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek çıktıyı benzer [/EXPORTS](dash-exports.md) çıktı.

Yalnızca [OPTIONAL](headers.md) DUMPBIN seçeneği ile üretilen dosyalar kullanıma [/GL](gl-whole-program-optimization.md) derleyici seçeneği.

## <a name="see-also"></a>Ayrıca bkz.

[DUMPBIN Seçenekleri](dumpbin-options.md)
