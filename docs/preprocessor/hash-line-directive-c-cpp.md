---
title: '##line yönergesi (C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#line'
helpviewer_keywords:
- preprocessor, directives
- line directive (#line)
- '#line directive'
ms.assetid: 585c1dc4-5184-4f01-98f4-80c1909744d7
ms.openlocfilehash: 35bee779ebf059c20d4a46e27b5ad4cbfb3ce5f3
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220227"
---
# <a name="line-directive-cc"></a>#line yönergesi (C/C++)

**#Line** yönergesi, önişlemcinin derleyicinin dahili olarak depolanan satır numarasını ve dosya adını belirli bir satır numarasına ve dosya adına değiştirmesini söyler.

## <a name="syntax"></a>Sözdizimi

> **#line** *basamak sırası* ["*dosya adı*"]

## <a name="remarks"></a>Açıklamalar

Derleyici, derleme sırasında bulduğu hatalara başvurmak için satır numarası ve isteğe bağlı dosya adını kullanır. Satır numarası genellikle geçerli giriş satırına başvurur ve dosya adı geçerli giriş dosyasına başvurur. Her satır işlendikten sonra satır numarası artırılır.

*Basamak sırası* değeri herhangi bir tamsayı sabiti olabilir. Makro değiştirme, ön işleme belirteçleri üzerinde gerçekleştirilebilir, ancak sonuç doğru sözdizimini değerlendirmelidir. *Dosya adı* herhangi bir karakter bileşimi olabilir ve çift tırnak işaretleri (`" "`) içine alınmalıdır. *Dosya adı* atlanırsa, önceki dosya adı değişmeden kalır.

**#Line** yönergesini yazarak kaynak satır numarasını ve dosya adını değiştirebilirsiniz. Çevirmen, önceden tanımlanmış makroların `__FILE__` ve `__LINE__`değerlerini belirleyebilmek için satır numarasını ve dosya adını kullanır. Bu makroları, kendini açıklayıcı hata iletilerini program metnine eklemek için kullanabilirsiniz. Önceden tanımlanmış bu makrolar hakkında daha fazla bilgi için bkz. [önceden tanımlanmış makrolar](../preprocessor/predefined-macros.md).

Makro, içeriği dosya adı olan ve çift tırnak işaretleriyle (`" "`) çevrelenen bir dizeye genişletilir. `__FILE__`

Satır numarasını ve dosya adını değiştirirseniz, derleyici önceki değerleri yok sayar ve yeni değerleri işlemeye devam eder. **#Line** yönergesi, genellikle hata iletilerinin oluşturulan program yerine özgün kaynak dosyasına başvurmasına neden olacak şekilde program oluşturucuları tarafından kullanılır.

Aşağıdaki örneklerde **#line** ve `__LINE__` `__FILE__` makroları gösterilmektedir.

Bu bildirimde, dahili olarak depolanan satır numarası 151 olarak ayarlanır ve dosya adı Copy. c olarak değiştirilir.

```C
#line 151 "copy.c"
```

Bu örnekte, makro `ASSERT` önceden tanımlı makroları `__LINE__` kullanır ve `__FILE__` belirli bir onaylama doğru değilse kaynak dosyayla ilgili bir hata iletisi yazdırır.

```C
#define ASSERT(cond) if( !(cond) )\
{printf( "assertion error line %d, file(%s)\n", \
__LINE__, __FILE__ );}
```

## <a name="see-also"></a>Ayrıca bkz.

[Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)
