---
title: Derleyici Hatası C3375
ms.date: 11/04/2016
f1_keywords:
- C3375
helpviewer_keywords:
- C3375
ms.assetid: f1df78c6-e6ca-48f3-8b29-4e1710002bf3
ms.openlocfilehash: b3dfc17f9df495fe6907b816bace0dac1eff08cc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50545281"
---
# <a name="compiler-error-c3375"></a>Derleyici Hatası C3375

'function': belirsiz temsilci işlevi

Bir temsilci örneğini oluşturmada bir statik üye işlevi için atanmış olması veya bağlanmamış bir temsilci bir örnek işlevi için bu nedenle derleyici bu hata verilen.

Daha fazla bilgi için [temsilci (C++ bileşen uzantıları)](../../windows/delegate-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3375 oluşturur.

```
// C3375.cpp
// compile with: /clr
ref struct R {
   static void f(R^) {}
   void f() {}
};

delegate void Del(R^);

int main() {
   Del ^ a = gcnew Del(&R::f);   // C3375
}
```