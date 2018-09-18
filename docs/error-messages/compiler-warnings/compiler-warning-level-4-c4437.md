---
title: Derleyici Uyarısı (düzey 4) C4437 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: dc07e350-20eb-474c-a7ad-f841ae7ec339
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11d234f7f264f051042ae99900875b8e570fa66a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118654"
---
# <a name="compiler-warning-level-4-c4437"></a>Derleyici Uyarısı (düzey 4) C4437

Sanal Taban 'class1' öğesinden 'class2' yönelik dynamic_cast bazı bağlamlarda/vd2 ile derleme başarısız veya 'class2' ile #pragma vtordisp(2) etkili tanımlayın

Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.

Derleyici karşılaştı bir `dynamic_cast` işlemi aşağıdaki özelliklere sahip.

- Cast bir taban sınıfı işaretçisinden türetilmiş sınıf işaretçisine ' dir.

- Türetilmiş bir sınıf sanal temel sınıf devralır.

- Türetilmiş sınıf olmayan bir `vtordisp` için sanal temel alan.

- Dönüştürme bir oluşturucu veya yıkıcı türetilmiş sınıfın içinde bulunamadı veya daha fazla bazı sınıfı türetilmiş bir sınıftan (Aksi durumda, derleyici uyarı C4436 verilecek) devralır.

Uyarı bildiren `dynamic_cast` oluşturulmuş bir nesne üzerinde çalışıyorsa doğru şekilde yerine getirmeyebilir.  Bu durum, çevreleyen işlevin bir oluşturucu veya uyarıda adlı türetilmiş sınıfından devralan bir sınıfın yok Edicisi çağrılır oluşur.  Uyarıda adlı bir türetilmiş sınıf hiçbir zaman başka ise türetilmiş, ya da kapsayan işlevin nesne oluşturma veya yok etme sırasında çağrılmaz, Uyarı yoksayılabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4437 oluşturur ve yok ortaya kod oluşturma sorunu gösterir `vtordisp` alan.

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

[dynamic_cast İşleci](../../cpp/dynamic-cast-operator.md)<br/>
[vtordisp](../../preprocessor/vtordisp.md)<br/>
[Derleyici Uyarısı (düzey 1) C4436](../../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)