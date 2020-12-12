---
description: 'Daha fazla bilgi edinin: bileşik deyimler (bloklar)'
title: Bileşik Deyimler (Bloklar)
ms.date: 11/04/2016
f1_keywords:
- '}'
- '{'
helpviewer_keywords:
- blocks, about blocks
- compound statements
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
ms.openlocfilehash: 7defb11a30466949d5a9ca5e86ca1e865fbfe4fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318019"
---
# <a name="compound-statements-blocks"></a>Bileşik Deyimler (Bloklar)

Bileşik deyim, küme ayraçları (**{}**) içine alınmış sıfır veya daha fazla deyimden oluşur. Bileşik deyim, deyim beklenen herhangi bir yerde kullanılabilir. Bileşik deyimlere genellikle "blok" adı verilir.

## <a name="syntax"></a>Syntax

```
{ [ statement-list ] }
```

## <a name="remarks"></a>Açıklamalar

Aşağıdaki örnek, deyimin *ifade* kısmı olarak bir bileşik ifade kullanır **`if`** (söz dizimi hakkında ayrıntılar için [if ifadesine](../cpp/if-else-statement-cpp.md) bakın):

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
> Bir bildirim bir deyim olduğundan, bildirim *deyim listesindeki* deyimlerden biri olabilir. Sonuç olarak, bileşik deyim içinde bildirilen, ancak açıkça statik olarak bildirilmeyen adların yerel kapsamı ve (nesneler için) ömrü vardır. Yerel kapsama sahip adların işlenmesi hakkındaki ayrıntılar için bkz. [kapsam](../cpp/scope-visual-cpp.md) .

## <a name="see-also"></a>Ayrıca bkz.

[C++ deyimlerine genel bakış](../cpp/overview-of-cpp-statements.md)
