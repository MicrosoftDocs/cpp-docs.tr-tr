---
title: "Satır içi derlemeyle işlevler yazma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], inline assembly
- inline assembly [C++], writing functions
- assembler [C++], writing functions
- __asm keyword [C++], in functions
ms.assetid: b5df8a04-fdc7-4622-8c9e-e4b618927497
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f2fc9e6a1d2c94e74ef8aabf085af8fc4dc0bc28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="writing-functions-with-inline-assembly"></a>Satır İçi Derlemeyle İşlevler Yazma
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Satır içi derleme kodunda işleviyle yazarsanız, işleve bağımsız değişkenler geçirmek ve ondan bir değeri döndürme kolaydır. Aşağıdaki örnekler bir işlev için ayrı bir derleyici ilk yazılır ve satır içi derleyicisi için yeniden yazılmıştır karşılaştırın. Çağrılan işlev `power2`, ikinci parametre gücünü 2 tarafından ilk parametre çarparak iki parametre alır. İçin ayrı bir assembler yazılan işlevi şuna benzeyebilir:  
  
```  
; POWER.ASM  
; Compute the power of an integer  
;  
       PUBLIC _power2  
_TEXT SEGMENT WORD PUBLIC 'CODE'  
_power2 PROC  
  
        push ebp        ; Save EBP  
        mov ebp, esp    ; Move ESP into EBP so we can refer  
                        ;   to arguments on the stack  
        mov eax, [ebp+4] ; Get first argument  
        mov ecx, [ebp+6] ; Get second argument  
        shl eax, cl     ; EAX = EAX * ( 2 ^ CL )  
        pop ebp         ; Restore EBP  
        ret             ; Return with sum in EAX  
  
_power2 ENDP  
_TEXT   ENDS  
        END  
```  
  
 İçin ayrı bir assembler yazılmış olduğundan, işlev ayrı bir kaynak dosya, derleme ve bağlantı adımlar gerektirir. C ve C++ işlev bağımsız değişkenleri genellikle yığında geçirilen bu nedenle bu sürümü `power2` işlevi bağımsız değişkenlerini konumlarına yığında tarafından erişir. (Unutmayın **modeli** yönergesi, MASM ve bazı diğer birleştiricileri kullanılabilir de yığın bağımsız değişkenleri ve yerel yığın değişkenleri adına göre erişim izin verir.)  
  
## <a name="example"></a>Örnek  
 Bu program Yazar `power2` satır içi derleme kodunda işleviyle:  
  
```  
// Power2_inline_asm.c  
// compile with: /EHsc  
// processor: x86  
  
#include <stdio.h>  
  
int power2( int num, int power );  
  
int main( void )  
{  
    printf_s( "3 times 2 to the power of 5 is %d\n", \  
              power2( 3, 5) );  
}  
int power2( int num, int power )  
{  
   __asm  
   {  
      mov eax, num    ; Get first argument  
      mov ecx, power  ; Get second argument  
      shl eax, cl     ; EAX = EAX * ( 2 to the power of CL )  
   }  
   // Return with result in EAX  
}  
```  
  
 Satır içi sürümünü `power2` işlevi bağımsız değişkenlerini adıyla başvuruyor ve aynı kaynak dosyası program kalan olarak görünür. Bu sürüm, daha az derleme yönergeleri de gerektirir.  
  
 Çünkü satır içi sürümünü `power2` C yürütmez `return` deyimi, zararsız uyarı uyarı 2 veya daha yüksek düzeyde derleme yaparsanız olur. İşlev bir değer döndürmesi ancak yokluğuna göre bildiremez derleyici bir `return` deyimi. Kullanabileceğiniz [#pragma Uyarısı](../../preprocessor/warning.md) bu uyarı oluşturma devre dışı bırakmak için.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__asm Bloklarında C veya C++ Kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)