---
title: "Assembly dili açıklamaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8b93f00aac6151471c1e36b29b2d9f5c3cdbdc1f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [__Asm bloklarında derleme dili kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)