---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4461'
title: Derleyici Uyarısı (düzey 1) C4461
ms.date: 11/04/2016
f1_keywords:
- C4461
helpviewer_keywords:
- C4461
ms.assetid: 104ffecc-3dd4-4cb1-89a8-81154fbe46d9
ms.openlocfilehash: 2efb92ca26f9e6cf76f7777c8a50ac657f73554d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311012"
---
# <a name="compiler-warning-level-1-c4461"></a>Derleyici Uyarısı (düzey 1) C4461

' Type ': Bu sınıfta bir Sonlandırıcı ' Sonlandırıcı ' bulunur, ancak yıkıcı ' dtor ' yok

Bir tür içindeki sonlandırıcının varlığı, silinecek kaynakları belirtir. Sonlandırıcı, türün yıkıcısında açıkça çağrılmadığı takdirde, ortak dil çalışma zamanı sonlandırıcının ne zaman çalıştırılacağı, nesnenizin kapsam dışına çıktıktan sonra belirler.

Tür içinde bir yıkıcı tanımlayabilir ve yıkıcıdan sonlandırıcıyı açıkça çağırırsanız, sonlandırıcıyı kesin bir şekilde çalıştırabilirsiniz.

Daha fazla bilgi için bkz. yok [ediciler ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4461 oluşturur.

```cpp
// C4461.cpp
// compile with: /W1 /clr /c
ref class A {
protected:
   !A() {}   // C4461
};

// OK
ref struct B {
   ~B() {
      B::!B();
   }

   !B() {}
};
```
