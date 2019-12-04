---
title: Derleyici hatası C2524
ms.date: 11/04/2016
f1_keywords:
- C2524
helpviewer_keywords:
- C2524
ms.assetid: e71d17f5-2fc2-416b-8dbd-e9bed85eb33a
ms.openlocfilehash: 1e53a0c08f07bf69378fbb7603f63c596f641355
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758664"
---
# <a name="compiler-error-c2524"></a>Derleyici hatası C2524

' yıkıcı ': yıkıcı/Sonlandırıcı ' void ' parametre listesine sahip olmalıdır

Yıkıcı veya Sonlandırıcı [void](../../cpp/void-cpp.md)olmayan bir parametre listesine sahipti. Diğer parametre türlerine izin verilmez.

## <a name="example"></a>Örnek

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

## <a name="example"></a>Örnek

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
