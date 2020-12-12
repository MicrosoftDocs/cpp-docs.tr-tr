---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2070'
title: Derleyici hatası C2070
ms.date: 11/04/2016
f1_keywords:
- C2070
helpviewer_keywords:
- C2070
ms.assetid: 4c8dea63-1227-4aba-be26-2462537f86fb
ms.openlocfilehash: b56b59a1aa9df1b653fd7f023c7db5fc6bcd9a41
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213151"
---
# <a name="compiler-error-c2070"></a>Derleyici hatası C2070

' Type ': geçersiz sizeof işleneni

[Sizeof](../../cpp/sizeof-operator.md) işleci bir ifade veya tür adı gerektiriyor.

Aşağıdaki örnek C2070 oluşturur:

```cpp
// C2070.cpp
void func() {}
int main() {
   int a;
   a = sizeof(func);   // C2070
}
```

Olası çözüm:

```cpp
// C2070b.cpp
void func() {}
int main() {
   int a;
   a = sizeof(a);
}
```
