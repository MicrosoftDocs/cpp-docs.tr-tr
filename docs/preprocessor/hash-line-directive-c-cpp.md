---
title: '#Yönergesi (C/C++) satır | Microsoft Docs'
ms.custom: ''
ms.date: 10/18/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#line'
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, directives
- line directive (#line)
- '#line directive'
ms.assetid: 585c1dc4-5184-4f01-98f4-80c1909744d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ebbcea7432b27e9269b5041d90d14534a77b812
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="line-directive-cc"></a>#line Yönergesi (C/C++)

`#line` yönergesi, önişlemciye derleyicinin dahili olarak depolanan satır numarasını ve dosya adını belirli bir satır numarası ve dosya adıyla değiştirmesini bildirir.

## <a name="syntax"></a>Sözdizimi

> **#line** *basamak dizisi* ["*filename*"]

## <a name="remarks"></a>Açıklamalar

Derleyici, derleme sırasında bulduğu hatalara başvurmak için satır numarası ve isteğe bağlı dosya adını kullanır. Satır numarası genellikle geçerli giriş satırına başvurur ve dosya adı geçerli giriş dosyasına başvurur. Her satır işlendikten sonra satır numarası artırılır.

*Basamak dizisi* değeri bir tamsayı sabiti olabilir. Makro değiştirme, ön işleme belirteçleri üzerinde gerçekleştirilebilir, ancak sonuç doğru sözdizimini değerlendirmelidir. *Filename* karakterlerin herhangi bir bileşimi olabilir ve çift tırnak içine alınmalıdır (**""**). Varsa *filename* olan atlanırsa, önceki filename değişmeden kalır.

Kaynak satır numarasını ve dosya adını bir `#line` yönergesi yazarak değiştirebilirsiniz. Önceden tanımlı makrolar değerleri belirlemek için satır numarasını ve dosya adı Çeviricisi kullanır **&#95; &#95;dosya&#95; &#95;** ve **&#95; &#95;satır&#95; &#95;**. Bu makroları, kendini açıklayıcı hata iletilerini program metnine eklemek için kullanabilirsiniz. Bu önceden tanımlanmış makrolar hakkında daha fazla bilgi için bkz: [önceden tanımlı makrolar](../preprocessor/predefined-macros.md).

**&#95; &#95;Dosya&#95; &#95;** makro genişler içeriği çift tırnak işaretleri dosya bir dize için (**""**).

Satır numarasını ve dosya adını değiştirirseniz, derleyici önceki değerleri yok sayar ve yeni değerleri işlemeye devam eder. `#line` yönergesi, hata iletilerinin oluşturulan program yerine orijinal kaynak dosyasına başvurmasını sağlamak için genellikle program oluşturucuları tarafından kullanılır.

Aşağıdaki örnekler göstermeye `#line` ve **&#95; &#95;satır&#95; &#95;** ve **&#95; &#95;dosya&#95; &#95;** makroları.

Bu bildirimde dahili olarak depolanan satır numarası 151 için ayarlanır ve dosya adı için copy.c değiştirilir.

```cpp
#line 151 "copy.c"
```

 Bu örnekte, makrosu `ASSERT` önceden tanımlı makrolar kullanan **&#95; &#95;satır&#95; &#95;** ve **&#95; &#95;dosya&#95; &#95;** yazdırmak için bir belirli bir onaylama doğru değilse, kaynak dosya ile ilgili hata iletisi.

```cpp
#define ASSERT(cond) if( !(cond) )\
{printf( "assertion error line %d, file(%s)\n", \
__LINE__, __FILE__ );}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Ön işlemci Yönergeleri](../preprocessor/preprocessor-directives.md)