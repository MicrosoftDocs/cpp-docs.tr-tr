---
description: 'Hakkında daha fazla bilgi edinin: satır Içi derleme ile yazma Işlevleri'
title: Satır İçi Derlemeyle İşlevler Yazma
ms.date: 08/30/2018
helpviewer_keywords:
- functions [C++], inline assembly
- inline assembly [C++], writing functions
- assembler [C++], writing functions
- __asm keyword [C++], in functions
ms.assetid: b5df8a04-fdc7-4622-8c9e-e4b618927497
ms.openlocfilehash: 94a1e03842620982e74818dbf2f1bd492a2a4738
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97121816"
---
# <a name="writing-functions-with-inline-assembly"></a>Satır İçi Derlemeyle İşlevler Yazma

**Microsoft'a Özgü**

Satır içi derleme kodu içeren bir işlev yazarsanız, bağımsız değişkenleri işleve geçirmek ve bundan bir değer döndürmek kolaydır. Aşağıdaki örneklerde, ilk olarak ayrı bir birleştirici için yazılan bir işlev karşılaştırılmaktadır ve sonra satır içi assembler için yeniden yazılır. Çağrılan işlev `power2` iki parametre alır, ilk parametreyi 2 ile ikinci parametrenin gücünden çarpar. Ayrı bir birleştirici için yazılan işlev şöyle görünebilir:

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

Ayrı bir birleştirici için yazıldığı için, işlev ayrı bir kaynak dosya ve derleme ve bağlantı adımları gerektirir. C ve C++ işlev bağımsız değişkenleri genellikle yığına geçirilir, bu nedenle işlevin bu sürümü, `power2` bağımsız değişkenlerine yığındaki konumlarına göre erişir. (Masd ve diğer bazı birleştiriciler için kullanılabilen **model** yönergesinin Ayrıca, yığın bağımsız değişkenlerine ve yerel yığın değişkenlerine ada göre erişmenizi de sağlar.)

## <a name="example"></a>Örnek

Bu program, `power2` işlevi satır içi derleme kodu ile Yazar:

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

İşlevin satır içi sürümü, `power2` bağımsız değişkenlerine adına göre başvurur ve programın geri kalanı ile aynı kaynak dosyasında görünür. Bu sürüm, daha az derleme yönergesi de gerektirir.

Satır içi sürümü `power2` bir C ifadesini yürütmediğinden **`return`** , uyarı düzeyi 2 veya daha yüksek bir sürümde derlerseniz zararsız bir uyarıya neden olur. İşlev bir değer döndürür, ancak derleyici bir deyimin yokluğunda bunu söyleyebilir **`return`** . Bu uyarının oluşturulmasını devre dışı bırakmak için [#pragma uyarısı](../../preprocessor/warning.md) kullanabilirsiniz.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__Asm bloklarında C veya C++ kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>
