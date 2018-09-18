---
title: Bileşik deyimler (bloklar) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '}'
- '{'
dev_langs:
- C++
helpviewer_keywords:
- blocks, about blocks
- compound statements
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89e243dd1905e61a6c9a1b16c1936d7d6617ba17
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116821"
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