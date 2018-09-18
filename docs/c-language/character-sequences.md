---
title: Karakter sıraları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5cf3b52b8a4e76062d06b0b9ca3d4535b79595c5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061519"
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