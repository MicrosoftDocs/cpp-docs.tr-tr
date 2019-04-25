---
title: Satır İçi Derlemedeki MASM Makro Yönergeleri
ms.date: 08/30/2018
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
ms.openlocfilehash: 7e1bed782d28a5bf7c934c3f57f50aae70038578
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167263"
---
# <a name="masm-macro-directives-in-inline-assembly"></a>Satır İçi Derlemedeki MASM Makro Yönergeleri

**Microsoft'a özgü**

Satır içi assembler macro derleyicisi değil. MASM makro yönergeleri kullanamazsınız (**MAKROSU**, `REPT`, **IRC**, `IRP`, ve `ENDM`) veya makro işleçleri (**<>**, **!** , **&**, `%`, ve `.TYPE`). Bir `__asm` blok kullanabileceğiniz ön işlemci yönergelerini C, ancak. Bkz: [C kullanarak veya C++ __asm bloklarındaki](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) daha fazla bilgi için.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__asm Bloklarında Bütünleştirilmiş Kod Dili Kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>