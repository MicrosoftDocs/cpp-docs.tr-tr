---
title: "Derleyici Uyarısı (düzey 4) C4437 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs: C++
ms.assetid: dc07e350-20eb-474c-a7ad-f841ae7ec339
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 88873faa9978da7c068d35cb88cc92317b7509d4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4437"></a>Derleyici Uyarısı (düzey 4) C4437
Sanal Taban 'class1' den dynamic_cast 'class2' için /vd2 ile bazı bağlamlarda derleme başarısız veya #pragma vtordisp(2) ile ' class2' yürürlükte tanımlayın  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
 Derleyici karşılaştı bir `dynamic_cast` işlemi aşağıdaki özelliklere sahip.  
  
-   Cast temel sınıf işaretçi bir türetilmiş sınıf işaretçidir.  
  
-   Türetilen sınıfın temel sınıf neredeyse devralır.  
  
-   Türetilmiş sınıf sahip olmayan bir `vtordisp` sanal temel alan.  
  
-   Cast oluşturucu veya türetilmiş bir sınıf yıkıcı içinde bulunamadı veya daha fazla bazı sınıfı (Aksi takdirde derleyici uyarısı C4436 verilecek) türetilmiş sınıfından devralıyor.  
  
 Uyarı belirten `dynamic_cast` kısmen oluşturulan bir nesne üzerinde çalışıyorsa doğru yerine getirmeyebilir.  Bu durum bir oluşturucu veya uyarıda adlı türetilmiş sınıf devralınan bir sınıf yıkıcı kapsayan işlevi çağrıldığında oluşur.  Uyarı adlı türetilmiş sınıf hiçbir zaman başka ise türetilmiş, ya da kapsayan işlevi, nesne oluşturması veya yok etme sırasında çağrılmaz, uyarıyı göz ardı edilebilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4437 oluşturur ve eksik gelen ortaya kod oluşturma sorunu gösterir `vtordisp` alan.  
  
```cpp  
// C4437.cpp  
// To see the warning and runtime assert, compile with: /W4  
// To eliminate the warning and assert, compile with: /W4 /vd2  
//       or compile with: /W4 /DFIX  
#pragma warning(default : 4437)  
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
        func();  
    }  
  
    void func()  
    {  
        A* a = static_cast<A*>(this);  
        B* b = dynamic_cast<B*>(a);     // C4437  
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
 [Derleyici Uyarısı (düzey 1) C4436](../../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)