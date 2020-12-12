---
description: 'Daha fazla bilgi için: karakter dizileri'
title: Karakter Sıraları
ms.date: 11/04/2016
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
ms.openlocfilehash: ac5642371389047bd8ce3a83e02dc13802167dc0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305084"
---
# <a name="character-sequences"></a>Karakter Sıraları

**ANSI 3.8.2 &** Kaynak dosya karakter sıralarının eşlemesi

Önişlemci deyimleri, kaçış dizilerinin desteklenmemesi dışında kaynak dosyası deyimleriyle aynı karakter kümesini kullanır.

Bu nedenle, bir içerme dosyasına yönelik bir yol belirtmek istediğinizde yalnızca bir ters eğik çizgi kullanın:

```
#include "path1\path2\myfile"
```

Kaynak kodu içinde iki ters eğik çizgi gereklidir:

```
fil = fopen( "path1\\path2\\myfile", "rt" );
```

## <a name="see-also"></a>Ayrıca bkz.

[Ön işleme yönergeleri](../c-language/preprocessing-directives.md)
