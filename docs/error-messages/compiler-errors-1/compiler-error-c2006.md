---
title: Derleyici Hatası C2006
ms.date: 11/04/2016
f1_keywords:
- C2006
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
ms.openlocfilehash: c23f17483925f25468214165fb459db577e576fc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475094"
---
# <a name="compiler-error-c2006"></a>Derleyici Hatası C2006

'token' bulunan bir dosya adı 'yönergesi' bekleniyor

Yönergeleri gibi [#include](../../preprocessor/hash-include-directive-c-cpp.md) veya [#import](../../preprocessor/hash-import-directive-cpp.md) bir dosya adı gerektirir. Hatayı gidermek için emin *belirteci* geçerli bir dosya adı. Ayrıca, dosya adı çift tırnak işareti veya açılı ayraçlar yerleştirin.

Aşağıdaki örnek, C2006 oluşturur:

```
// C2006.cpp
#include stdio.h   // C2006
```

Olası çözüm:

```
// C2006b.cpp
// compile with: /c
#include <stdio.h>
```