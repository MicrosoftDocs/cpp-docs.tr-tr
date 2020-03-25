---
title: İç Derlemede Etiketlere Atlama
ms.date: 08/30/2018
helpviewer_keywords:
- inline assembly, jumping to labels
- labels, in inline assembly
- __asm keyword [C++], labels
- case sensitivity, labels in inline assembly
- labels, in __asm blocks
- jumping to labels in inline assembly
ms.assetid: 36c18b97-8981-4631-9dfd-af6c14a04297
ms.openlocfilehash: 199156a08af13f4a70793609b37c70b0c95bf9ba
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169337"
---
# <a name="jumping-to-labels-in-inline-assembly"></a>İç Derlemede Etiketlere Atlama

**Microsoft 'a özgü**

Sıradan bir C veya C++ etiket gibi, `__asm` bloğundaki bir etiket tanımlandığı işlevin tamamında kapsama sahiptir (yalnızca bloğunda değil). Derleme yönergelerinin ve `goto` deyimlerinin her ikisi de `__asm` bloğunun içindeki veya dışındaki etiketlere atlayabilirler.

`__asm` bloklardaki tanımlı Etiketler büyük/küçük harfe duyarlı değildir; `goto` deyimleri ve derleme yönergeleri, büyük/küçük harfe bakılmaksızın bu etiketlere başvurabilir. C ve C++ etiketler yalnızca `goto` deyimleri tarafından kullanıldığında büyük/küçük harfe duyarlıdır. Derleme yönergeleri, büyük/küçük harfe bakılmaksızın C++ bir C veya etiketine atlayabilir.

Aşağıdaki kod tüm permütasyon gösterir:

```cpp
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

C Kitaplığı işlev adlarını `__asm` bloklara etiket olarak kullanmayın. Örneğin, aşağıdaki gibi `exit` etiket olarak kullanmayı düşünebilirsiniz:

```cpp
; BAD TECHNIQUE: using library function name as label
   jne exit
   .
   .
   .
exit:
   ; More __asm code follows
```

**Exit** bir C Kitaplığı işlevinin adı olduğundan, bu kod istenen konum yerine **Çıkış** işlevine atmasına neden olabilir.

MASı programlarında olduğu gibi, dolar simgesi (`$`) geçerli konum sayacı olarak görev yapar. Bu, şu anda oluşturulan yönerge için bir etikettir. `__asm` bloklarından, ana kullanımı uzun koşullu atlamaları yapmak için kullanılır:

```cpp
   jne $+5 ; next instruction is 5 bytes long
   jmp farlabel ; $+5
   .
   .
   .
farlabel:
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır İçi Assembler](../../assembler/inline/inline-assembler.md)<br/>
