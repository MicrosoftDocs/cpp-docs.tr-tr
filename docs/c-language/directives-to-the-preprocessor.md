---
title: Ön işlemci Yönergeleri
ms.date: 11/04/2016
ms.assetid: adc6251e-cf6b-4508-bdbb-55f446c838d3
ms.openlocfilehash: 520d181c3a58ee2c626678a3afd9126f1ef183cc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62234146"
---
# <a name="directives-to-the-preprocessor"></a>Ön işlemci Yönergeleri

"Direktifi", C Önişlemci 'yi derlemeden önce programın metni üzerinde belirli bir eylemi gerçekleştirmesini söyler. [Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md) , *Önişlemci başvurusunda*tamamen açıklanmıştır. Bu örnek Önişlemci yönergesini `#define`kullanır:

```
#define MAX 100
```

Bu ifade, derleyicisine derlemeden `MAX` `100` önce her oluşumunu değiştirmesini söyler. C derleyicisi Önişlemci yönergeleri şunlardır:

|#define|#endif|#ifdef|#line|
|--------------|-------------|-------------|------------|
|`#elif`|`#error`|**#ifndef**|**#pragma**|
|`#else`|`#if`|`#include`|`#undef`|

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak dosyalar ve kaynak programlar](../c-language/source-files-and-source-programs.md)
