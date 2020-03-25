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
ms.openlocfilehash: cd0e5daa2232f17a34bee2f0d8b9569e524fbf34
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189565"
---
# <a name="compound-statements-blocks"></a>Bileşik Deyimler (Bloklar)

Bileşik deyim, küme ayraçları ( **{}** ) içine alınmış sıfır veya daha fazla deyimden oluşur. Bileşik deyim, deyim beklenen herhangi bir yerde kullanılabilir. Bileşik deyimlere genellikle "blok" adı verilir.

## <a name="syntax"></a>Sözdizimi

```
{ [ statement-list ] }
```

## <a name="remarks"></a>Açıklamalar

Aşağıdaki örnek, **if** ifadesinin *ifade* parçası olarak bir bileşik ifade kullanır (söz dizimi hakkında ayrıntılar için [IF ifadesine](../cpp/if-else-statement-cpp.md) bakın):

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
>  Bir bildirim bir deyim olduğundan, bildirim *deyim listesindeki*deyimlerden biri olabilir. Sonuç olarak, bileşik deyim içinde bildirilen, ancak açıkça statik olarak bildirilmeyen adların yerel kapsamı ve (nesneler için) ömrü vardır. Yerel kapsama sahip adların işlenmesi hakkındaki ayrıntılar için bkz. [kapsam](../cpp/scope-visual-cpp.md) .

## <a name="see-also"></a>Ayrıca bkz.

[C++ Deyimlerine Genel Bakış](../cpp/overview-of-cpp-statements.md)
