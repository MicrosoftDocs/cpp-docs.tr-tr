---
description: 'Daha fazla bilgi edinin: ön Işlemci yönergeleri'
title: Ön işlemci Yönergeleri
ms.date: 11/04/2016
ms.assetid: adc6251e-cf6b-4508-bdbb-55f446c838d3
ms.openlocfilehash: 50691647436f492b329b6af43a626e933453d3a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213962"
---
# <a name="directives-to-the-preprocessor"></a>Ön işlemci Yönergeleri

"Direktifi", C Önişlemci 'yi derlemeden önce programın metni üzerinde belirli bir eylemi gerçekleştirmesini söyler. [Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md) , *Önişlemci başvurusunda* tamamen açıklanmıştır. Bu örnek Önişlemci yönergesini kullanır `#define` :

```
#define MAX 100
```

Bu ifade, derleyicisine derlemeden önce her oluşumunu değiştirmesini `MAX` söyler `100` . C derleyicisi Önişlemci yönergeleri şunlardır:

|#define|#endif|#ifdef|#line|
|--------------|-------------|-------------|------------|
|`#elif`|`#error`|**#ifndef**|**#pragma**|
|`#else`|`#if`|`#include`|`#undef`|

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak dosyalar ve kaynak programlar](../c-language/source-files-and-source-programs.md)
