---
title: Assembly Dili Açıklamaları
ms.date: 08/30/2018
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
ms.openlocfilehash: fc37658eccd99b61d45aa9a9a7a2675ef90eee89
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167250"
---
# <a name="assembly-language-comments"></a>Assembly Dili Açıklamaları

**Microsoft'a özgü**

Yönergeleri bir `__asm` blok assembly dili açıklamaları kullanabilirsiniz:

```cpp
__asm mov ax, offset buff ; Load address of buff
```

Assembly dili açıklamaları kullanmak C makroları tek mantıksal çizgiye genişletmek için kaçının. (Bkz [__asm bloklarını C makroları olarak tanımlama](../../assembler/inline/defining-asm-blocks-as-c-macros.md).) Bir `__asm` bloğu aynı zamanda C stili yorumlar içerir; daha fazla bilgi için [C kullanarak veya C++ __asm bloklarındaki](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md).

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__asm Bloklarında Bütünleştirilmiş Kod Dili Kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>