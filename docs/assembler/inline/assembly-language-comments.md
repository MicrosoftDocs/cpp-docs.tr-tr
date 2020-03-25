---
title: Assembly Dili Açıklamaları
ms.date: 08/30/2018
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
ms.openlocfilehash: a8b2c98c61d58d72e78dbffd4f3b6ed7707d2d7a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169610"
---
# <a name="assembly-language-comments"></a>Assembly Dili Açıklamaları

**Microsoft 'a özgü**

`__asm` bloğundaki yönergeler, derleme dili açıklamalarını kullanabilir:

```cpp
__asm mov ax, offset buff ; Load address of buff
```

C makroları tek bir mantıksal satıra genişletiğinden, makrolarla bütünleştirilmiş kod dili açıklamalarını kullanmaktan kaçının. (Bkz. [__asm bloklarını C makroları olarak tanımlama](../../assembler/inline/defining-asm-blocks-as-c-macros.md).) `__asm` bloğu, C stili açıklamalar da içerebilir; daha fazla bilgi için bkz. [using C C++ veya __asm blokları](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md).

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__asm Bloklarında Bütünleştirilmiş Kod Dili Kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
