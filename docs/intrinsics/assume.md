---
title: __assume
ms.date: 09/02/2019
f1_keywords:
- __assume
- _assume
- __assume_cpp
helpviewer_keywords:
- __assume keyword [C++]
ms.assetid: d8565123-b132-44b1-8235-5a8c8bff85a7
ms.openlocfilehash: f3f847b5268605bdc5df90a8bbc6a88c78431864
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216967"
---
# <a name="__assume"></a>__assume

**Microsoft 'a özgü**

İyileştiriciye bir ipucu geçirir.

## <a name="syntax"></a>Sözdizimi

```C
__assume(
   expression
)
```

### <a name="parameters"></a>Parametreler

*ifadesini*\
True olarak değerlendirilme kabul edilen herhangi bir ifade.

## <a name="remarks"></a>Açıklamalar

İyileştirici tarafından `expression` temsil edilen koşulun, anahtar sözcüğünün göründüğü ve değiştirilene kadar `expression` doğru kaldığı varsayılır (örneğin, bir değişkene atamaya göre). İyileştiriciye geçirilen ipuçlarının seçmeli kullanımı, iyileştirmeden `__assume` iyileştirebilirler.

Deyim bir çelişki olarak yazılmışsa (her zaman yanlış olarak değerlendirilen bir ifade), her zaman olarak `__assume(0)`değerlendirilir. `__assume` Kodunuz beklenildiği gibi davranmıyorsa, daha önce açıklandığı gibi `expression` tanımladığınız ' ın geçerli ve doğru olduğundan emin olun. Beklenen `__assume(0)` davranış hakkında daha fazla bilgi için, sonraki açıklamalara bakın.

> [!WARNING]
>  Program, erişilebilir bir yol üzerinde geçersiz `__assume` bir ifade içermemelidir. Derleyici geçersiz `__assume` bir deyime ulaşabilirse, program öngörülemeyen ve potansiyel olarak tehlikeli davranışa neden olabilir.

`__assume`orijinal bir iç değer değildir. İşlev olarak bildirilmesini gerektirmez ve bir `#pragma intrinsic` yönergede kullanılamaz. Kod üretilmese de, iyileştirici tarafından oluşturulan kod etkilenir.

Onaylama `__assume` sırasında yalnızca [](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) onay kurtarılabilir olmadığında kullanın. Derleyici hata işleme `__assume` kodunu en uygun hale getirebileceğinden, sonraki hata kurtarma kodunuz olan bir onaylama işlemi kullanmayın.

`__assume(0)` İfade özel bir durumdur. Erişilemeyen `__assume(0)` bir kod yolunu göstermek için kullanın. Aşağıdaki örnek, bir switch ifadesinin varsayılan `__assume(0)` durumunun ulaşılamadığını göstermek için nasıl kullanılacağını gösterir. Bu, en yaygın kullanımını `__assume(0)`gösterir.

Önceki sürümlerle uyumluluk için, [_/za \(devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirlenmediği takdirde bu, **__varsay** için bir eş anlamlı olduğunu **varsayalım** .

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__assume`|x86, ARM, x64, ARM64|

## <a name="example"></a>Örnek

```cpp
// compiler_intrinsics__assume.cpp
#ifdef DEBUG
# define ASSERT(e)    ( ((e) || assert(__FILE__, __LINE__) )
#else
# define ASSERT(e)    ( __assume(e) )
#endif

void func1(int i)
{
}

int main(int p)
{
   switch(p){
      case 1:
         func1(1);
         break;
      case 2:
         func1(-1);
         break;
      default:
         __assume(0);
            // This tells the optimizer that the default
            // cannot be reached. As so, it does not have to generate
            // the extra code to check that 'p' has a value
            // not represented by a case arm. This makes the switch
            // run faster.
   }
}
```

Kullanımı, ön `__assume(0)` iyileştiriciye varsayılan durum ile ulaşılamadığından söyler. Örnek, programcının yalnızca için `p` olası girişlerin 1 veya 2 olacağını bildiği gösterilmektedir. İçin `p`başka bir değer geçirilirse, program geçersiz hale gelir ve öngörülemeyen davranışlara neden olur.

`__assume(0)` İfadesinin sonucu olarak, derleyici bir Case ifadesinde temsil edilmeyen bir değere sahip olup olmadığını `p` test etmek için kod oluşturmaz. Bunun çalışması `__assume(0)` için deyimin, varsayılan durum gövdesinde ilk ifade olması gerekir.

Derleyici temelinde `__assume`kod oluşturduğundan, `__assume` deyim içindeki ifade çalışma zamanında yanlış ise bu kod doğru çalışmayabilir. İfadenin çalışma zamanında her zaman doğru olduğundan emin değilseniz, kodu korumak için `assert` işlevini kullanabilirsiniz.

```C
#define ASSERT(e)    ( ((e) || assert(__FILE__, __LINE__)), __assume(e) )
```

Ne yazık ki, bu `assert` kullanım derleyicinin bu belgede daha önce açıklanan varsayılan büyük/küçük harf iyileştirmesini gerçekleştirmesini engeller. Alternatif olarak, aşağıdaki gibi ayrı bir makro kullanabilirsiniz.

```C
#ifdef DEBUG
# define NODEFAULT   ASSERT(0)
#else
# define NODEFAULT   __assume(0)
#endif

   default:
      NODEFAULT;
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
