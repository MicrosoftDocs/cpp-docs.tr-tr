---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4486'
title: Derleyici Uyarısı (düzey 1) C4486
ms.date: 11/04/2016
f1_keywords:
- C4486
helpviewer_keywords:
- C4486
ms.assetid: 2c0c59e3-d025-4d97-8da2-fa27df1402fc
ms.openlocfilehash: e664c9654b41932ab81c596494953807b8bb5d13
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212447"
---
# <a name="compiler-warning-level-1-c4486"></a>Derleyici Uyarısı (düzey 1) C4486

' function ': bir başvuru sınıfının veya değer sınıfının özel bir sanal yöntemi ' Sealed ' olarak işaretlenmelidir

Yönetilen bir sınıfın veya yapının özel sanal üye işlevine erişilemez veya geçersiz kılınmadığından, [korumalı](../../extensions/sealed-cpp-component-extensions.md)olarak işaretlenmelidir.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C4486 oluşturur.

```cpp
// C4486.cpp
// compile with: /clr /c /W1
ref class B {
private:
   virtual void f() {}   // C4486
   virtual void f1() sealed {}   // OK
};
```

Aşağıdaki örnek, özel bir Sealed, sanal işlevin olası bir kullanımını gösterir.

```cpp
// C4486_b.cpp
// compile with: /clr /c
ref class B {};

ref class D : B {};

interface class I {
   B^ mf();
};

ref class E : I {
private:
   virtual B^ g() sealed = I::mf {
      return gcnew B;
   }

public:
   virtual D^ mf() {
      return gcnew D;
   }
};
```
