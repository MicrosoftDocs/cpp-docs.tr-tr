---
title: Derleyici hatası C3320
ms.date: 11/04/2016
f1_keywords:
- C3320
helpviewer_keywords:
- C3320
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
ms.openlocfilehash: 0289d49ebbb0e30153beb6b0b2bc758bff5ef118
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201311"
---
# <a name="compiler-error-c3320"></a>Derleyici hatası C3320

' Type ': tür modül ' name ' özelliğiyle aynı ada sahip olamaz

Bir struct, Class, Enum veya Union olabilecek, verilen bir Kullanıcı tanımlı tür (UDT), [Modül](../../windows/module-cpp.md) özniteliğinin Name özelliğine geçirilen parametreyle aynı ada sahip olamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3320 oluşturur:

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
