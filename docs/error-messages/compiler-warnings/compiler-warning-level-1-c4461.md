---
title: "Derleyici Uyarısı (düzey 1) C4461 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4461
dev_langs:
- C++
helpviewer_keywords:
- C4461
ms.assetid: 104ffecc-3dd4-4cb1-89a8-81154fbe46d9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b3b3a64ac5d7bcfbc912c63abf57769fe6da2d40
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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