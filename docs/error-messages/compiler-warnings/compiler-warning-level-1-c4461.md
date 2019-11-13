---
title: Derleyici Uyarısı (düzey 1) C4461
ms.date: 11/04/2016
f1_keywords:
- C4461
helpviewer_keywords:
- C4461
ms.assetid: 104ffecc-3dd4-4cb1-89a8-81154fbe46d9
ms.openlocfilehash: 195e5532b6555210077e43ad3086ee3106f3e757
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966020"
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