---
title: Açıklamalar (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- code comments, C++
- comments, documenting code
- comments, C++ code
- white space, C++ comments
ms.assetid: 6fcb906c-c264-4083-84bc-373800b2e514
ms.openlocfilehash: 3326ad7d0b5118182a5d582061fd0c103986f232
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189760"
---
# <a name="comments-c"></a>Açıklamalar (C++)

Açıklama, derleyicinin yoksaydığı ancak programcılar için yararlı bir metindir. Açıklamalar normalde daha sonra başvurmak üzere koda açıklama eklemek için kullanılır. Derleyici bunları boşluk olarak işler. Belirli kod satırlarını devre dışı bırakmak için test sırasında açıklamaları kullanabilirsiniz; Ancak, açıklama içeren kodu çevreleyecek ancak açıklamaları iç içe geçirebilmeniz için, `#if`/`#endif` Önişlemci yönergeleri bu şekilde daha iyi çalışır.

Bir C++ açıklaması aşağıdaki yollardan biriyle yazılır:

- `/*` (eğik çizgi, yıldız işareti) karakterleri, ardından bir dizi karakter (yeni satırlar dahil) ve onun da ardından `*/` karakterleri gelir. Bu sözdizimi ANSI C ile aynıdır.

- `//` (iki eğik çizgi) karakterlerinin ardından bir dizi karakter gelir. Hemen öncesinde bir ters eğik çizginin gelmediği yeni bir çizgi, bu açıklama formunu sonlandırır. Bu nedenle, buna genellikle "tek çizgilik açıklama" denir.

Açıklama karakterleri (`/*`, `*/` ve `//`); karakter sabiti, dize sabiti veya açıklama içinde herhangi bir özel anlama sahip değildir. Bundan dolayı, ilk sözdizimini kullanan açıklamalar iç içe yerleştirilemez.

## <a name="see-also"></a>Ayrıca bkz.

[Sözcük Temelli Kurallar](../cpp/lexical-conventions.md)
