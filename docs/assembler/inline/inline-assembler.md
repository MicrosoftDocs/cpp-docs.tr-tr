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
ms.workload: cplusplus
ms.openlocfilehash: bdbfdc47ad0bca868ce7594b84adfa093ef580ca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="inline-assembler"></a>Satır İçi Derleyicisi
**Microsoft özel**  
  
 Derleme dili; program hızını geliştirmek, bellek ihtiyaçlarını azaltmak ve donanımı denetlemek gibi pek çok amaca hizmet eder. Derleme dili talimatlarını ek derleme ve bağlama adımı olmadan doğrudan C ve C++ kaynaklı programlarınıza katıştırmak için satır içi derleyiciyi kullanabilirsiniz. Satır içi assembler derleyici içinde yerleşik olarak bulunur, böylece, Microsoft Makro Çevirici (MASM) gibi ayrı bir derleyici gerekmez.  
  
> [!NOTE]
>  Satır içi derleme kodu içeren programlar diğer donanım platformlarına tamamen taşınamaz. Taşınabilirlik için tasarlıyorsanız, satır içi derleyici kullanmaktan kaçının.  
  
 Satır içi derleme ARM üzerinde desteklenmiyor ve [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] işlemci.  Aşağıdaki konular, Visual C/C++ satır içi birleştirici/ayırıcı ile x86 işlemcilerin nasıl kullanıldığını açıklar:  
  
-   [Satır İçi Assembler’a Genel Bakış](../../assembler/inline/inline-assembler-overview.md)  
  
-   [Satır İçi Bütünleştirilmiş Kod Avantajları](../../assembler/inline/advantages-of-inline-assembly.md)  
  
-   [__asm](../../assembler/inline/asm.md)  
  
-   [__asm Bloklarında Bütünleştirilmiş Kod Dili Kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)  
  
-   [__asm Bloklarında C veya C++ Kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)  
  
-   [Bir Satır İçi Bütünleştirilmiş Kodda Kayıtları Kullanma ve Koruma](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md)  
  
-   [İç Bütünleştirilmiş Kodda Etiketlere Atlama](../../assembler/inline/jumping-to-labels-in-inline-assembly.md)  
  
-   [Satır İçi Bütünleştirilmiş Kodda C İşlevlerini Çağırma](../../assembler/inline/calling-c-functions-in-inline-assembly.md)  
  
-   [Satır İçi Bütünleştirilmiş Kodda C İşlevlerini Çağırma](../../assembler/inline/calling-cpp-functions-in-inline-assembly.md)  
  
-   [__asm Bloklarını C Makroları olarak tanımlama](../../assembler/inline/defining-asm-blocks-as-c-macros.md)  
  
-   [Satır İçi Bütünleştirilmiş Kodu En İyi Duruma Getirme](../../assembler/inline/optimizing-inline-assembly.md)  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri ve derleme dili](../../intrinsics/compiler-intrinsics-and-assembly-language.md)   
 [C++ Dil Başvurusu](../../cpp/cpp-language-reference.md)