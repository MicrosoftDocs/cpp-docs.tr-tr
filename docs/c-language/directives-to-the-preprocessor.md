---
title: Ön İşlemci yönergeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: adc6251e-cf6b-4508-bdbb-55f446c838d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f1ddecf1e205cc9a6d7f09a27fbf243417540e49
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033569"
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