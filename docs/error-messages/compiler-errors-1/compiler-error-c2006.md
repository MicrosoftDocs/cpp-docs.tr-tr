---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2006'
title: Derleyici hatası C2006
ms.date: 11/04/2016
f1_keywords:
- C2006
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
ms.openlocfilehash: 5747f5417db60bd3c1f7bc1420c257552a9b42c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298519"
---
# <a name="compiler-error-c2006"></a>Derleyici hatası C2006

' Directive ' bir dosya adı bekliyordu, ' token ' bulundu

[#İnclude](../../preprocessor/hash-include-directive-c-cpp.md) veya [#import](../../preprocessor/hash-import-directive-cpp.md) gibi yönergeler bir dosya adı gerektirir. Hatayı gidermek için *belirtecin* geçerli bir dosya adı olduğundan emin olun. Ayrıca, dosya adını çift tırnak içine veya açılı ayraç içine alın.

Aşağıdaki örnek C2006 oluşturur:

```cpp
// C2006.cpp
#include stdio.h   // C2006
```

Olası çözüm:

```cpp
// C2006b.cpp
// compile with: /c
#include <stdio.h>
```
