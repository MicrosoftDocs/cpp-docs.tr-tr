---
description: 'Daha fazla bilgi edinin: açıklamalar (C++)'
title: Açıklamalar (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- code comments, C++
- comments, documenting code
- comments, C++ code
- white space, C++ comments
ms.assetid: 6fcb906c-c264-4083-84bc-373800b2e514
ms.openlocfilehash: b3bbcafe1f18c791fc5935161b6cdbfae0bf03cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239798"
---
# <a name="comments-c"></a>Açıklamalar (C++)

Açıklama, derleyicinin yoksaydığı ancak programcılar için yararlı bir metindir. Açıklamalar normalde daha sonra başvurmak üzere koda açıklama eklemek için kullanılır. Derleyici bunları boşluk olarak işler. Belirli kod satırlarını devre dışı bırakmak için test sırasında açıklamaları kullanabilirsiniz; Ancak, `#if` / `#endif` Açıklama içeren kodu çevreleyecek ancak açıklamaları iç içe geçirebilmeniz için Önişlemci yönergeleri bunun için daha iyi çalışır.

Bir C++ açıklaması aşağıdaki yollardan biriyle yazılır:

- `/*` (eğik çizgi, yıldız işareti) karakterleri, ardından bir dizi karakter (yeni satırlar dahil) ve onun da ardından `*/` karakterleri gelir. Bu sözdizimi ANSI C ile aynıdır.

- `//` (iki eğik çizgi) karakterlerinin ardından bir dizi karakter gelir. Hemen öncesinde bir ters eğik çizginin gelmediği yeni bir çizgi, bu açıklama formunu sonlandırır. Bu nedenle, buna genellikle "tek çizgilik açıklama" denir.

Açıklama karakterleri (`/*`, `*/` ve `//`); karakter sabiti, dize sabiti veya açıklama içinde herhangi bir özel anlama sahip değildir. Bundan dolayı, ilk sözdizimini kullanan açıklamalar iç içe yerleştirilemez.

## <a name="see-also"></a>Ayrıca bkz.

[Sözcük temelli kurallar](../cpp/lexical-conventions.md)
