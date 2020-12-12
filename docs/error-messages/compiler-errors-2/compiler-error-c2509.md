---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2509'
title: Derleyici hatası C2509
ms.date: 11/04/2016
f1_keywords:
- C2509
helpviewer_keywords:
- C2509
ms.assetid: 339c1fcd-ec4a-456c-9f18-a9b24d9921af
ms.openlocfilehash: d7b6c2f05aaf525bee9572cd921d1fdffe1b0cf1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212967"
---
# <a name="compiler-error-c2509"></a>Derleyici hatası C2509

' tanımlayıcı ': üye işlev ' class ' içinde bildirilmemiş

İşlev belirtilen sınıfta bildirilmemiş.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2509 oluşturur.

```cpp
// C2509.cpp
// compile with: /c
struct A {
   virtual int vfunc() = 0;
   virtual int vfunc2() = 0;
};

struct B : private A {
   using A::vfunc;
   virtual int vfunc2();
};

int B::vfunc() { return 1; }   // C2509
int B::vfunc2() { return 1; }   // OK
```
