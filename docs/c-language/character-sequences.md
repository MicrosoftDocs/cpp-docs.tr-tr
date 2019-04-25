---
title: Karakter Sıraları
ms.date: 11/04/2016
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
ms.openlocfilehash: 42fb6b61771feb3eaedfb4ce1e674003df91b263
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62312693"
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

## <a name="see-also"></a>Ayrıca bkz.

[Ön işleme Yönergeleri](../c-language/preprocessing-directives.md)
