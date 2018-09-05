---
title: Satır içi derlemeyle işlevler yazma | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], inline assembly
- inline assembly [C++], writing functions
- assembler [C++], writing functions
- __asm keyword [C++], in functions
ms.assetid: b5df8a04-fdc7-4622-8c9e-e4b618927497
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c8b2694d2dc5781a6ef521abdc97e98c928be92c
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43680834"
---
# <a name="writing-functions-with-inline-assembly"></a>Satır İçi Derlemeyle İşlevler Yazma

**Microsoft'a özgü**

Bir işlevi satır içi derleme kodu yazarsanız, işleve bağımsız değişkenleri geçirmek ve bir değer döndürürler daha kolaydır. Aşağıdaki örnekler için ayrı bir derleyici önce yazılmış ve satır içi assembler için sonra yeniden yazan bir işlev karşılaştırın. Çağrılan işlev `power2`, ikinci parametresinin değerini 2 olarak ilk parametre çarparak, iki parametre alır. Ayrı bir derleyici için yazılan, işlev şuna benzeyebilir:

```asm
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

İşlevi, ayrı bir derleyici için yazılır olduğundan, ayrı bir kaynak dosya, derleme ve bağlantı adımları gerektirir. C ve C++ işlev bağımsız değişkenleri genellikle Kalanlar yığın üzerinde bu nedenle bu sürümünü `power2` işlevi, bağımsız değişkenler yığında konumlarına göre erişir. (Unutmayın **modeli** yönergesi, MASM ve bazı diğer birleştiricileri kullanılabilir ayrıca yığın bağımsız değişkenleri ve yerel yığın değişkenleri adıyla erişmek olanak tanır.)

## <a name="example"></a>Örnek

Bu program Yazar `power2` işlevi satır içi derleme kodu ile:

```cpp
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

Satır içi sürümü `power2` işlevi için bağımsız değişkenlerinden adıyla başvuran ve aynı kaynak dosyada programın geri kalanını olarak görünür. Bu sürüm, daha az sayıda derleme yönergelerini de gerektirir.

Çünkü satır içi sürümü `power2` C yürütülmez `return` deyimi, zararsız bir uyarı uyarı düzeyi 2 veya üzeri derlerseniz olur. İşlev bir değer döndürür, ancak derleyici, içinde olmaması bildiremez bir `return` deyimi. Kullanabileceğiniz [#pragma Uyarısı](../../preprocessor/warning.md) bu uyarı oluşturulmasını devre dışı bırakmak için.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__asm Bloklarında C veya C++ Kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>