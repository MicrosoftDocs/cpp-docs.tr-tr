---
title: Satır İçi Derleyiciye Genel Bakış
ms.date: 08/30/2018
helpviewer_keywords:
- inline assembler
- __asm keyword [C++], invoking inline assembler
- invoking inline assembler
- inline assembly, inline assembler
ms.assetid: d990331a-0e33-4760-8d7a-b720b0288335
ms.openlocfilehash: 3872dcb194146bf0f4c89b0be03a49b5fe3a9e37
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87192086"
---
# <a name="inline-assembler-overview"></a>Satır İçi Derleyiciye Genel Bakış

**Microsoft'a Özgü**

Satır içi derleyici, ek derleme ve bağlantı adımları olmadan C ve C++ kaynak programlarınıza derleme dili yönergeleri eklemenize olanak tanır. Satır içi derleyici, derleyici içine eklenmiştir içinde yerleşik olarak bulunur, böylece Microsoft Macro Assembler (MASM) gibi ayrı bir derleyici gerekmez.

Satır içi derleyici ayrı derleme ve bağlantı adımları gerektirmediğinden, ayrı bir derleyiciden daha kullanışlıdır. Satır içi derleme kodu, kapsamdaki herhangi bir C veya C++ değişkeni ya da işlev adını kullanabilir, bu sayede programınızın C ve C++ koduyla tümleştirilmesi kolaydır. Ayrıca, derleme kodu C ve C++ deyimleriyle karışabileceğinden, C veya C++ ' da tek başına veya imkansız olan görevleri gerçekleştirebilir.

[__Asm](../../assembler/inline/asm.md) anahtar sözcüğü satır içi assembler çağırır ve bir C veya C++ ifadesinin yasal olduğu her yerde görünebilir. Kendisi tarafından bulunamaz. Ardından, bir derleme yönergesi, küme ayracı içine alınmış bir dizi yönerge veya en azından boş bir küme ayracı olmalıdır. **`__asm`** Burada "Block" terimi, ayraç içinde olsun ya da etmeksizin herhangi bir yönergeyi veya yönerge grubunu ifade eder.

Aşağıdaki kod, **`__asm`** küme ayraçları içine alınmış basit bir bloğudur. (Kod, bir özel işlev giriş sırasıdır.)

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

Alternatif olarak, **`__asm`** her derleme yönergesinin önüne koyabilirsiniz:

```cpp
__asm push ebp
__asm mov  ebp, esp
__asm sub  esp, __LOCAL_SIZE
```

**`__asm`** Anahtar sözcüğü bir ifade ayırıcısı olduğundan, aynı satıra derleme yönergeleri de koyabilirsiniz:

```cpp
__asm push ebp   __asm mov  ebp, esp   __asm sub  esp, __LOCAL_SIZE
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır içi assembler](../../assembler/inline/inline-assembler.md)<br/>
