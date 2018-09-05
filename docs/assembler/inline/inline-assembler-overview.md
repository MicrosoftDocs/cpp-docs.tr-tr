---
title: Satır içi derleyiciye genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inline assembler
- __asm keyword [C++], invoking inline assembler
- invoking inline assembler
- inline assembly, inline assembler
ms.assetid: d990331a-0e33-4760-8d7a-b720b0288335
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e52316a5080ce7d64d34a09aa265ea561c186ed
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43681225"
---
# <a name="inline-assembler-overview"></a>Satır İçi Derleyiciye Genel Bakış

**Microsoft'a özgü**

Satır içi derleyici, derleme dili talimatlarını ek derleme ve bağlama adımı olmadan C ve C++ kaynak programlarınıza katıştırmak sağlar. Satır içi derleyici, derleyici içine eklenmiştir içinde yerleşik olarak bulunur, böylece Microsoft Macro Assembler (MASM) gibi ayrı bir derleyici gerekmez.

Satır içi derleyici ayrı derleme ve bağlantı adımları gerektirmediğinden, ayrı bir derleyiciden daha kullanışlıdır. Satır içi derleme kodu, programınızın C ve C++ kodu ile tümleştirmek de kolaydır, böylece kapsam içinde olan tüm C veya C++ değişken veya işlev adı kullanabilirsiniz. Ve derleme kodu C ve C++ deyimleri ile karma olabilir çünkü hantal ya da C veya C++ tek başına olanaksız olan görevleri yapabilirsiniz.

[__Asm](../../assembler/inline/asm.md) anahtar sözcüğü satır içi assembler çağırır ve her yerde bir C veya C++ deyiminin geçerli olduğu durumda görünebilir. Kendisi tarafından bulunamaz. Derleme yönergesinde, köşeli ayraçlar veya en azından içine yönergeler grubu tarafından gelmelidir bir çift boş tırnak işaretinin izlemesi. Terim "`__asm` blok" burada herhangi bir yönerge ya da küme ayraçları içinde olsun veya olmasın yönergeler grubu anlamına gelir.

Aşağıdaki kod, basit bir `__asm` blok küme ayraçları içine alınmış. (Kod, bir özel işlev giriş sırasıdır.)

```cpp
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

Alternatif olarak, koyabilirsiniz `__asm` her bir derleme yönergesinin önüne:

```cpp
__asm push ebp
__asm mov  ebp, esp
__asm sub  esp, __LOCAL_SIZE
```

`__asm` anahtar sözcüğü bir deyim ayırıcısı olduğundan, aynı satıra derleme yönergeleri de koyabilirsiniz:

```cpp
__asm push ebp   __asm mov  ebp, esp   __asm sub  esp, __LOCAL_SIZE
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır İçi Assembler](../../assembler/inline/inline-assembler.md)<br/>