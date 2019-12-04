---
title: Derleyici hatası C2787
ms.date: 11/04/2016
f1_keywords:
- C2787
helpviewer_keywords:
- C2787
ms.assetid: 34cb57e6-cafe-4ce7-bcc6-53d194629bd0
ms.openlocfilehash: 00f2097dc556055f0becf1d81d784c9126c66f63
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739603"
---
# <a name="compiler-error-c2787"></a>Derleyici hatası C2787

' tanımlayıcı ': Bu nesneyle ilişkili hiçbir GUID yok

[__Uuidof](../../cpp/uuidof-operator.md) işleci, bir GUID eklenmiş veya bir nesne Kullanıcı tanımlı türü olan Kullanıcı tanımlı bir tür alır. Bağımsız değişken GUID olmayan kullanıcı tanımlı bir tür olduğunda bu hata oluşur.

Aşağıdaki örnek C2787 oluşturur:

```cpp
// C2787.cpp
#include <windows.h>
struct F {};

struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) F2;

int main() {
   __uuidof(F);   // C2787
   __uuidof(F2);   // OK
}
```
