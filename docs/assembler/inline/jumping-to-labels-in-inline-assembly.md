---
title: Satır içi derlemede etiketlere atlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inline assembly, jumping to labels
- labels, in inline assembly
- __asm keyword [C++], labels
- case sensitivity, labels in inline assembly
- labels, in __asm blocks
- jumping to labels in inline assembly
ms.assetid: 36c18b97-8981-4631-9dfd-af6c14a04297
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a96bd532b5b4f03cb2040dd3157a6224ccf5029
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
ms.locfileid: "32052245"
---
# <a name="jumping-to-labels-in-inline-assembly"></a>İç Derlemede Etiketlere Atlama
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Gibi bir sıradan C veya C++ etiketi, bir etiket bir `__asm` blok kapsam (yalnızca bloğunda) tanımlanmış işlevi boyunca sahiptir. Hem derleme yönergeleri ve `goto` atlama deyimleri etiketlere içinde veya dışında `__asm` bloğu.  
  
 Tanımlanan etiketleri `__asm` blokları büyük küçük harfe duyarlı değildir; her iki `goto` deyimleri ve derleme yönergeleri etiketlerin durum dikkate almaksızın için başvurabilir. C ve C++ etiketleri büyük yalnızca tarafından kullanıldığında küçük harf duyarlı `goto` deyimleri. Derleme yönergeleri C veya C++ etiket durum dikkate almaksızın atlayabilirsiniz.  
  
 Aşağıdaki kod tüm permütasyon gösterir:  
  
```  
void func( void )  
{  
   goto C_Dest;  /* Legal: correct case   */  
   goto c_dest;  /* Error: incorrect case */  
  
   goto A_Dest;  /* Legal: correct case   */  
   goto a_dest;  /* Legal: incorrect case */  
  
   __asm  
   {  
      jmp C_Dest ; Legal: correct case  
      jmp c_dest ; Legal: incorrect case  
  
      jmp A_Dest ; Legal: correct case  
      jmp a_dest ; Legal: incorrect case  
  
      a_dest:    ; __asm label  
   }  
  
   C_Dest:       /* C label */   
   return;  
}  
int main()  
{  
}  
```  
  
 C Kitaplık işlevi adları etiket olarak kullanmayın `__asm` engeller. Örneğin, kullanılacak isteği duyabilirsiniz `exit` aşağıdaki gibi bir etiket olarak:  
  
```  
; BAD TECHNIQUE: using library function name as label  
jne exit  
   .  
   .  
   .  
exit:  
   ; More __asm code follows  
```  
  
 Çünkü **çıkmak** adı bir C Kitaplığı işlevinin bu kodu atlama neden olabilir **çıkmak** istenilen konuma işlev yerine.  
  
 MASM programları, dolar simgesi olduğu gibi (`$`) geçerli konumu sayacı olarak görev yapar. Şu anda getirilen yönerge etiketi değil. İçinde `__asm` blokları, ana kullanım alanı olan uzun koşullu atlar yapmak için:  
  
```  
jne $+5 ; next instruction is 5 bytes long  
jmp farlabel  
; $+5  
   .  
   .  
   .  
farlabel:  
```  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Satır İçi Assembler](../../assembler/inline/inline-assembler.md)