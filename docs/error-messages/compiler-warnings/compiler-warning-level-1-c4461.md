---
title: "Derleyici Uyarısı (düzey 1) C4461 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4461
dev_langs: C++
helpviewer_keywords: C4461
ms.assetid: 104ffecc-3dd4-4cb1-89a8-81154fbe46d9
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cc417e7044eb3eac12365676c6c1be9abeddfed0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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