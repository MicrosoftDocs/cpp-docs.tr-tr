---
title: Ön işlemci Yönergeleri
ms.date: 11/04/2016
ms.assetid: adc6251e-cf6b-4508-bdbb-55f446c838d3
ms.openlocfilehash: 0abc21f38f5776acd9167f0526160dc5e1bb8cbb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50450078"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Dosyalar ve Kaynak Programlar](../c-language/source-files-and-source-programs.md)