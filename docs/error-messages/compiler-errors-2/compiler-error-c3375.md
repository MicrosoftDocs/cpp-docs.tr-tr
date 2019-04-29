---
title: Derleyici Hatası C3375
ms.date: 11/04/2016
f1_keywords:
- C3375
helpviewer_keywords:
- C3375
ms.assetid: f1df78c6-e6ca-48f3-8b29-4e1710002bf3
ms.openlocfilehash: ba1dbf08fb56364d2ab5b8c40847ab89484dc005
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328804"
---
# <a name="compiler-error-c3375"></a>Derleyici Hatası C3375

'function': belirsiz temsilci işlevi

Bir temsilci örneğini oluşturmada bir statik üye işlevi için atanmış olması veya bağlanmamış bir temsilci bir örnek işlevi için bu nedenle derleyici bu hata verilen.

Daha fazla bilgi için [temsilci (C++ bileşen uzantıları)](../../extensions/delegate-cpp-component-extensions.md).

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