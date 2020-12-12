---
description: Daha fazla bilgi edinin:/ıMPORTS (DUMPBIN)
title: /IMPORTS (DUMPBIN)
ms.date: 11/04/2016
f1_keywords:
- /imports
helpviewer_keywords:
- IMPORTS dumpbin option
- /IMPORTS dumpbin option
- -IMPORTS dumpbin option
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
ms.openlocfilehash: 86c428280bbca3a4957f7d7a0a640482607547de
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199798"
---
# <a name="imports-dumpbin"></a>/IMPORTS (DUMPBIN)

```
/IMPORTS[:file]
```

Bu seçenek, yürütülebilir bir dosyaya veya DLL 'ye aktarılan dll 'lerin listesini (statik olarak bağlanmış ve [gecikmeli yüklendi](linker-support-for-delay-loaded-dlls.md)) ve bu DLL 'lerden her biri ayrı ayrı içeri aktarmaları görüntüler.

İsteğe bağlı `file` Belirtim yalnızca bu DLL için içeri aktarmaların görüntülenmesini belirtmenize olanak tanır. Örneğin:

```
dumpbin /IMPORTS:msvcrt.dll
```

## <a name="remarks"></a>Açıklamalar

Bu seçenekle görüntülenecek çıktı, [/dışarı aktarmalar](dash-exports.md) çıktısına benzerdir.

[/GL](gl-whole-program-optimization.md) derleyici seçeneği ile oluşturulan dosyalarda yalnızca [/Headers](headers.md) dumpbin seçeneği kullanılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[DUMPBIN Seçenekleri](dumpbin-options.md)
