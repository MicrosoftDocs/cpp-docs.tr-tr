---
title: "#<a name=\"line-directive-cc--microsoft-docs\"></a>Yönergesi (C/C++) satır | Microsoft Docs"
ms.custom: 
ms.date: 10/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '#line'
dev_langs: C++
helpviewer_keywords:
- preprocessor, directives
- line directive (#line)
- '#line directive'
ms.assetid: 585c1dc4-5184-4f01-98f4-80c1909744d7
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 41886c8107db882ad3bea5a041b529ba8bbbeed6
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="line-directive-cc"></a>#line Yönergesi (C/C++)

`#line` yönergesi, önişlemciye derleyicinin dahili olarak depolanan satır numarasını ve dosya adını belirli bir satır numarası ve dosya adıyla değiştirmesini bildirir.

## <a name="syntax"></a>Sözdizimi

> **#line** *basamak dizisi* ["*filename*"]

## <a name="remarks"></a>Açıklamalar

Derleyici, derleme sırasında bulduğu hatalara başvurmak için satır numarası ve isteğe bağlı dosya adını kullanır. Satır numarası genellikle geçerli giriş satırına başvurur ve dosya adı geçerli giriş dosyasına başvurur. Her satır işlendikten sonra satır numarası artırılır.

*Basamak dizisi* değeri bir tamsayı sabiti olabilir. Makro değiştirme, ön işleme belirteçleri üzerinde gerçekleştirilebilir, ancak sonuç doğru sözdizimini değerlendirmelidir. *Filename* karakterlerin herhangi bir bileşimi olabilir ve çift tırnak içine alınmalıdır (**""**). Varsa *filename* olan atlanırsa, önceki filename değişmeden kalır.

Kaynak satır numarasını ve dosya adını bir `#line` yönergesi yazarak değiştirebilirsiniz. Önceden tanımlı makrolar değerleri belirlemek için satır numarasını ve dosya adı Çeviricisi kullanır **&#95; &#95; Dosya &#95; &#95;**  ve **&#95; &#95; Çizgi &#95; &#95;** . Bu makroları, kendini açıklayıcı hata iletilerini program metnine eklemek için kullanabilirsiniz. Bu önceden tanımlanmış makrolar hakkında daha fazla bilgi için bkz: [önceden tanımlı makrolar](../preprocessor/predefined-macros.md).

**&#95; &#95; Dosya &#95; &#95;**  makro genişler içeriği çift tırnak işaretleri dosya bir dize için (**""**).

Satır numarasını ve dosya adını değiştirirseniz, derleyici önceki değerleri yok sayar ve yeni değerleri işlemeye devam eder. `#line` yönergesi, hata iletilerinin oluşturulan program yerine orijinal kaynak dosyasına başvurmasını sağlamak için genellikle program oluşturucuları tarafından kullanılır.

Aşağıdaki örnekler göstermeye `#line` ve **&#95; &#95; Çizgi &#95; &#95;**  ve **&#95; &#95; Dosya &#95; &#95;**  makroları.

Bu bildirimde dahili olarak depolanan satır numarası 151 için ayarlanır ve dosya adı için copy.c değiştirilir.

```cpp
#line 151 "copy.c"
```

 Bu örnekte, makrosu `ASSERT` önceden tanımlı makrolar kullanan **&#95; &#95; Çizgi &#95; &#95;**  ve **&#95; &#95; Dosya &#95; &#95;**  verilen onaylama doğru değilse, kaynak dosya ile ilgili bir hata iletisi yazdırmak için.

```cpp
#define ASSERT(cond) if( !(cond) )\
{printf( "assertion error line %d, file(%s)\n", \
__LINE__, __FILE__ );}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)