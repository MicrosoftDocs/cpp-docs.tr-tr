---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2786'
title: Derleyici hatası C2786
ms.date: 11/04/2016
f1_keywords:
- C2786
helpviewer_keywords:
- C2786
ms.assetid: 6676d8c0-86dd-4a39-bdda-b75a35f4d137
ms.openlocfilehash: 64c794281da775df94187a1e871ab3e48bc35a3c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297869"
---
# <a name="compiler-error-c2786"></a>Derleyici hatası C2786

' Type ': __uuidof için geçersiz işlenen

[__Uuidof](../../cpp/uuidof-operator.md) işleci, bir GUID eklenmiş veya bir nesne Kullanıcı tanımlı türü olan Kullanıcı tanımlı bir tür alır.  Olası nedenler:

1. Bağımsız değişken Kullanıcı tanımlı bir tür değil.

1. **`__uuidof`** bağımsız değişkenden GUID ayıklanamıyor.

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
