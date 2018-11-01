---
title: Karakter Sıraları
ms.date: 11/04/2016
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
ms.openlocfilehash: dea24a2ae5887ea8c0111d8251ba4d9d03ccba0f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50489667"
---
# <a name="character-sequences"></a>Karakter Sıraları

**ANSI 3.8.2** kaynak dosyası karakter dizilerinin eşleme

Önişlemci deyimleri, kaçış dizilerinin desteklenmemesi dışında kaynak dosyası deyimleriyle aynı karakter kümesini kullanır.

Bu nedenle, bir içerme dosyasına yönelik bir yol belirtmek istediğinizde yalnızca bir ters eğik çizgi kullanın:

```
#include "path1\path2\myfile"
```

Kaynak kodu içinde iki ters eğik çizgi gereklidir:

```
fil = fopen( "path1\\path2\\myfile", "rt" );
```

## <a name="see-also"></a>Ayrıca Bkz.

[Ön işleme Yönergeleri](../c-language/preprocessing-directives.md)