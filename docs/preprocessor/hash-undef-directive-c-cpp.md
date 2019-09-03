---
title: '##undef yönergesi (C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive'
- undef directive (#undef)
- preprocessor, directives
ms.assetid: 88900e0e-2c19-4a63-b681-f3d3133c24ca
ms.openlocfilehash: 1a69bc568579e7da7c7e3816cb67c8153b8f1a27
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220209"
---
# <a name="undef-directive-cc"></a>#undef yönergesi (C/C++)

Daha önce `#define` ile oluşturulmuş bir adı kaldırır (tanımsız hale getirir).

## <a name="syntax"></a>Sözdizimi

> **#undef** *tanımlayıcı*

## <a name="remarks"></a>Açıklamalar

**#Undef** yönergesi *tanımlayıcının*geçerli tanımını kaldırır. Sonuç olarak, *tanımlayıcının* sonraki oluşumları ön işlemci tarafından yok sayılır. **#Undef**kullanarak makro tanımını kaldırmak için, bir parametre listesi değil yalnızca makro *tanımlayıcısına*izin verin.

**#Undef** yönergesini, önceki tanımına sahip olmayan bir tanımlayıcıya de uygulayabilirsiniz. Bu tanımlayıcının tanımsız hale gelmesini sağlar. Makro değiştirme **#undef** deyimleri içinde gerçekleştirilmez.

**#Undef** yönergesi, genellikle bir tanımlayıcının özel bir `#define` anlamı olan kaynak programda bir bölge oluşturmak için bir yönergeyle eşleştirilir. Örneğin, kaynak programın belirli bir işlevi, programın geri kalanını etkilemeyen ortama özgü değerler tanımlamak için bildirim sabitleri kullanabilir. **#Undef** yönergesi, kaynak programın koşullu derlemesini `#if` denetlemek için direktifle de birlikte kullanılabilir. Daha fazla bilgi için [#if, #elif, #else ve #endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)yönergelerine bakın.

Aşağıdaki örnekte, **#undef** yönergesi sembolik bir sabit ve Makro tanımlarını kaldırır. Yalnızca makronun tanımlayıcısının belirtildiğine dikkat edin.

```C
#define WIDTH 80
#define ADD( X, Y ) ((X) + (Y))
.
.
.
#undef WIDTH
#undef ADD
```

**Microsoft 'a özgü**

Makrolar, `/U` seçeneğini kullanarak komut satırından ve ardından tanımsız olacak makro adları tarafından tanımsız olabilir. Bu komutu verme etkisi, dosyanın başındaki `#undef` *makro adı* deyimlerinin dizisine eşdeğerdir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)
