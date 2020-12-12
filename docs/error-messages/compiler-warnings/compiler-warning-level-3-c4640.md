---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4640'
title: Derleyici Uyarısı (düzey 3) C4640
ms.date: 11/04/2016
f1_keywords:
- C4640
helpviewer_keywords:
- C4640
ms.assetid: f76871f6-e436-4c35-9793-d2f22f7e1c7f
ms.openlocfilehash: f0fc41256d11c54742a157236e09e36277902b5e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338557"
---
# <a name="compiler-warning-level-3-c4640"></a>Derleyici Uyarısı (düzey 3) C4640

' örnek ': yerel statik nesnenin yapımı iş parçacığı güvenli değil

Bir nesnenin statik örneği iş parçacığı güvenli değildir.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Aşağıdaki örnek C4640 oluşturur:

```cpp
// C4640.cpp
// compile with: /W3
#pragma warning(default:4640)

class X {
public:
   X() {
   }
};

void f() {
   static X aX;   // C4640
}

int main() {
   f();
}
```
