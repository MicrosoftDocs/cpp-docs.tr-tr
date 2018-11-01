---
title: '#Satır yönergesi (C/C++)'
ms.date: 10/18/2017
f1_keywords:
- '#line'
helpviewer_keywords:
- preprocessor, directives
- line directive (#line)
- '#line directive'
ms.assetid: 585c1dc4-5184-4f01-98f4-80c1909744d7
ms.openlocfilehash: e478d287af097081910d192e2ac0fbee6890bfa2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614766"
---
# <a name="line-directive-cc"></a>#line Yönergesi (C/C++)

**#Line** yönergesi, önişlemciye derleyicinin dahili olarak depolanan satır numarasını ve dosya adını bir satır numarasını ve dosya adını değiştirmek söyler.

## <a name="syntax"></a>Sözdizimi

> **#line** *basamak dizisi* ["*filename*"]

## <a name="remarks"></a>Açıklamalar

Derleyici, derleme sırasında bulduğu hatalara başvurmak için satır numarası ve isteğe bağlı dosya adını kullanır. Satır numarası genellikle geçerli giriş satırına başvurur ve dosya adı geçerli giriş dosyasına başvurur. Her satır işlendikten sonra satır numarası artırılır.

*Basamak dizisi* değeri herhangi bir tamsayı sabiti olabilir. Makro değiştirme, ön işleme belirteçleri üzerinde gerçekleştirilebilir, ancak sonuç doğru sözdizimini değerlendirmelidir. *Filename* karakter herhangi bir birleşimi olabilir ve çift tırnak içine alınmalıdır (**""**). Varsa *filename* olan atlanırsa, önceki dosya değişmeden kalır.

Kaynak satır numarasını ve dosya adını yazarak değiştirebilirsiniz bir **#line** yönergesi. Önceden tanımlanmış makrolar değerlerini belirlemek için satır numarasını ve dosya adı translator kullanır `__FILE__` ve `__LINE__`. Bu makroları, kendini açıklayıcı hata iletilerini program metnine eklemek için kullanabilirsiniz. Bu önceden tanımlanmış makrolar hakkında daha fazla bilgi için bkz. [önceden tanımlanmış makrolar](../preprocessor/predefined-macros.md).

`__FILE__` Makro genişler çift tırnak işareti içine alınmış dosya adı olan bir dize (**""**).

Satır numarasını ve dosya adını değiştirirseniz, derleyici önceki değerleri yok sayar ve yeni değerleri işlemeye devam eder. **#Line** yönergesi genellikle program Oluşturucuları tarafından hata iletilerinin oluşturulan program orijinal kaynak dosyasına yerine neden için kullanılır.

Aşağıdaki örnekler gösterir **#line** ve `__LINE__` ve `__FILE__` makroları.

Bu bildirimde dahili olarak depolanan satır numarası 151 olarak ayarlanır ve dosya adı için copy.c değiştirilir.

```cpp
#line 151 "copy.c"
```

Bu örnekte, makro `ASSERT` önceden tanımlanmış makrolar kullanan `__LINE__` ve `__FILE__` belirli bir onaylama işlemi doğru değilse kaynak dosyası hakkında bir hata iletisi yazdırmak için.

```cpp
#define ASSERT(cond) if( !(cond) )\
{printf( "assertion error line %d, file(%s)\n", \
__LINE__, __FILE__ );}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Ön işlemci Yönergeleri](../preprocessor/preprocessor-directives.md)