---
title: Bağlayıcı araçları uyarısı LNK4217 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4217
dev_langs:
- C++
helpviewer_keywords:
- LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c650eddd8078419f63df48cc91705d2e86eb5c8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067990"
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