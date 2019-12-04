---
title: Derleyici hatası C2006
ms.date: 11/04/2016
f1_keywords:
- C2006
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
ms.openlocfilehash: 64f81929916cd3a4adf38a302ea34d46d9a5c070
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756558"
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
