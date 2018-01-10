---
title: "Satır içi derlemedeki MASM makro yönergeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0df9f8584b87e511c43430a5c0df7dac61805ede
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="masm-macro-directives-in-inline-assembly"></a>Satır İçi Derlemedeki MASM Makro Yönergeleri
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Satır içi derleyicisi makro derleyici değil. MASM makro yönergeleri kullanamazsınız (**MAKROSU**, `REPT`, **IRC**, `IRP`, ve `ENDM`) veya makrosu işleçleri (**<>**, **!** ,  **&** , `%`, ve `.TYPE`). Bir `__asm` blok kullanabileceğiniz C önişlemci yönergeleri, ancak. Bkz: [kullanarak C veya C++ __asm bloklarındaki](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) daha fazla bilgi için.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__asm Bloklarında Bütünleştirilmiş Kod Dili Kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)