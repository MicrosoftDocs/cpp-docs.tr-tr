---
title: Bağlayıcı Araçları Uyarısı LNK4217
ms.date: 04/09/2019
f1_keywords:
- LNK4217
helpviewer_keywords:
- LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
ms.openlocfilehash: 3fcb806afa064a4f6d9c9c0680c617662a3b9a21
ms.sourcegitcommit: 0ad3f4517e64900a2702dd3d366586f9e2bce2c2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2019
ms.locfileid: "59477398"
---
# <a name="linker-tools-warning-lnk4217"></a>Bağlayıcı Araçları Uyarısı LNK4217

> Sembol '*sembol*'içinde tanımlanan'*filename_1.obj*'tarafından alınan'*filename_2.obj*'işlevindeki'*işlevi*'

[__declspec(dllimport)](../../cpp/dllexport-dllimport.md) sembolü sembol aynı görüntü nesne dosyasında tanımlanan olsa bile belirtildi. Kaldırma `__declspec(dllimport)` bu uyarıyı çözmek için değiştiricisi.

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