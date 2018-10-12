---
title: __assume | Microsoft Docs
ms.custom: ''
ms.date: 10/09/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __assume
- _assume
- __assume_cpp
dev_langs:
- C++
helpviewer_keywords:
- __assume keyword [C++]
ms.assetid: d8565123-b132-44b1-8235-5a8c8bff85a7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41542065a4fc7d3b90fd3159dca4c7a7d169c115
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163679"
---
# <a name="assume"></a>__assume

**Microsoft'a özgü**

İyileştirici ipucu geçirir.

## <a name="syntax"></a>Sözdizimi

```
__assume(
   expression
)
```

#### <a name="parameters"></a>Parametreler

*İfade*<br/>
Doğru olarak değerlendirilebilmesi için kabul herhangi bir ifade.

## <a name="remarks"></a>Açıklamalar

Koşul tarafından temsil edilen iyileştirici varsayar `expression` burada anahtar sözcüğü görünür ve kadar doğrudur noktasında geçerlidir `expression` (örneğin, tarafından bir değişkene atama) değiştirdi. İyileştirici tarafından geçirilen ipuçları seçmeli kullanımını `__assume` iyileştirme artırabilir.

Varsa `__assume` deyimi bir çelişki (her zaman false olarak değerlendirilen bir ifade) olarak yazılır, bu her zaman değerlendirilir `__assume(0)`. Kodunuzu beklendiği gibi davranmayan, emin `expression` tanımladığınız daha önce açıklandığı gibi geçerli ve doğru olduğundan. Hakkında daha fazla bilgi için beklenen `__assume(0)` davranışı, daha sonra açıklamalara bakın.

> [!WARNING]
>  Bir program, geçersiz bir içermemelidir `__assume` erişilebilir bir yolda bildirimi. Geçersiz bir derleyici erişebiliyorsa `__assume` deyimi, programın öngörülemeyen ve potansiyel olarak tehlikeli olabilecek davranışını açabilir.

`__assume` bir orijinal olmayan iç. Bildirilen bir işlev olarak gerekmez ve içinde kullanılamaz bir `#pragma intrinsic` yönergesi. İyileştirici tarafından oluşturulan kodu, kod oluşturulmasına rağmen etkilenir.

Kullanım `__assume` içinde bir [ASSERT](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) yalnızca assert kurtarılabilir olmadığında. Kullanmayın `__assume` içinde olan sonraki hata kurtarma kodu derleyici hemen hata işleme kodu En İyileştir çünkü bir onaylamadır.

`__assume(0)` Bir özel durum bir ifadedir. Kullanım `__assume(0)` erişilemeyen kod yolu belirtmek için. Aşağıdaki örnek nasıl kullanılacağını gösterir `__assume(0)` switch deyimi varsayılan durumunun ulaşılamıyor belirtmek için. Bu en tipik kullanımını gösterir `__assume(0)`.

Önceki sürümlerle uyumluluk için **_assume** eşanlamlıdır **__assume** sürece derleyici seçeneği [/Za \(dil uzantılarını devre dışı bırak)](../build/reference/za-ze-disable-language-extensions.md) olduğu Belirtilen.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__assume`|x86, ARM, x64|

## <a name="example"></a>Örnek

```
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

Kullanımını `__assume(0)` iyileştirici varsayılan durumda ulaşılamıyor söyler. Örnek için tek olası girdi Programcı bilir gösterir `p` 1 veya 2 olacaktır. Başka bir değer geçtiyse `p`, program geçersiz hale gelir ve öngörülemeyen davranışlara neden olur.

Sonucu olarak `__assume(0)` ifade, derleyicinin test etmek için kod oluşturmaz olmadığını `p` case deyiminde temsil edilmeyen bir değere sahip. Bunun çalışması `__assume(0)` deyimi varsayılan durumunun gövdesinde ilk deyim olmalıdır.

Derleyici göre kod oluşturur çünkü `__assume`, bu kod, doğru çalışmayabilir içindeki ifade `__assume` deyimi çalışma zamanında false'dur. İfade her zaman çalışma zamanında doğru olduğundan emin değilseniz, kullanabileceğiniz `assert` kod korumak için işlevi.

```
#define ASSERT(e)    ( ((e) || assert(__FILE__, __LINE__)), __assume(e) )
```

Ne yazık ki bu kullanımını `assert` derleyici, bu belgenin önceki bölümlerinde açıklanan varsayılan örneği iyileştirme gerçekleştirmesini engeller. Alternatif olarak, ayrı bir makro şu şekilde kullanabilirsiniz.

```
#ifdef DEBUG
# define NODEFAULT   ASSERT(0)
#else
# define NODEFAULT   __assume(0)
#endif

   default:
      NODEFAULT;
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)