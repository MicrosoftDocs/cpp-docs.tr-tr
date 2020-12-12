---
description: 'Daha fazla bilgi edinin: belirteçlerin değerlendirmesi'
title: Belirteçlerin Değerlendirmesi
ms.date: 11/04/2016
helpviewer_keywords:
- tokens, evaluating
ms.assetid: 28870b62-dff6-4644-8b75-d58f340b48d2
ms.openlocfilehash: e22a904956b3f429585c6627a7fb2e8f8da6d222
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196535"
---
# <a name="evaluation-of-tokens"></a>Belirteçlerin Değerlendirmesi

Derleyici belirteçleri yorumlarken, bir sonraki belirtece geçmeden önce tek bir belirtece olabildiğince çok karakteri dahil eder. Bu davranış nedeniyle, belirteçler boşlukla düzgün bir şekilde ayrılmamışsa derleyici bunları istediğiniz gibi yorumlamayabilir. Aşağıdaki ifadeyi göz önünde bulundurun:

```
i+++j
```

Bu örnekte, derleyici önce üç artı işaretinden olası en uzun işleci (`++`) oluşturur, ardından kalan artı işaretini ek işleç (`+`) olarak işler. Bu nedenle, ifade `(i++) + (j)` olarak değil, `(i) + (++j)` olarak yorumlanır. Bu ve benzer durumlarda, belirsizlikten kaçınmak ve uygun ifade değerlendirmesi sağlamak için boşluk ve parantezler kullanın.

**Microsoft'a Özgü**

C derleyicisi, bir CTRL + Z karakterini dosya sonu göstergesi olarak değerlendirir. CTRL+Z'den sonra gelen metni yoksayar.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C belirteçleri](../c-language/c-tokens.md)
