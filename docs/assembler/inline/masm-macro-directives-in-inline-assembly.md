---
title: Satır İçi Derlemedeki MASM Makro Yönergeleri
ms.date: 08/30/2018
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
ms.openlocfilehash: 38b73346fc52f6b5efe478f8eb960ad049fae924
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169285"
---
# <a name="masm-macro-directives-in-inline-assembly"></a>Satır İçi Derlemedeki MASM Makro Yönergeleri

**Microsoft 'a özgü**

Satır içi assembler bir makro birleştirici değil. Ması makro yönergelerini (**makro**, `REPT`, **IRC**, `IRP`ve `ENDM`) veya makro işleçlerini ( **<>** , **!** , **&** , `%`ve `.TYPE`) kullanamazsınız. Bir `__asm` bloğu C önişlemci yönergelerini kullanabilir, ancak. Daha fazla bilgi için bkz. [C veya C++ __asm bloklarıyla kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__asm Bloklarında Bütünleştirilmiş Kod Dili Kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
