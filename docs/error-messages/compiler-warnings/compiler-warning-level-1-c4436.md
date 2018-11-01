---
title: Derleyici Uyarısı (düzey 1) C4436
ms.date: 11/04/2016
ms.assetid: 2b54a1fc-c9c6-4cc9-90be-faa44fc715d5
ms.openlocfilehash: b8f62b7556d458f285597b4ae92a4f6e15ee60c9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658001"
---
# <a name="compiler-warning-level-1-c4436"></a>Derleyici Uyarısı (düzey 1) C4436

Sanal Taban 'class1' dynamic_cast oluşturucuda veya yok edicide 'class2' için oluşturulmuş bir nesne derleme/vd2 ile başarısız veya #pragma vtordisp(2) ' class2' yürürlükte tanımlayın

Derleyici karşılaştı bir `dynamic_cast` işlemi aşağıdaki özelliklere sahip.

- Cast bir taban sınıfı işaretçisinden türetilmiş sınıf işaretçisine ' dir.

- Türetilmiş bir sınıf sanal temel sınıf devralır.

- Türetilmiş sınıf olmayan bir `vtordisp` için sanal temel alan.

- Dönüştürme bir oluşturucu veya yıkıcı türetilmiş sınıfın içinde bulunamadı veya türetilmiş sınıftan daha fazla bazı sınıfından devralır.

Uyarı gösterir `dynamic_cast` oluşturulmuş bir nesne üzerinde çalışıyorsa doğru yerine getirmeyebilir.  Türetilen Oluşturucu/yıkıcı bazı daha fazla türetilmiş nesnenin bir alt nesnesi üzerinde çalışıyorsa, gerçekleşir.  Uyarıda adlı bir türetilmiş sınıf hiçbir zaman başka ise türetilmiş, Uyarı yoksayılabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4436 oluşturur ve yok ortaya kod oluşturma sorunu gösterir `vtordisp` alan.

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

[dynamic_cast İşleci](../../cpp/dynamic-cast-operator.md)<br/>
[vtordisp](../../preprocessor/vtordisp.md)<br/>
[Derleyici Uyarısı (düzey 4) C4437](../../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md)