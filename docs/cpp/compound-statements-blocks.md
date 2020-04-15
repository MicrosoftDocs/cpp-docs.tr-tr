---
title: Bileşik Deyimler (Bloklar)
ms.date: 11/04/2016
f1_keywords:
- '}'
- '{'
helpviewer_keywords:
- blocks, about blocks
- compound statements
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
ms.openlocfilehash: 60d7e88c5ccccac5a1d967a91c8a82dd954d9afc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337337"
---
# <a name="compound-statements-blocks"></a>Bileşik Deyimler (Bloklar)

Bileşik deyimi kıvırcık ayraçlarla **({ })** kapalı sıfır veya daha fazla ifadeden oluşur. Bileşik deyim, deyim beklenen herhangi bir yerde kullanılabilir. Bileşik deyimlere genellikle "blok" adı verilir.

## <a name="syntax"></a>Sözdizimi

```
{ [ statement-list ] }
```

## <a name="remarks"></a>Açıklamalar

Aşağıdaki örnek, **if** deyiminin *deyimi* nin deyimi olarak bileşik bir ifade kullanır (sözdizimi hakkındaki ayrıntılar için [If Bildirimi'ne](../cpp/if-else-statement-cpp.md) bakın):

```cpp
if( Amount > 100 )
{
    cout << "Amount was too large to handle\n";
    Alert();
}
else
{
    Balance -= Amount;
}
```

> [!NOTE]
> Bir bildirim bir deyim olduğundan, bir bildirim deyim *listesindeki*ifadelerden biri olabilir. Sonuç olarak, bileşik deyim içinde bildirilen, ancak açıkça statik olarak bildirilmeyen adların yerel kapsamı ve (nesneler için) ömrü vardır. Yerel kapsama sahip isimlerin tedavisi yle ilgili ayrıntılar için [Kapsam'a](../cpp/scope-visual-cpp.md) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Deyimlerine Genel Bakış](../cpp/overview-of-cpp-statements.md)
