---
title: "Satır içi derleyiciye genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inline assembler
- __asm keyword [C++], invoking inline assembler
- invoking inline assembler
- inline assembly, inline assembler
ms.assetid: d990331a-0e33-4760-8d7a-b720b0288335
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a58d9fd2dbce875c39c4c0e9af7ae85d5b20f43d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="inline-assembler-overview"></a>Satır İçi Derleyiciye Genel Bakış
**Microsoft özel**  
  
 Satır içi derleyicisi C ve C++ kaynak programlarınızı ek derleme ve bağlantı adımlar olmadan assembly dili yönergeleri katıştırma olanak sağlar. Satır içi derleyici, derleyici içine eklenmiştir içinde yerleşik olarak bulunur, böylece Microsoft Macro Assembler (MASM) gibi ayrı bir derleyici gerekmez.  
  
 Satır içi derleyici ayrı derleme ve bağlantı adımları gerektirmediğinden, ayrı bir derleyiciden daha kullanışlıdır. Satır içi derleme kodunda programınızın C ve C++ kodu ile tümleştirilmesi kolaydır, kapsam içi herhangi C veya C++ değişken veya işlev adı kullanabilirsiniz. Ve bütünleştirilmiş kodu, C ve C++ deyimleri ile bir arada kullanılabilir olduğundan, kullanışsız ya da C veya C++ tek başına imkansız görevlerini gerçekleştirebilir.  
  
 [__Asm](../../assembler/inline/asm.md) anahtar sözcüğü satır içi derleyicisi çağırır ve yerde C veya C++ deyimi yasal görünebilir. Tek başına bulunamaz. Derleme yönerge, küme ayraçları veya, çok az içine yönergeleri grubu tarafından gelmelidir küme ayraçları boş bir çifti. Terim "`__asm` blok" Buraya herhangi bir yönerge veya desteklemediğini köşeli parantez içindeki yönergeleri grubu başvuruyor.  
  
 Aşağıdaki kodu basit bir: `__asm` ayraçlar içinde blok. (Kod, bir özel işlev giriş sırasıdır.)  
  
```  
// asm_overview.cpp  
// processor: x86  
void __declspec(naked) main()  
{  
    // Naked functions must provide their own prolog...  
    __asm {  
        push ebp  
        mov ebp, esp  
        sub esp, __LOCAL_SIZE  
    }  
  
    // ... and epilog  
    __asm {  
        pop ebp  
        ret  
    }  
}  
```  
  
 Alternatif olarak, koyabilirsiniz `__asm` her derleme yönergesi önünde:  
  
```  
__asm push ebp  
__asm mov  ebp, esp  
__asm sub  esp, __LOCAL_SIZE  
```  
  
 `__asm` anahtar sözcüğü bir deyim ayırıcısı olduğundan, aynı satıra derleme yönergeleri de koyabilirsiniz:  
  
```  
__asm push ebp   __asm mov  ebp, esp   __asm sub  esp, __LOCAL_SIZE  
```  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Satır İçi Assembler](../../assembler/inline/inline-assembler.md)