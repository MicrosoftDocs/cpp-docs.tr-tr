---
title: Derleyici Uyarısı (düzey 1) C4486
ms.date: 11/04/2016
f1_keywords:
- C4486
helpviewer_keywords:
- C4486
ms.assetid: 2c0c59e3-d025-4d97-8da2-fa27df1402fc
ms.openlocfilehash: b6e1fc7001908202efc2fb0ef3653153c007eac0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456036"
---
# <a name="compiler-warning-level-1-c4486"></a>Derleyici Uyarısı (düzey 1) C4486

'function': bir başvuru sınıfının veya değer sınıfının özel bir sanal yöntemi 'sealed' olarak işaretlenmelidir

Bir özel sanal üye işlevi bir yönetilen sınıfın veya yapının geçersiz kılınmış veya erişilemiyor beri işaretlenmelidir [korumalı](../../windows/sealed-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4486 oluşturur.

```
// C4486.cpp
// compile with: /clr /c /W1
ref class B {
private:
   virtual void f() {}   // C4486
   virtual void f1() sealed {}   // OK
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, özel bir korumalı, sanal işlevin olası kullanım gösterir.

```
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