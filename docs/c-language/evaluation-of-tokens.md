---
title: Belirteçlerin değerlendirmesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- tokens, evaluating
ms.assetid: 28870b62-dff6-4644-8b75-d58f340b48d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5d5c79ac043b2131df7a876f2de63922c45c9ead
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035285"
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