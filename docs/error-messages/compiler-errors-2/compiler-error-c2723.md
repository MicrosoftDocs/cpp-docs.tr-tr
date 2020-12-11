---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2723'
title: Derleyici hatası C2723
ms.date: 11/04/2016
f1_keywords:
- C2723
helpviewer_keywords:
- C2723
ms.assetid: 86925601-2297-4cfd-94e2-2caf27c474c4
ms.openlocfilehash: ab6eacd4279f0fd7b1c44b86b72cbe62ee51020e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155520"
---
# <a name="compiler-error-c2723"></a>Derleyici hatası C2723

' function ': ' belirtici ' belirticisi işlev tanımında geçersizdir

Tanımlayıcı, sınıf bildirimi dışında bir işlev tanımıyla birlikte bulunamaz. **`virtual`** Tanımlayıcı yalnızca bir sınıf bildiriminde bulunan bir üye işlev bildiriminde belirtilebilir.

Aşağıdaki örnek C2723 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2723.cpp
struct X {
   virtual void f();
   virtual void g();
};

virtual void X::f() {}   // C2723

// try the following line instead
void X::g() {}
```
