---
title: __assume | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __assume
- __assume_cpp
dev_langs:
- C++
helpviewer_keywords:
- __assume keyword [C++]
ms.assetid: d8565123-b132-44b1-8235-5a8c8bff85a7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ff952e40110c3f56465b0d897fdd5410c0189f1f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="assume"></a>__assume
**Microsoft Specific**  
  
 İpucu iyileştirici geçirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__assume(  
   expression  
)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `expression`  
 True değerlendirileceği varsayılır herhangi bir ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 Koşul tarafından temsil edilen iyileştirici varsayar `expression` anahtar sözcüğü burada görünür ve kadar doğrudur noktasında geçerlidir `expression` (örneğin, tarafından bir değişkene atama) değiştirdi. Tarafından iyileştirici ipuçları seçmeli kullanımını geçirilen `__assume` en iyi duruma getirme artırabilir.  
  
 Varsa `__assume` deyimi çelişki (her zaman yanlış olarak değerlendirilir bir ifade) olarak yazılır, her zaman kabul edilir `__assume(0)`. Kodunuzu beklendiği gibi davranmakta değil, emin `expression` tanımladığınız daha önce açıklandığı gibi geçerli ve doğru olduğundan. Hakkında daha fazla bilgi için beklenen `__assume(0)` davranışı, daha sonra açıklamalar bakın.  
  
> [!WARNING]
>  Bir program geçersiz bir içermemelidir `__assume` ulaşılabilir yolunda deyimi. Geçersiz bir derleyici erişebiliyorsa `__assume` deyimi, program neden olabilecek öngörülemeyen ve potansiyel olarak tehlikeli olabilecek davranışı.  
  
 `__assume` bir orijinal değil iç. Bir işlevi olarak belirtilecek olmadığından ve içinde kullanılamaz bir `#pragma intrinsic` yönergesi. Kod oluşturulur ancak iyileştiricisi tarafından oluşturulan kodu etkilenir.  
  
 Kullanım `__assume` içinde bir [ASSERT](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) yalnızca assert kurtarılabilir olmadığında. Kullanmayın `__assume` sahip olduğunuz sonraki hata kurtarma kodu derleyici hemen hata işleme kodu en iyi duruma çünkü assert içinde.  
  
 `__assume(0)` Açıklamadır bir özel durum. Kullanım `__assume(0)` ulaşılamıyor bir kod yolu belirtmek için. Aşağıdaki örnekte nasıl kullanılacağını gösterir `__assume(0)` switch deyimi varsayılan durumunun ulaşılamıyor belirtmek için. Bu, en tipik kullanımını gösterir `__assume(0)`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__assume`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
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
  
 Kullanımını `__assume(0)` iyileştirici varsayılan durumda ulaşılamıyor söyler. Örnek Programcı yalnızca olası için girdi bilir gösterir `p` 1 veya 2 olacaktır. Başka bir değer geçtiyse `p`, programın geçersiz hale gelir ve beklenmeyen davranışlara neden olur.  
  
 Sonucu olarak `__assume(0)` deyimi, derleyici test etmek için kod oluşturmaz olup olmadığını `p` case deyimi temsil edilmeyen bir değere sahip. Bunun çalışması `__assume(0)` deyimi, varsayılan durumda gövdesi işlemindeki ilk deyim olmalıdır.  
  
 Derleyici göre kod oluşturduğundan `__assume`, varsa bu kodu düzgün çalışmayabilir ifadenin içine `__assume` deyimi false çalışma zamanında. İfade her zaman çalışma zamanında doğru olduğundan emin değilseniz, kullanabileceğiniz `assert` kodu korumak için işlevi.  
  
```  
#define ASSERT(e)    ( ((e) || assert(__FILE__, __LINE__)), __assume(e) )  
```  
  
 Ne yazık ki, bu kullanımını `assert` derleyici bu belgenin önceki bölümlerinde açıklanan varsayılan durumda iyileştirme gerçekleştirmesini engeller. Alternatif olarak, ayrı bir makrosu gibi kullanabilirsiniz.  
  
```  
#ifdef DEBUG  
# define NODEFAULT   ASSERT(0)  
#else  
# define NODEFAULT   __assume(0)  
#endif  
  
   default:  
      NODEFAULT;  
```  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)