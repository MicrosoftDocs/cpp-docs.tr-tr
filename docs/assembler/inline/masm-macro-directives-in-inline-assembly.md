---
description: Daha fazla bilgi için bkz. satır Içi derlemede MASMMACRO yönergeleri
title: Satır İçi Derlemedeki MASM Makro Yönergeleri
ms.date: 08/30/2018
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
ms.openlocfilehash: 131066ad117e0f314ba0900e8ecd19eb4843c25b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117568"
---
# <a name="masm-macro-directives-in-inline-assembly"></a>Satır İçi Derlemedeki MASM Makro Yönergeleri

**Microsoft'a Özgü**

Satır içi assembler bir makro birleştirici değil. Ması makro yönergelerini (**makro**, `REPT` , **IRC**, `IRP` , ve `ENDM` ) veya makro işleçlerini ( **<>** , **!**, **&** , `%` ve `.TYPE` ) kullanamazsınız. Bir **`__asm`** blok C önişlemci yönergelerini kullanabilir, ancak. Daha fazla bilgi için bkz. [__asm bloklarında C veya C++ kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__Asm bloklarında derleme dili kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
