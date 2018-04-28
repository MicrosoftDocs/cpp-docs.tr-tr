---
title: Assembly dili açıklamaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 048635a874db604f872b4fa87d72bd06d0455438
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="assembly-language-comments"></a>Assembly Dili Açıklamaları
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 ' Ndaki yönergeleri bir `__asm` blok assembly dili açıklamaları kullanabilirsiniz:  
  
```  
__asm mov ax, offset buff ; Load address of buff  
```  
  
 Tek bir mantıksal satıra C makroları genişletmek için assembly dili açıklamaları makroları kullanmaktan kaçının. (Bkz [__asm bloklarını C makroları olarak tanımlama](../../assembler/inline/defining-asm-blocks-as-c-macros.md).) Bir `__asm` bloğu için ayrıca C tarzı açıklamaları içerir; daha fazla bilgi için bkz: [kullanarak C veya C++ __asm bloklarındaki](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md).  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__asm Bloklarında Bütünleştirilmiş Kod Dili Kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)