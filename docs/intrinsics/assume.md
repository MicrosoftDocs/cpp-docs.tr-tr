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
ms.openlocfilehash: 06189405703a7cc34f3bd807ec79612394ee899f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368192"
---
# <a name="__assume"></a>__assume

**Microsoft'a Özgü**

Optimize ediciye bir ipucu geçer.

## <a name="syntax"></a>Sözdizimi

```C
__assume(
   expression
)
```

### <a name="parameters"></a>Parametreler

*Ifa -de*\
Doğru olarak değerlendirilecek herhangi bir ifade.

## <a name="remarks"></a>Açıklamalar

En iyi duruma getirici, temsil `expression` edilen koşulun anahtar kelimenin göründüğü ve değiştirilinceye kadar `expression` (örneğin, bir değişkene atama yla) doğru kaldığı noktada doğru olduğunu varsayar. Optimizasyonu geliştirerek `__assume` optimize ediciye aktarılan ipuçlarının seçici kullanımı.

`__assume` İfade bir çelişki olarak yazılmışsa (her zaman yanlışı değerlendiren bir `__assume(0)`ifade), her zaman . Kodunuz beklendiği gibi davranmıyorsa, tanımladığınız `expression` kodun daha önce açıklandığı gibi geçerli ve doğru olduğundan emin olun. Beklenen `__assume(0)` davranış hakkında daha fazla bilgi için daha sonraki açıklamalara bakın.

> [!WARNING]
> Bir program erişilebilir bir `__assume` yolda geçersiz bir deyim içermemelidir. Derleyici geçersiz `__assume` bir bildirime ulaşabilirse, program öngörülemeyen ve tehlikeli olabilecek davranışlara neden olabilir.

`__assume`gerçek bir içsel değildir. Bir işlev olarak bildirilmesi gerekmez ve bir `#pragma intrinsic` yönergede kullanılamaz. Kod oluşturulmasa da, en iyi duruma getirici tarafından oluşturulan kod etkilenir.

Yalnızca `__assume` assert kurtarılamazolduğunda [assert'de](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) kullanın. Derleyici `__assume` hata işleme kodunu en iyi duruma getirebileceğinden, sonraki hata kurtarma kodunun olduğu bir assert'da kullanmayın.

İfade `__assume(0)` özel bir durum. Ulaşılamayan bir kod yolunu belirtmek için kullanın. `__assume(0)` Aşağıdaki örnekte, bir `__assume(0)` anahtar bildiriminin varsayılan durumunda ulaşılamayacağını belirtmek için nasıl kullanılacağı gösterilmektedir. Bu, en tipik `__assume(0)`kullanımını gösterir.

Önceki sürümlerle uyumluluk için **_assume,** derleyici seçeneği [/Za \(Dil uzantıları)](../build/reference/za-ze-disable-language-extensions.md) belirtilmedikçe **__assume** eşanlamlısa eş anlamlıdır.

## <a name="requirements"></a>Gereksinimler

|Içsel|Mimari|
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

Kullanımı, `__assume(0)` en iyi duruma varsayılan servis talebine ulaşılamayacağını söyler. Örnek, programcının tek olası girdinin 1 `p` veya 2 olacağını bildiğini göstermektedir. Başka bir değer için `p`geçirilirse, program geçersiz olur ve öngörülemeyen davranışlara neden olur.

İfadenin `__assume(0)` bir sonucu olarak, derleyici, servis talebi `p` bildiriminde temsil edilmeyen bir değere sahip olup olmadığını sınamak için kod oluşturmaz. Bunun işe yaraması `__assume(0)` için, deyimin varsayılan servis talebinin gövdesindeki ilk deyim olması gerekir.

Derleyici, `__assume` deyimin içindeki `__assume`ifade çalışma zamanında yanlışsa, bu kod doğru çalışmayabilir. İfadenin her zaman çalışma zamanında doğru olacağından emin değilseniz, `assert` kodu korumak için işlevi kullanabilirsiniz.

```C
#define ASSERT(e)    ( ((e) || assert(__FILE__, __LINE__)), __assume(e) )
```

Ne yazık ki, bu kullanım derleyicinin bu belgede daha önce açıklanan varsayılan durum optimizasyonunu gerçekleştirmesini `assert` engeller. Alternatif olarak, aşağıdaki gibi ayrı bir makro kullanabilirsiniz.

```C
#ifdef DEBUG
# define NODEFAULT   ASSERT(0)
#else
# define NODEFAULT   __assume(0)
#endif

   default:
      NODEFAULT;
```

**END Microsoft Özel**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici içsel](../intrinsics/compiler-intrinsics.md)\
[Anahtar sözcükler](../cpp/keywords-cpp.md)
