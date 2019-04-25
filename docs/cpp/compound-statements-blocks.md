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
ms.openlocfilehash: 6aef2a0b5716ab501fabe80f0dda15080abe3ff5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154870"
---
# <a name="compound-statements-blocks"></a>Bileşik Deyimler (Bloklar)

Bileşik deyim, küme ayraçları içine alınmış sıfır veya daha fazla deyim oluşur (**{}**). Bileşik deyim, deyim beklenen herhangi bir yerde kullanılabilir. Bileşik deyimlere genellikle "blok" adı verilir.

## <a name="syntax"></a>Sözdizimi

```
{ [ statement-list ] }
```

## <a name="remarks"></a>Açıklamalar

Aşağıdaki örnek olarak bileşik deyim kullanır *deyimi* parçası **varsa** deyimi (bkz [if deyimi](../cpp/if-else-statement-cpp.md) sözdizimi hakkında daha fazla ayrıntı için):

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
>  Bir bildirim bir deyim olduğu için bir bildirim deyimlerinde biri olabilir *deyim listesindeki*. Sonuç olarak, bileşik deyim içinde bildirilen, ancak açıkça statik olarak bildirilmeyen adların yerel kapsamı ve (nesneler için) ömrü vardır. Bkz: [kapsam](../cpp/scope-visual-cpp.md) yerel kapsama sahip adların kullanımı hakkındaki ayrıntılar için.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Deyimlerine Genel Bakış](../cpp/overview-of-cpp-statements.md)