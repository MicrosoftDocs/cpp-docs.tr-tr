---
title: Derleyici hatası C2786
ms.date: 11/04/2016
f1_keywords:
- C2786
helpviewer_keywords:
- C2786
ms.assetid: 6676d8c0-86dd-4a39-bdda-b75a35f4d137
ms.openlocfilehash: ba5d05e9c7cc702509144fb876a1301bfc8bf3d4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739616"
---
# <a name="compiler-error-c2786"></a>Derleyici hatası C2786

' Type ': __uuidof için geçersiz işlenen

[__Uuidof](../../cpp/uuidof-operator.md) işleci, bir GUID eklenmiş veya bir nesne Kullanıcı tanımlı türü olan Kullanıcı tanımlı bir tür alır.  Olası nedenler:

1. Bağımsız değişken Kullanıcı tanımlı bir tür değil.

1. `__uuidof` bağımsız değişkenden GUID ayıklanamaz.

Aşağıdaki örnek C2786 oluşturur:

```cpp
// C2786.cpp
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};

int main() {
   __uuidof(int);   // C2786
   __uuidof(int *);   // C2786
   __uuidof(A **);   // C2786

   // no error
   __uuidof(A);
   __uuidof(A *);
   __uuidof(A &);
   __uuidof(A[]);

   int i;
   int *pi;
   A **ppa;

   __uuidof(i);      // C2786
   __uuidof(pi);     // C2786
   __uuidof(ppa);    // C2786
}
```
