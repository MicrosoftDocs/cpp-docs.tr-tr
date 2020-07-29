---
title: Assembly Dili Açıklamaları
ms.date: 08/30/2018
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
ms.openlocfilehash: 2e993bd48c7ec801abd440676c80a5bd8f7b42ec
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87192736"
---
# <a name="assembly-language-comments"></a>Assembly Dili Açıklamaları

**Microsoft'a Özgü**

Bir bloktaki yönergeler **`__asm`** , derleme dili açıklamalarını kullanabilir:

```cpp
__asm mov ax, offset buff ; Load address of buff
```

C makroları tek bir mantıksal satıra genişletiğinden, makrolarla bütünleştirilmiş kod dili açıklamalarını kullanmaktan kaçının. (Bkz. [__asm bloklarını C makroları olarak tanımlama](../../assembler/inline/defining-asm-blocks-as-c-macros.md).) Bir **`__asm`** blok, c stili açıklamalar da içerebilir; daha fazla bilgi için bkz. [__asm blokları içinde c veya C++ kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md).

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__Asm bloklarında derleme dili kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
