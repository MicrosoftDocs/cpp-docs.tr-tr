---
title: Derleyici Hatası C2786
ms.date: 11/04/2016
f1_keywords:
- C2786
helpviewer_keywords:
- C2786
ms.assetid: 6676d8c0-86dd-4a39-bdda-b75a35f4d137
ms.openlocfilehash: b03155ad1a209ae59327dd31d432f5623f380ac9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266003"
---
# <a name="compiler-error-c2786"></a>Derleyici Hatası C2786

'type': __uuidof için geçersiz işlenen

[__Uuidof](../../cpp/uuidof-operator.md) işleci ile bağlı bir GUID veya böyle bir kullanıcı tanımlı türde bir nesne kullanıcı tanımlı bir tür alır.  Olası nedenler:

1. Bağımsız değişken, kullanıcı tanımlı bir tür değil.

1. `__uuidof` GUID bağımsız değişkende ayıklanamıyor.

Aşağıdaki örnek, C2786 oluşturur:

```
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