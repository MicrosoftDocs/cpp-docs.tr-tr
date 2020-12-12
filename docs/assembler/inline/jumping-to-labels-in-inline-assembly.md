---
description: 'Hakkında daha fazla bilgi edinin: satır Içi derlemede etiketlere atlama'
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
ms.openlocfilehash: b4a32dd9baace77245f612d68b58f954a81075ab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117724"
---
# <a name="jumping-to-labels-in-inline-assembly"></a>İç Derlemede Etiketlere Atlama

**Microsoft'a Özgü**

Sıradan bir C veya C++ etiketi gibi, blok içindeki bir etiketin **`__asm`** tanımlandığı işlevin tamamında kapsamı vardır (yalnızca bloğunda değil). Derleme yönergeleri ve **`goto`** deyimleri, blok içindeki veya dışındaki etiketlere atlayabilir **`__asm`** .

Bloklardaki tanımlı Etiketler büyük/küçük **`__asm`** harfe duyarlı değildir; her iki **`goto`** deyim ve derleme yönergeleri de bu etiketlere, büyük/küçük harfe bakılmaksızın başvurabilir. C ve C++ etiketleri yalnızca deyimler tarafından kullanıldığında büyük/küçük harfe duyarlıdır **`goto`** . Derleme yönergeleri, büyük/küçük harfe bakılmaksızın bir C veya C++ etiketine atlayabilir.

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

C Kitaplığı işlev adlarını bloklar halinde etiket olarak kullanmayın **`__asm`** . Örneğin, `exit` aşağıdaki gibi bir etiket olarak kullanmayı düşünebilirsiniz:

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

MASı programlarında olduğu gibi, dolar simgesi ( `$` ) geçerli konum sayacı işlevi görür. Bu, şu anda oluşturulan yönerge için bir etikettir. **`__asm`** Bloklar bölümünde, ana kullanımı uzun koşullu atlamaları yapmak için kullanılır:

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

[Satır içi assembler](../../assembler/inline/inline-assembler.md)<br/>
