---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2507'
title: Derleyici hatası C2507
ms.date: 11/04/2016
f1_keywords:
- C2507
helpviewer_keywords:
- C2507
ms.assetid: f102aff5-de7d-4c3f-9cac-2ddf9ce02b14
ms.openlocfilehash: b2043f01cea9a64ace11fbdaa8d905fd892cc99c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212980"
---
# <a name="compiler-error-c2507"></a>Derleyici hatası C2507

' tanımlayıcı ': taban sınıfta çok fazla sayıda sanal değiştirici var

Bir sınıf veya yapı **`virtual`** birden çok kez tanımlanmış. **`virtual`** Temel sınıfların bir listesindeki her bir sınıf için yalnızca bir değiştirici görünebilir.

Aşağıdaki örnek C2507 oluşturur:

```cpp
// C2507.cpp
// compile with: /c
class A {};
class B : virtual virtual public A {};   // C2507
class C : virtual public A {};   // OK
```
