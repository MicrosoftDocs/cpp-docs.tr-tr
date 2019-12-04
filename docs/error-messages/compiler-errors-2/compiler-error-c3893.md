---
title: Derleyici hatası C3893
ms.date: 11/04/2016
f1_keywords:
- C3893
helpviewer_keywords:
- C3893
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
ms.openlocfilehash: 20c17eaa6555b5511ecbc930eacdb2ec92475b23
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749509"
---
# <a name="compiler-error-c3893"></a>Derleyici hatası C3893

' var ': initonly veri üyesinin lvalue kullanımına yalnızca ' type_name ' sınıfının bir örnek oluşturucusunda izin verilir

Statik [initonly](../../dotnet/initonly-cpp-cli.md) veri üyeleri yalnızca kendi adreslerini statik bir oluşturucuda alabilir.

Örnek (statik olmayan) initonly veri üyeleri yalnızca kendi adreslerine örnek (statik olmayan) oluşturucular içinde alınmış olabilir.

Aşağıdaki örnek C3893 oluşturur:

```cpp
// C3893.cpp
// compile with: /clr
ref struct Y1 {
   Y1() : data_var(0) {
      int% i = data_var;   // OK
   }
   initonly int data_var;
};

int main(){
   Y1^ y= gcnew Y1;
   int% i = y->data_var;   // C3893
}
```
