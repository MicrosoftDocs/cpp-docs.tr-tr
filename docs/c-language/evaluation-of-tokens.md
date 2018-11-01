---
title: Belirteçlerin Değerlendirmesi
ms.date: 11/04/2016
helpviewer_keywords:
- tokens, evaluating
ms.assetid: 28870b62-dff6-4644-8b75-d58f340b48d2
ms.openlocfilehash: c54b497464d68a9e6c6048a93119726e14ef4718
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482062"
---
# <a name="evaluation-of-tokens"></a>Belirteçlerin Değerlendirmesi

Derleyici belirteçleri yorumlarken, bir sonraki belirtece geçmeden önce tek bir belirtece olabildiğince çok karakteri dahil eder. Bu davranış nedeniyle, belirteçler boşlukla düzgün bir şekilde ayrılmamışsa derleyici bunları istediğiniz gibi yorumlamayabilir. Aşağıdaki ifadeyi göz önünde bulundurun:

```
i+++j
```

Bu örnekte, derleyici önce üç artı işaretinden olası en uzun işleci (`++`) oluşturur, ardından kalan artı işaretini ek işleç (`+`) olarak işler. Bu nedenle, ifade `(i++) + (j)` olarak değil, `(i) + (++j)` olarak yorumlanır. Bu ve benzer durumlarda, belirsizlikten kaçınmak ve uygun ifade değerlendirmesi sağlamak için boşluk ve parantezler kullanın.

**Microsoft'a özgü**

C derleyicisi, bir CTRL + Z karakterini dosya sonu göstergesi olarak değerlendirir. CTRL+Z'den sonra gelen metni yoksayar.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[C Belirteçleri](../c-language/c-tokens.md)