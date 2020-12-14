---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2500'
title: Derleyici hatası C2500
ms.date: 11/04/2016
f1_keywords:
- C2500
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
ms.openlocfilehash: 39d1ab0876470b443d4444a3c583cc0993c98325
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275977"
---
# <a name="compiler-error-c2500"></a>Derleyici hatası C2500

' Identifier1 ': ' identifier2 ' zaten bir doğrudan taban sınıfı

Bir sınıf veya yapı, temel sınıfların bir listesinde birden çok kez görünür.

Doğrudan taban, temel listede bahsedilen bir temeldir. Dolaylı bir taban, temel listedeki sınıflardan birinin taban sınıfıdır.

Bir sınıf doğrudan temel sınıf olarak birden çok kez belirtilemez. Bir sınıf, dolaylı bir temel sınıf olarak birden çok kez kullanılabilir.

Aşağıdaki örnek C2500 oluşturur:

```cpp
// C2500.cpp
// compile with: /c
class A {};
class B : public A, public A {};    // C2500

// OK
class C : public A {};
class D : public A {};
class E : public C, public D {};
```
