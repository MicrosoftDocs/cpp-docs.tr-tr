---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2791'
title: Derleyici hatası C2791
ms.date: 11/04/2016
f1_keywords:
- C2791
helpviewer_keywords:
- C2791
ms.assetid: 938ad1fb-75d9-4ce2-ad92-83d6249005b5
ms.openlocfilehash: 0f5bd93c1c6ee32399da793147a18e9225b5fcb1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297778"
---
# <a name="compiler-error-c2791"></a>Derleyici hatası C2791

geçersiz ' Super ' kullanımı: ' class ' herhangi bir taban sınıfa sahip değil

[Super](../../cpp/super.md) anahtar sözcüğü, temel sınıfı olmayan bir sınıfın üye işlevinin bağlamı içinde kullanıldı.

Aşağıdaki örnek C2791 oluşturur:

```cpp
// C2791.cpp
struct D {
   void mf() {
      __super::mf();   // C2791
   }
};
```
