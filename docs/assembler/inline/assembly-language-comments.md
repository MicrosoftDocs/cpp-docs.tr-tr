---
title: Assembly dili açıklamaları | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 02f4c493bac5c2a066dc0b24e2a566d49345288d
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43683332"
---
# <a name="assembly-language-comments"></a>Assembly Dili Açıklamaları

**Microsoft'a özgü**

Yönergeleri bir `__asm` blok assembly dili açıklamaları kullanabilirsiniz:

```cpp
__asm mov ax, offset buff ; Load address of buff
```

Assembly dili açıklamaları kullanmak C makroları tek mantıksal çizgiye genişletmek için kaçının. (Bkz [__asm bloklarını C makroları olarak tanımlama](../../assembler/inline/defining-asm-blocks-as-c-macros.md).) Bir `__asm` bloğu aynı zamanda C stili yorumlar içerir; daha fazla bilgi için [kullanarak C veya C++ __asm bloklarındaki](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md).

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__asm Bloklarında Bütünleştirilmiş Kod Dili Kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>