---
title: Derleyici Hatası C2786 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2786
dev_langs:
- C++
helpviewer_keywords:
- C2786
ms.assetid: 6676d8c0-86dd-4a39-bdda-b75a35f4d137
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 027c41ad1665e0002855f07fe82293bfbee6d4e7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031112"
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