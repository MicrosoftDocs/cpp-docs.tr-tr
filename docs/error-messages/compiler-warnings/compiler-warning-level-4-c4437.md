---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4437'
title: Derleyici Uyarısı (düzey 4) C4437
ms.date: 11/04/2016
f1_keywords:
- C4437
helpviewer_keywords:
- C4437
ms.assetid: dc07e350-20eb-474c-a7ad-f841ae7ec339
ms.openlocfilehash: 6ea94a972c08dfa6752c5c165a9c547419b03334
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251433"
---
# <a name="compiler-warning-level-4-c4437"></a>Derleyici Uyarısı (düzey 4) C4437

' Class1 ' sanal tabandan ' Class2 ' öğesine dynamic_cast, bazı bağlamlarda/VD2 ile derleme veya #pragma vtordisp (2) ile ' Class2 ' tanımlama başarısız olabilir

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Derleyici, **`dynamic_cast`** aşağıdaki özelliklere sahip bir işlemle karşılaştı.

- Atama, bir temel sınıf işaretçisinden türetilmiş sınıf işaretçisine kadar olur.

- Türetilmiş sınıf, temel sınıfı neredeyse devralır.

- Türetilmiş sınıfın `vtordisp` sanal taban için bir alanı yok.

- Cast, türetilmiş sınıfın oluşturucusunda veya yıkıcısında veya türetilmiş sınıftan daha fazla devralan bir sınıf (Aksi takdirde, derleyici uyarısı C4436 verilecek) içinde bulunamadı.

Uyarı, **`dynamic_cast`** kısmen oluşturulmuş bir nesne üzerinde çalışıyorsa doğru şekilde gerçekleştirilemeyebilir.  Bu durum, kapsayan işlev, uyarıda adı geçen türetilmiş sınıfı devralan bir sınıfın oluşturucusundan veya yıkıcısında çağrıldığında oluşur.  Uyarı içinde adı geçen türetilmiş sınıf hiç bir daha alınmadıysa veya nesne oluşturma veya yok etme sırasında kapsayan işlev çağrılmadıysa, uyarı yoksayılabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4437 oluşturur ve eksik alandan oluşan kod oluşturma sorununu gösterir `vtordisp` .

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

## <a name="see-also"></a>Ayrıca bkz.

[dynamic_cast Işleci](../../cpp/dynamic-cast-operator.md)<br/>
[vtordisp](../../preprocessor/vtordisp.md)<br/>
[Derleyici Uyarısı (düzey 1) C4436](../../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)
