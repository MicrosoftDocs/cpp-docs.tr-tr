---
description: 'Hakkında daha fazla bilgi edinin: __assume'
title: __assume
ms.date: 09/02/2019
f1_keywords:
- __assume
- _assume
- __assume_cpp
helpviewer_keywords:
- __assume keyword [C++]
ms.assetid: d8565123-b132-44b1-8235-5a8c8bff85a7
ms.openlocfilehash: fd7f275a8b570bc6176f4464ee59f2656328cf30
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337239"
---
# <a name="__assume"></a>__assume

**Microsoft'a Özgü**

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

İyileştirici tarafından temsil edilen koşulun, `expression` anahtar sözcüğünün göründüğü ve değiştirilene kadar doğru kaldığı varsayılır `expression` (örneğin, bir değişkene atamaya göre). İyileştiriciye geçirilen ipuçlarının seçmeli kullanımı, **`__assume`** iyileştirmeden iyileştirebilirler.

**`__assume`** Deyim bir çelişki olarak yazılmışsa (her zaman yanlış olarak değerlendirilen bir ifade), her zaman olarak değerlendirilir `__assume(0)` . Kodunuz beklenildiği gibi davranmıyorsa, `expression` daha önce açıklandığı gibi tanımladığınız ' ın geçerli ve doğru olduğundan emin olun. Beklenen davranış hakkında daha fazla bilgi için `__assume(0)` , sonraki açıklamalara bakın.

> [!WARNING]
> Program, **`__assume`** erişilebilir bir yol üzerinde geçersiz bir ifade içermemelidir. Derleyici geçersiz bir deyime ulaşabilirse **`__assume`** , program öngörülemeyen ve potansiyel olarak tehlikeli davranışa neden olabilir.

`__assume` orijinal bir iç değer değildir. İşlev olarak bildirilmesini gerektirmez ve bir `#pragma intrinsic` yönergede kullanılamaz. Kod üretilmese de, iyileştirici tarafından oluşturulan kod etkilenir.

Onaylama sırasında **`__assume`** yalnızca [](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) onay kurtarılabilir olmadığında kullanın. **`__assume`** Derleyici hata işleme kodunu en uygun hale getirebileceğinden, sonraki hata kurtarma kodunuz olan bir onaylama işlemi kullanmayın.

`__assume(0)`İfade özel bir durumdur. `__assume(0)`Erişilemeyen bir kod yolunu göstermek için kullanın. Aşağıdaki örnek, `__assume(0)` bir switch ifadesinin varsayılan durumunun ulaşılamadığını göstermek için nasıl kullanılacağını gösterir. Bu, en yaygın kullanımını gösterir `__assume(0)` .

Önceki sürümlerle uyumluluk için, **`_assume`** **`__assume`** [/za \( Disable dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirlenmediği için bir eş anlamlı.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|**`__assume`**|x86, ARM, x64, ARM64|

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

Kullanımı, `__assume(0)` ön iyileştiriciye varsayılan durum ile ulaşılamadığından söyler. Örnek, programcının yalnızca için olası girişlerin `p` 1 veya 2 olacağını bildiği gösterilmektedir. İçin başka bir değer geçirilirse `p` , program geçersiz hale gelir ve öngörülemeyen davranışlara neden olur.

İfadesinin sonucu olarak `__assume(0)` , derleyici `p` bir Case ifadesinde temsil edilmeyen bir değere sahip olup olmadığını test etmek için kod oluşturmaz. Bunun çalışması için `__assume(0)` deyimin, varsayılan durum gövdesinde ilk ifade olması gerekir.

Derleyici temelinde kod oluşturduğundan **`__assume`** , deyim içindeki ifade **`__assume`** çalışma zamanında yanlış ise bu kod doğru çalışmayabilir. İfadenin çalışma zamanında her zaman doğru olduğundan emin değilseniz, `assert` kodu korumak için işlevini kullanabilirsiniz.

```C
#define ASSERT(e)    ( ((e) || assert(__FILE__, __LINE__)), __assume(e) )
```

Ne yazık ki, bu kullanım `assert` derleyicinin bu belgede daha önce açıklanan varsayılan büyük/küçük harf iyileştirmesini gerçekleştirmesini engeller. Alternatif olarak, aşağıdaki gibi ayrı bir makro kullanabilirsiniz.

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
[Anahtar sözcükler](../cpp/keywords-cpp.md)
