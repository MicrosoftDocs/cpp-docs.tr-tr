---
title: Derleyici Hatası C3893
ms.date: 11/04/2016
f1_keywords:
- C3893
helpviewer_keywords:
- C3893
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
ms.openlocfilehash: 45a140d3fd5f510ee2434950ca3c4b47c0756d75
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385504"
---
# <a name="compiler-error-c3893"></a>Derleyici Hatası C3893

'var': initonly veri üyesinin lvalue kullanımına yalnızca 'type_name' sınıfının bir örnek oluşturucusunda izin verilir

Statik [initonly](../../dotnet/initonly-cpp-cli.md) veri üyeleri yalnızca statik bir oluşturucuda adresleri sahiptir.

Örnek (statik olmayan) initonly veri üyeleri yalnızca adresleri (statik olmayan) örneği oluşturucularda alınmış olabilir.

Aşağıdaki örnek, C3893 oluşturur:

```
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