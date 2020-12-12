---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2787'
title: Derleyici hatası C2787
ms.date: 11/04/2016
f1_keywords:
- C2787
helpviewer_keywords:
- C2787
ms.assetid: 34cb57e6-cafe-4ce7-bcc6-53d194629bd0
ms.openlocfilehash: 96a06908012e565bc606bf56f6a1709ee1f265a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297817"
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
