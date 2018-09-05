---
title: Satır içi derlemede etiketlere atlama | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
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
ms.openlocfilehash: e697df32218c3e2bcdeb03cde44b7b5d854cb7b0
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693630"
---
# <a name="jumping-to-labels-in-inline-assembly"></a>İç Derlemede Etiketlere Atlama

**Microsoft'a özgü**

Gibi bir sıradan C veya C++ etiketi, etikete bir `__asm` bloğu boyunca (yalnızca blok içinde) tanımlanmış işlev kapsamına sahiptir. Her iki derleme yönergeleri ve `goto` atlama deyimleri içinde veya dışında etiketlere `__asm` blok.

İçinde tanımlanan etiketler `__asm` blokları büyük küçük harfe duyarlı değildir; her iki `goto` deyimleri ve derleme yönergeleri çalışması bakılmaksızın bu etiketlerine başvurabilir. C ve C++ etiketler büyük küçük harfe duyarlıdır yalnızca tarafından kullanıldığında `goto` deyimleri. Derleme yönergeleri çalışması bakılmaksızın bir C veya C++ etiketine atlayabilir.

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

Etiket olarak C Kitaplığı işlev adlarını kullanmayın `__asm` engeller. Örneğin, kullanılacak fikri size cazip olabilir `exit` aşağıdaki gibi bir etiket olarak:

```cpp
; BAD TECHNIQUE: using library function name as label
   jne exit
   .
   .
   .
exit:
   ; More __asm code follows
```

Çünkü **çıkmak** adı C Kitaplığı işlevi, bu kod bir atlama neden olabilecek **çıkmak** istenilen konuma işlevi yerine.

MASM programlar, dolar simgesinin olduğu gibi (`$`) geçerli konumu sayaç olarak görev yapar. Şu anda bir araya getirilen yönerge için bir etikettir. İçinde `__asm` blokları, ana kullanım olan uzun koşullu atlar yapmak için:

```cpp
   jne $+5 ; next instruction is 5 bytes long
   jmp farlabel ; $+5
   .
   .
   .
farlabel:
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır İçi Assembler](../../assembler/inline/inline-assembler.md)<br/>