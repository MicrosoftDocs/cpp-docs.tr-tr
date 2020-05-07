---
title: C Bileşik Atama
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C], assignment
- compound assignment operators
- assignment operators, compound
ms.assetid: db7b5893-cd56-4f1c-9981-5a024200ab63
ms.openlocfilehash: 39a9391e2a62a59c5e7fd7937c1f3d12509b76ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327905"
---
# <a name="c-compound-assignment"></a>C Bileşik Atama

Bileşik atama işleçleri basit atama işlecini başka bir ikili işleçle birleştirir. Bileşik atama işleçleri ek işleç tarafından belirtilen işlemi gerçekleştirir, ardından sonucu sol işlenene atar. Örneğin, gibi bir bileşik atama ifadesi

> *İfade1* **+=** *İfade2*

şöyle anlaşılabilirler

> *İfade1* **=** *expression1* İfade1 **+** *İfade2*

Ancak, bileşik atama ifadesi *İfade1* ' i yalnızca bir kez değerlendirirken, genişletilmiş sürüm *İfade1* ' i iki kez değerlendirirken, bileşik atama ifadesi genişletilmiş sürüme eşit değildir.

Birleşik atama işlecinin işlenenleri integral veya kayan türde olmalıdır. Her bileşik atama işleci, karşılık gelen ikili işlecin gerçekleştirdiği dönüştürmeleri gerçekleştirir ve işlenenlerinin türlerini uygun şekilde kısıtlar. Ekleme-atama (`+=`) ve çıkarma atama (**-=**) işleçleri Ayrıca işaretçi türünün bir sol işlenenine sahip olabilir, bu durumda sağ işlenen integral türünde olmalıdır. Birleşik atama işleminin sonucu, sol işlenenin değerine ve türüne sahiptir.

```C
#define MASK 0xff00

n &= MASK;
```

Bu örnekte, ve `n` `MASK`ÜZERINDE bit düzeyinde kapsamlı ve bir işlem gerçekleştirilir ve sonuç öğesine `n`atanır. Bildirim sabiti `MASK` , bir [#define](../preprocessor/hash-define-directive-c-cpp.md) Önişlemci yönergesi ile tanımlanmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[C Atama İşleçleri](../c-language/c-assignment-operators.md)
