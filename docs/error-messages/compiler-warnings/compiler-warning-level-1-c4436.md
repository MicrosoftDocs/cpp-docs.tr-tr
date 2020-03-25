---
title: Derleyici Uyarısı (düzey 1) C4436
ms.date: 11/04/2016
f1_keywords:
- C4436
helpviewer_keywords:
- C4436
ms.assetid: 2b54a1fc-c9c6-4cc9-90be-faa44fc715d5
ms.openlocfilehash: 7772d835e398ade24b452f2b816afeae09659bf7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162393"
---
# <a name="compiler-warning-level-1-c4436"></a>Derleyici Uyarısı (düzey 1) C4436

' Class1 ' sanal tabanından Oluşturucu ya da yıkıcı içindeki ' Class2 ' öğesine dynamic_cast, kısmen oluşturulmuş nesne derlemesi ile/VD2 ile hata verebilir veya #pragma vtordisp (2) etkin olarak ' Class2 ' tanımlayabilir

Derleyici, aşağıdaki özelliklere sahip bir `dynamic_cast` işlemiyle karşılaştı.

- Atama, bir temel sınıf işaretçisinden türetilmiş sınıf işaretçisine kadar olur.

- Türetilmiş sınıf, temel sınıfı neredeyse devralır.

- Türetilmiş sınıfın sanal taban için `vtordisp` alanı yok.

- Cast, türetilmiş sınıfın oluşturucusunda veya yıkıcısında veya daha fazla türetilmiş sınıftan devralan bazı bir sınıfta bulunur.

Uyarı, kısmen oluşturulmuş bir nesne üzerinde çalışıyorsa `dynamic_cast` düzgün gerçekleştiremeyeceğini gösterir.  Bu, türetilmiş Oluşturucu/yok edici başka bir türetilmiş nesnenin alt nesnesi üzerinde çalışıyorsa meydana gelir.  Uyarıda adı geçen türetilmiş sınıf hiç bir daha alınmadıysa, uyarı yoksayılabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4436 oluşturur ve eksik `vtordisp` alanından oluşan kod oluşturma sorununu gösterir.

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

## <a name="see-also"></a>Ayrıca bkz.

[dynamic_cast İşleci](../../cpp/dynamic-cast-operator.md)<br/>
[vtordisp](../../preprocessor/vtordisp.md)<br/>
[Derleyici Uyarısı (düzey 4) C4437](../../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md)
