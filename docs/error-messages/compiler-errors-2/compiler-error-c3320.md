---
title: Derleyici Hatası C3320
ms.date: 11/04/2016
f1_keywords:
- C3320
helpviewer_keywords:
- C3320
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
ms.openlocfilehash: 622e7366dda4cd6693d9b6128855fa0966e07952
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581473"
---
# <a name="compiler-error-c3320"></a>Derleyici Hatası C3320

'type': tür Modül 'name' özelliği aynı ada sahip olamaz

Geçirilen parametre olarak bir yapı, sınıf, enum veya birleşim olabilir, bir verilen kullanıcı tanımlı tür (UDT) aynı ada sahip olamaz [Modülü](../../windows/module-cpp.md) özniteliğin adı özelliği.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3320 oluşturur:

```cpp
// C3320.cpp
#include "unknwn.h"
[module(name="xx")];

[export] struct xx {   // C3320
// Try the following line instead
// [export] struct yy {
   int i;
};
```