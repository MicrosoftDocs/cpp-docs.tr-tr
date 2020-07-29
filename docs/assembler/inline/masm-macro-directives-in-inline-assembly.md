---
title: Satır İçi Derlemedeki MASM Makro Yönergeleri
ms.date: 08/30/2018
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
ms.openlocfilehash: 964f70aeef6e0e62ac4b941b2cc26d3e7c7ef466
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87191802"
---
# <a name="masm-macro-directives-in-inline-assembly"></a>Satır İçi Derlemedeki MASM Makro Yönergeleri

**Microsoft'a Özgü**

Satır içi assembler bir makro birleştirici değil. Ması makro yönergelerini (**makro**, `REPT` , **IRC**, `IRP` , ve `ENDM` ) veya makro işleçlerini ( **<>** , **!**, **&** , `%` ve `.TYPE` ) kullanamazsınız. Bir **`__asm`** blok C önişlemci yönergelerini kullanabilir, ancak. Daha fazla bilgi için bkz. [__asm bloklarında C veya C++ kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__Asm bloklarında derleme dili kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
