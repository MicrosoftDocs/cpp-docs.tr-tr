---
title: Satır içi derlemedeki MASM makro yönergeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cfd8e3ca5fb6bf65a288c17b1754d567b2b081a8
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="masm-macro-directives-in-inline-assembly"></a>Satır İçi Derlemedeki MASM Makro Yönergeleri
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Satır içi derleyicisi makro derleyici değil. MASM makro yönergeleri kullanamazsınız (**MAKROSU**, `REPT`, **IRC**, `IRP`, ve `ENDM`) veya makrosu işleçleri (**<>**, **!** , **&**, `%`, ve `.TYPE`). Bir `__asm` blok kullanabileceğiniz C önişlemci yönergeleri, ancak. Bkz: [kullanarak C veya C++ __asm bloklarındaki](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) daha fazla bilgi için.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__asm Bloklarında Bütünleştirilmiş Kod Dili Kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)