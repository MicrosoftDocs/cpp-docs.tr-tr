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
ms.openlocfilehash: 4f4f5ce244be6d7f4e13d7a2abc5d21232c08d9d
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039013"
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

**Microsoft'a Özgü**

Makrolar kullanılarak komut satırından tanımsız olabilir `/U` kaldırılacak makro adlarını ardından seçeneği. Bu komutu çalıştırmanın etkisi dizisi ile eşdeğerdir `#undef` *makro adı* dosyasının başında deyimleri.

**END Microsoft'a Özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Ön işlemci Yönergeleri](../preprocessor/preprocessor-directives.md)