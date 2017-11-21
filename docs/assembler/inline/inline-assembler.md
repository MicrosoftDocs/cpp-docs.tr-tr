---
title: "Satır içi derleyicisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- assembler [C++]
- assembler [C++], inline
- assembly language [C++], inline
- inline assembler [C++]
- inline assembly [C++]
ms.assetid: 7e13f18f-3628-4306-8b81-4a6d09c043fe
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 22f428a21af037b86e063261003baf9849357c9e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="inline-assembler"></a>Satır İçi Derleyicisi
**Microsoft özel**  
  
 Derleme dili; program hızını geliştirmek, bellek ihtiyaçlarını azaltmak ve donanımı denetlemek gibi pek çok amaca hizmet eder. Derleme dili talimatlarını ek derleme ve bağlama adımı olmadan doğrudan C ve C++ kaynaklı programlarınıza katıştırmak için satır içi derleyiciyi kullanabilirsiniz. Satır içi assembler derleyici içinde yerleşik olarak bulunur, böylece, Microsoft Makro Çevirici (MASM) gibi ayrı bir derleyici gerekmez.  
  
> [!NOTE]
>  Satır içi derleme kodu içeren programlar diğer donanım platformlarına tamamen taşınamaz. Taşınabilirlik için tasarlıyorsanız, satır içi derleyici kullanmaktan kaçının.  
  
 Satır içi derleme ARM üzerinde desteklenmiyor ve [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] işlemci.  Aşağıdaki konular, Visual C/C++ satır içi birleştirici/ayırıcı ile x86 işlemcilerin nasıl kullanıldığını açıklar:  
  
-   [Satır içi derleyiciye genel bakış](../../assembler/inline/inline-assembler-overview.md)  
  
-   [Satır içi derleme avantajları](../../assembler/inline/advantages-of-inline-assembly.md)  
  
-   [__asm](../../assembler/inline/asm.md)  
  
-   [__Asm bloklarında derleme dili kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)  
  
-   [__Asm bloklarında C veya C++ kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)  
  
-   [Satır içi derlemede kayıtları koruma ve kullanma](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md)  
  
-   [Satır içi derlemede etiketlere atlama](../../assembler/inline/jumping-to-labels-in-inline-assembly.md)  
  
-   [Satır içi derlemede C işlevlerini çağırma](../../assembler/inline/calling-c-functions-in-inline-assembly.md)  
  
-   [Satır içi derlemede C++ işlevlerini çağırma](../../assembler/inline/calling-cpp-functions-in-inline-assembly.md)  
  
-   [__Asm bloklarını C makroları olarak tanımlama](../../assembler/inline/defining-asm-blocks-as-c-macros.md)  
  
-   [Satır içi derleme en iyi duruma getirme](../../assembler/inline/optimizing-inline-assembly.md)  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri ve derleme dili](../../intrinsics/compiler-intrinsics-and-assembly-language.md)   
 [C++ Dil Başvurusu](../../cpp/cpp-language-reference.md)