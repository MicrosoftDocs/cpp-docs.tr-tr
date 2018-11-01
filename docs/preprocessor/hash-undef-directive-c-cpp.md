---
title: '#undef yönergesi (C/C++)'
ms.date: 11/04/2016
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive'
- undef directive (#undef)
- preprocessor, directives
ms.assetid: 88900e0e-2c19-4a63-b681-f3d3133c24ca
ms.openlocfilehash: cb3a08165e41f336df0e141f50310f191cd83257
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537273"
---
# <a name="undef-directive-cc"></a>#undef Yönergesi (C/C++)
Daha önce `#define` ile oluşturulmuş bir adı kaldırır (tanımsız hale getirir).

## <a name="syntax"></a>Sözdizimi

```
#undef
identifier
```

## <a name="remarks"></a>Açıklamalar

**#Undef** yönergesi, geçerli tanımı kaldırır *tanımlayıcı*. Sonuç olarak, sonraki tekrarı *tanımlayıcı* önişlemci tarafından göz ardı edilir. Makro tanımı kullanarak kaldırmak için **#undef**, yalnızca makronun vermek *tanımlayıcı* ; parametre listesi vermeyin.

Ayrıca uygulayabilirsiniz **#undef** yönerge için önce bir tanımı olan bir tanımlayıcı. Bu tanımlayıcının tanımsız hale gelmesini sağlar. İçinde Makro değişikliği gerçekleştirilmez **#undef** deyimleri.

**#Undef** yönergesi ile eşleştirilir genellikle bir `#define` yönergesi bir tanımlayıcının özel anlama sahip bir kaynak programda bir bölge oluşturmak için. Örneğin, kaynak programın belirli bir işlevi, programın geri kalanını etkilemeyen ortama özgü değerler tanımlamak için bildirim sabitleri kullanabilir. **#Undef** yönergesi ile de çalışır `#if` yönergesi kaynak programın koşullu derlemesini denetlemek için. Bkz: [#if, #elif, #else ve #endif yönergeleri](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md) daha fazla bilgi için.

Aşağıdaki örnekte, **#undef** yönergesi sembolik bir sabitin ve bir makronun tanımlarını kaldırır. Yalnızca makronun tanımlayıcısının belirtildiğine dikkat edin.

```
#define WIDTH 80
#define ADD( X, Y ) ((X) + (Y))
.
.
.
#undef WIDTH
#undef ADD
```

**Microsoft'a özgü**

Makrolar kullanılarak komut satırından tanımsız olabilir `/U` kaldırılacak makro adlarını ardından seçeneği. Bu komutu çalıştırmanın etkisi dizisi ile eşdeğerdir `#undef` *makro adı* dosyasının başında deyimleri.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Ön işlemci Yönergeleri](../preprocessor/preprocessor-directives.md)