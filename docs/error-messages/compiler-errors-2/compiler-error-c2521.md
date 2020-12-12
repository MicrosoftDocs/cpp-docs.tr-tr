---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2521'
title: Derleyici hatası C2521
ms.date: 11/04/2016
f1_keywords:
- C2521
helpviewer_keywords:
- C2521
ms.assetid: 6042821b-e345-4a54-a7e9-a2c9019ea016
ms.openlocfilehash: a85ae6db2bd2f41ecbdd3aef385068cd2515e2bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177737"
---
# <a name="compiler-error-c2521"></a>Derleyici hatası C2521

işlev herhangi bir bağımsız değişken almaz

Bağımsız değişkenleri bir yıkıcı veya sonlandırıcısı ile kullanmaya çalıştınız.

Daha fazla bilgi için bkz. yok [ediciler ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Örnek

Aşağıdaki örnek C2521 oluşturur.

```cpp
// C2521.cpp
// compile with: /clr
ref class R {
protected:
   !R() {}

public:
   void CleanUp() {
      this->!R(4);   // C2521
      this->!R();   // OK
   }
};

int main() {
   R^ r = gcnew R();
   r->CleanUp();
}
```
