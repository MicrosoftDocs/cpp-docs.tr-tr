---
title: Derleyici Uyarısı (düzey 1) C4461 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4461
dev_langs:
- C++
helpviewer_keywords:
- C4461
ms.assetid: 104ffecc-3dd4-4cb1-89a8-81154fbe46d9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 86c12208c6992b97f30bc36ea821ba26148ff751
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081409"
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