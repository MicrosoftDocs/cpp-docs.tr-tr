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

"Yönergesi" metnini program derleme çalıştırılmadan önce belirli bir eylemi gerçekleştirmek için C önişlemcisi bildirir. [Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md) tam olarak açıklanan *önişlemci başvurusu*. Bu örnekte önişlemci yönergesi `#define`:

```
#define MAX 100
```

Bu ifade her örneğini değiştirin derleyiciye `MAX` tarafından `100` derleme önce. C derleyicisi ön işlemci yönergeleri verilmiştir:

|#define|#endif|#ifdef|#line|
|--------------|-------------|-------------|------------|
|`#elif`|`#error`|**#ifndef**|**#pragma**|
|`#else`|`#if`|`#include`|`#undef`|

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Dosyalar ve Kaynak Programlar](../c-language/source-files-and-source-programs.md)
