---
title: C Bileşik Atama
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C], assignment
- compound assignment operators
- assignment operators, compound
ms.assetid: db7b5893-cd56-4f1c-9981-5a024200ab63
ms.openlocfilehash: 102f53378430074a59636eb18488a7ab51289731
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445142"
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