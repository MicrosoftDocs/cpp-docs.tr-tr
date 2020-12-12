---
description: 'Daha fazla bilgi edinin: #undef yönergesi (C/C++)'
title: '##undef yönergesi (C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive'
- undef directive (#undef)
- preprocessor, directives
ms.assetid: 88900e0e-2c19-4a63-b681-f3d3133c24ca
ms.openlocfilehash: 20dfd1d0b26f18a26e7ad407704d6cb0ffd563bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300466"
---
# <a name="undef-directive-cc"></a>#undef yönergesi (C/C++)

Daha önce `#define` ile oluşturulmuş bir adı kaldırır (tanımsız hale getirir).

## <a name="syntax"></a>Syntax

> **#undef** *tanımlayıcı*

## <a name="remarks"></a>Açıklamalar

**#Undef** yönergesi *tanımlayıcının* geçerli tanımını kaldırır. Sonuç olarak, *tanımlayıcının* sonraki oluşumları ön işlemci tarafından yok sayılır. **#Undef** kullanarak makro tanımını kaldırmak için, bir parametre listesi değil yalnızca makro *tanımlayıcısına* izin verin.

**#Undef** yönergesini, önceki tanımına sahip olmayan bir tanımlayıcıya de uygulayabilirsiniz. Bu tanımlayıcının tanımsız hale gelmesini sağlar. Makro değiştirme **#undef** deyimleri içinde gerçekleştirilmez.

**#Undef** yönergesi, genellikle bir `#define` tanımlayıcının özel bir anlamı olan kaynak programda bir bölge oluşturmak için bir yönergeyle eşleştirilir. Örneğin, kaynak programın belirli bir işlevi, programın geri kalanını etkilemeyen ortama özgü değerler tanımlamak için bildirim sabitleri kullanabilir. **#Undef** yönergesi, `#if` kaynak programın koşullu derlemesini denetlemek için direktifle de birlikte kullanılabilir. Daha fazla bilgi için [#if, #elif, #else ve #endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)yönergelerine bakın.

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

**Microsoft'a Özgü**

Makrolar, seçeneğini kullanarak komut satırından ve `/U` ardından tanımsız olacak makro adları tarafından tanımsız olabilir. Bu komutu verme etkisi, `#undef` dosyanın başındaki *makro adı* deyimlerinin dizisine eşdeğerdir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Ön işlemci yönergeleri](../preprocessor/preprocessor-directives.md)
