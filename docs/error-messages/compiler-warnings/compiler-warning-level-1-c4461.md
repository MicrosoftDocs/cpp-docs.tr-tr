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
ms.openlocfilehash: 2884daeb7497f6664cecf864ec705891cac62f48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33278639"
---
# <a name="compiler-warning-level-1-c4461"></a>Derleyici Uyarısı (düzey 1) C4461
'type': Bu sınıf bir Sonlandırıcısı 'Sonlandırıcı' ancak hiçbir yıkıcı 'dtor' sahiptir  
  
 Bir türdeki bir sonlandırıcı varlığını silinecek kaynakları anlamına gelir. Bir sonlandırıcı tür Yıkıcı açıkça çağrılan sürece, ortak dil çalışma zamanı ne zaman, nesne kapsam dışında göründükten sonra sonlandırıcıyı çalıştırılacağını belirler.  
  
 Türünde bir yıkıcı tanımlayın ve sonlandırıcıyı Yıkıcı açıkça çağırın, sonlandırıcıyı belirleyici biçimde çalıştırabilirsiniz.  
  
 Daha fazla bilgi için bkz: [yok ediciler ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4461 oluşturur.  
  
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