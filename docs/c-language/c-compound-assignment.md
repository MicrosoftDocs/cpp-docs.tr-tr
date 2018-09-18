---
title: C bileşik atama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C], assignment
- compound assignment operators
- assignment operators, compound
ms.assetid: db7b5893-cd56-4f1c-9981-5a024200ab63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c4450682abbb5efd739b5eb08d228b4c55d00ec
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029331"
---
# <a name="c-compound-assignment"></a>C Bileşik Atama

Bileşik atama işleçleri, başka bir ikili işlecin basit atama işleciyle birleştirin. Bileşik atama işleçleri ek işleci tarafından belirtilen işlemi gerçekleştirmeyi ve ardından sol işleneni sonucu atayın. Örneğin, bir bileşik atama ifadesi gibi

> *İfade1* **+=** *expression2*

olarak anlaşılabilir

> *İfade1* **=** *İfade1* **+** *expression2*

Bileşik atama ifadesi değerlendirilir ancak bileşik atama ifadesi genişletilmiş bir sürümü için eşdeğer olmadığından *İfade1* genişletilmiş sürümü değerlendirir sırasında bir kez  *expression1* iki kez: toplama işlemi ve atama işlemi.

Bileşik atama işlecinin işlenenleri tamsayı veya kayan türde olmalıdır. Her bileşik atama işleci, karşılık gelen ikili işleç gerçekleştirir ve tür işlenenlerini uygun şekilde kısıtlayan dönüştürmeleri gerçekleştirir. Toplama Ataması (`+=`) ve çıkarma Ataması (**-=**) işleçleri çalışması sağ işleneni integral türünde olmalıdır, işaretçi türünde bir sol işleneni de sahip olabilir. Bileşik atama işleminin sonucu, sol işlenen türü ve değeri vardır.

```C
#define MASK 0xff00

n &= MASK;
```

Bu örnekte, üzerinde bir bit düzeyinde kapsamlı-ve işlem gerçekleştirilir `n` ve `MASK`, ve sonucu atandığı `n`. Bildirim sabiti `MASK` ile tanımlanmış bir [#define](../preprocessor/hash-define-directive-c-cpp.md) önişlemci yönergesi.

## <a name="see-also"></a>Ayrıca Bkz.

[C Atama İşleçleri](../c-language/c-assignment-operators.md)