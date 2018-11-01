---
title: Açıklamaları (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- code comments, C++
- comments, documenting code
- comments, C++ code
- white space, C++ comments
ms.assetid: 6fcb906c-c264-4083-84bc-373800b2e514
ms.openlocfilehash: a90d9d37e69cb2e8be4ab18f77026fdce1221307
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506112"
---
# <a name="comments-c"></a>Açıklamaları (C++)

Açıklama, derleyicinin yoksaydığı ancak programcılar için yararlı bir metindir. Açıklamalar normalde daha sonra başvurmak üzere koda açıklama eklemek için kullanılır. Derleyici bunları boşluk olarak işler. Kodun belirli satırlarını etkin hale getirmek için test açıklamaları kullanabilirsiniz; Ancak, `#if` / `#endif` önişlemci yönergeleri çalışması daha iyi bu çünkü açıklamaları içeren kodu çevreleyebilirsiniz ancak açıklamaları iç içe olamaz.

Bir C++ açıklaması aşağıdaki yollardan biriyle yazılır:

- `/*` (eğik çizgi, yıldız işareti) karakterleri, ardından bir dizi karakter (yeni satırlar dahil) ve onun da ardından `*/` karakterleri gelir. Bu sözdizimi ANSI C ile aynıdır.

- `//` (iki eğik çizgi) karakterlerinin ardından bir dizi karakter gelir. Hemen öncesinde bir ters eğik çizginin gelmediği yeni bir çizgi, bu açıklama formunu sonlandırır. Bu nedenle, buna genellikle "tek çizgilik açıklama" denir.

Açıklama karakterleri (`/*`, `*/` ve `//`); karakter sabiti, dize sabiti veya açıklama içinde herhangi bir özel anlama sahip değildir. Bundan dolayı, ilk sözdizimini kullanan açıklamalar iç içe yerleştirilemez.

## <a name="see-also"></a>Ayrıca bkz.

[Sözcük Temelli Kurallar](../cpp/lexical-conventions.md)