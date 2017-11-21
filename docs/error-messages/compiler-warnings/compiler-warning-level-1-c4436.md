---
title: "Derleyici Uyarısı (düzey 1) C4436 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs: C++
ms.assetid: 2b54a1fc-c9c6-4cc9-90be-faa44fc715d5
caps.latest.revision: "2"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e727159cbd0f87d8ae01813b7ac2a0ed57362b08
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4436"></a>Derleyici Uyarısı (düzey 1) C4436
Sanal Taban 'class1' den dynamic_cast Oluşturucusu veya yıkıcı 'class2' için veya kısmen oluşturulmuş nesnesiyle derleme /vd2 başarısız #pragma vtordisp(2) ile ' class2' yürürlükte tanımlayın  
  
 Derleyici karşılaştı bir `dynamic_cast` işlemi aşağıdaki özelliklere sahip.  
  
-   Cast temel sınıf işaretçi bir türetilmiş sınıf işaretçidir.  
  
-   Türetilen sınıfın temel sınıf neredeyse devralır.  
  
-   Türetilmiş sınıf sahip olmayan bir `vtordisp` sanal temel alan.  
  
-   Cast oluşturucu veya türetilmiş bir sınıf yıkıcı içinde bulunamadı veya daha fazla bazı sınıfı türetilmiş sınıfından devralıyor.  
  
 Uyarı gösterir `dynamic_cast` kısmen oluşturulan bir nesne üzerinde çalışıyorsa, doğru yerine getirmeyebilir.  Türetilen Oluşturucusu/yıkıcı bir alt nesnesinin bazı daha fazla türetilmiş üzerinde çalışıyorsa, olur.  Uyarı adlı türetilmiş sınıf hiçbir zaman başka ise türetilmiş, uyarıyı göz ardı edilebilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4436 oluşturur ve eksik gelen ortaya kod oluşturma sorunu gösterir `vtordisp` alan.  
  
```cpp  
// C4436.cpp  
// To see the warning and runtime assert, compile with: /W1  
// To eliminate the warning and assert, compile with: /W1 /vd2  
//       or compile with: /W1 /DFIX  
#include <cassert>  
  
struct A  
{  
public:  
    virtual ~A() {}  
};  
  
#if defined(FIX)  
#pragma vtordisp(push, 2)  
#endif  
struct B : virtual A  
{  
    B()  
    {  
        A* a = static_cast<A*>(this);  
        B* b = dynamic_cast<B*>(a);     // C4436  
        assert(this == b);              // assert unless compiled with /vd2  
    }  
};  
#if defined(FIX)  
#pragma vtordisp(pop)  
#endif  
  
struct C : B  
{  
    int i;  
};  
  
int main()  
{  
    C c;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [dynamic_cast işleci](../../cpp/dynamic-cast-operator.md)   
 [vtordisp](../../preprocessor/vtordisp.md)   
 [Derleyici Uyarısı (düzey 4) C4437](../../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md)