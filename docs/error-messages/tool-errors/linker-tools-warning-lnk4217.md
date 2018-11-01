---
title: Bağlayıcı Araçları Uyarısı LNK4217
ms.date: 11/04/2016
f1_keywords:
- LNK4217
helpviewer_keywords:
- LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
ms.openlocfilehash: 12766241832d39f0b47ed85036c0ebeb0447fc75
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448054"
---
# <a name="linker-tools-warning-lnk4217"></a>Bağlayıcı Araçları Uyarısı LNK4217

Sembol 'symbol' function 'işlevini alma işlemi yerel olarak tanımlanan

[__declspec(dllimport)](../../cpp/dllexport-dllimport.md) sembolü sembol yerel olarak tanımlanan olsa bile belirtildi. Kaldırma `__declspec` bu uyarıyı çözmek için değiştiricisi.

`symbol` görüntüyü içinde tanımlanmış sembol adıdır. `function` sembolü içeri aktarılırken işlevidir.

Seçeneğini kullanarak derleme yaptığınızda bu uyarıyı görünmez [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).

İlk modülünün içeri aktarma kitaplığını sahip ikinci modül bunun yerine derleme yaptığınızda iki modül birbirine bağlamak çalışırsanız LNK4217 da meydana gelebilir.

```
// LNK4217.cpp
// compile with: /LD
#include "windows.h"
__declspec(dllexport) void func(unsigned short*) {}
```

Ardından,

```
// LNK4217b.cpp
// compile with: /c
#include "windows.h"
__declspec(dllexport) void func(unsigned short*) {}
```

Bu iki modül bağlantı girişimi LNK4217 neden, ikinci örnek gidermek için ilk örneğinin içeri aktarma kitaplığı ile derleme.