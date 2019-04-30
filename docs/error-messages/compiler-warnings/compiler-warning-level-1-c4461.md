---
title: Derleyici Uyarısı (düzey 1) C4461
ms.date: 11/04/2016
f1_keywords:
- C4461
helpviewer_keywords:
- C4461
ms.assetid: 104ffecc-3dd4-4cb1-89a8-81154fbe46d9
ms.openlocfilehash: 5cc9b08f0f25e9c92b4185f060ab123684c5d9e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408270"
---
# <a name="compiler-warning-level-1-c4461"></a>Derleyici Uyarısı (düzey 1) C4461

'type': Bu sınıf, bir Sonlandırıcı 'Sonlandırıcı' ancak hiçbir yok edici 'dtor' sahiptir

Kaynakları silmek için bir tür içindeki bir sonlandırıcı varlığını gösterir. Sonlandırıcıda tür yok ediciden açıkça çağrılır sürece, ortak dil çalışma zamanı zaman Sonlandırıcı nesnenizin kapsamın dışına çıkıncaya sonra çalıştırılacak belirler.

Türün bir yok ediciyi tanımlayın ve sonlandırıcı yok ediciden açıkça çağırmak, belirleyici, sonlandırıcı çalıştırabilirsiniz.

Daha fazla bilgi için [yok ediciler ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4461 oluşturur.

```
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