---
title: Bağlayıcı Araçları Uyarısı LNK4217
ms.date: 04/15/2019
f1_keywords:
- LNK4217
helpviewer_keywords:
- LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
ms.openlocfilehash: f1ea3cd0a8770571ae5c55d29a901c134311550f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59674246"
---
# <a name="linker-tools-warning-lnk4217"></a>Bağlayıcı Araçları Uyarısı LNK4217

> Sembol '*sembol*'içinde tanımlanan'*filename_1.obj*'tarafından alınan'*filename_2.obj*'işlevindeki'*işlevi*'

[__declspec(dllimport)](../../cpp/dllexport-dllimport.md) sembolü sembol aynı görüntü nesne dosyasında tanımlanan olsa bile belirtildi. Kaldırma `__declspec(dllimport)` bu uyarıyı çözmek için değiştiricisi.

## <a name="remarks"></a>Açıklamalar

*Sembol* görüntüyü içinde tanımlı bir sembolü adıdır. *işlev* sembolü içeri aktarılırken işlevdir.

Bu uyarı kullanarak derleme yaptığınızda görünmez [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) seçeneği.

İlk modülünün içeri aktarma kitaplığını sahip ikinci modül bunun yerine derleme yaptığınızda iki modül birbirine bağlamak çalışırsanız LNK4217 da meydana gelebilir.

```cpp
// LNK4217.cpp
// compile with: /LD
#include "windows.h"
__declspec(dllexport) void func(unsigned short*) {}
```

Ardından,

```cpp
// LNK4217b.cpp
// compile with: /c
#include "windows.h"
__declspec(dllexport) void func(unsigned short*) {}
```

Bu iki modül bağlantı girişimi LNK4217 neden olur. İkinci örnek gidermek için ilk örneğinin içeri aktarma kitaplığı ile derleyin.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı araçları uyarısı LNK4049](linker-tools-warning-lnk4049.md) \
[Bağlayıcı araçları uyarısı LNK4286](linker-tools-warning-lnk4286.md) \
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)