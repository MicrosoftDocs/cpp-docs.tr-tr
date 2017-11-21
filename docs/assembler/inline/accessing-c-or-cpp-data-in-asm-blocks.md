---
title: "C veya C++ verilerine __asm bloklarındaki erişme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- data members [C++], in __asm blocks
- data access [C++], in __asm blocks
- __asm keyword [C++], data members
- structure types in __asm blocks
ms.assetid: e99f5a28-0381-4090-8ece-6af8f2436a49
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f9a7316c8db4e9f6d74b3cd762e24272caaf2f34
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="accessing-c-or-c-data-in-asm-blocks"></a>__asm Bloklarında C veya C++ Verilerine Erişme
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Satır içi derleme için harika bir kolaylık C veya C++ değişkenleri için ad ile başvurmak için yeteneğidir. Bir `__asm` blok blok göründüğü kapsamındaki değişken adları dahil olmak üzere tüm sembolleri başvurabilir. Örneğin, varsa C değişkeni `var` kapsam, yönergesi  
  
```  
__asm mov eax, var  
```  
  
 değerini depolar `var` EAX içinde.  
  
 Bir sınıf, yapı veya bileşim üyesi benzersiz bir ad varsa bir `__asm` bloğu değişkeni belirtmeden yalnızca üye adı kullanarak için başvurabilir veya `typedef` süre önce adı (**.**) işleci. Ancak, üye adı benzersiz değilse, bir değişken yerleştirmeniz gerekir veya `typedef` dönem işleci hemen önce adı. Örneğin, aşağıdaki örnek paylaşımı yapısı türler `same_name` kullanıcıların üye adı olarak:.  
  
 Türleriyle değişkenler bildirirseniz  
  
```  
struct first_type hal;  
struct second_type oat;  
```  
  
 üye yapılan tüm başvuruları `same_name` değişken adı olduğundan kullanmalısınız `same_name` benzersiz değil. Ancak üye `weasel` böylece yalnızca üye adını kullanarak başvurabilirsiniz benzersiz bir adı vardır:  
  
```  
// InlineAssembler_Accessing_C_asm_Blocks.cpp  
// processor: x86  
#include <stdio.h>  
struct first_type  
{  
   char *weasel;  
   int same_name;  
};  
  
struct second_type  
{  
   int wonton;  
   long same_name;  
};  
  
int main()  
{  
   struct first_type hal;  
   struct second_type oat;  
  
   __asm  
   {  
      lea ebx, hal  
      mov ecx, [ebx]hal.same_name ; Must use 'hal'  
      mov esi, [ebx].weasel       ; Can omit 'hal'  
   }  
   return 0;  
}  
```  
  
 Değişken adı atlama yalnızca kodlama kolaylık olduğuna dikkat edin. Değişken adı mevcut olup olmadığını aynı derleme yönergeleri üretilir.  
  
 C++ içinde veri üyeleri erişim kısıtlamalarını dikkate almaksızın erişebilir. Ancak, üye işlevleri çağrılamaz.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__Asm bloklarında C veya C++ kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)