---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2524'
title: Derleyici hatası C2524
ms.date: 11/04/2016
f1_keywords:
- C2524
helpviewer_keywords:
- C2524
ms.assetid: e71d17f5-2fc2-416b-8dbd-e9bed85eb33a
ms.openlocfilehash: 94e974674a5e244168499a50304a07264d23e618
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151144"
---
# <a name="compiler-error-c2524"></a>Derleyici hatası C2524

' yıkıcı ': yıkıcı/Sonlandırıcı ' void ' parametre listesine sahip olmalıdır

Yıkıcı veya Sonlandırıcı [void](../../cpp/void-cpp.md)olmayan bir parametre listesine sahipti. Diğer parametre türlerine izin verilmez.

## <a name="examples"></a>Örnekler

Aşağıdaki kod C2524 yeniden üretir.

```cpp
// C2524.cpp
// compile with: /c
class A {
   A() {}
   ~A(int i) {}    // C2524
   // try the following line instead
   // ~A() {}
};
```

Aşağıdaki kod C2524 yeniden üretir.

```cpp
// C2524_b.cpp
// compile with: /clr /c
ref struct I1 {
protected:
   !I1(int i);   // C2524
   // try the following line instead
   // !I1();
};
```
