---
title: -IMPORTS (DUMPBIN) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /imports
dev_langs:
- C++
helpviewer_keywords:
- IMPORTS dumpbin option
- /IMPORTS dumpbin option
- -IMPORTS dumpbin option
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5b3b1e3a74fea278bc142d02f793308b6b0e054
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713576"
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