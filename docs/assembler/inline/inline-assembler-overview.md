---
title: Satır İçi Derleyiciye Genel Bakış
ms.date: 08/30/2018
helpviewer_keywords:
- inline assembler
- __asm keyword [C++], invoking inline assembler
- invoking inline assembler
- inline assembly, inline assembler
ms.assetid: d990331a-0e33-4760-8d7a-b720b0288335
ms.openlocfilehash: 6233e07e115c21a0a173f094079dc9c1753533b6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169403"
---
# <a name="inline-assembler-overview"></a>Satır İçi Derleyiciye Genel Bakış

**Microsoft 'a özgü**

Satır içi derleyici, ek derleme ve bağlantı adımları olmadan C ve C++ kaynak programlarınıza derleme dili yönergeleri eklemenize olanak tanır. Satır içi derleyici, derleyici içine eklenmiştir içinde yerleşik olarak bulunur, böylece Microsoft Macro Assembler (MASM) gibi ayrı bir derleyici gerekmez.

Satır içi derleyici ayrı derleme ve bağlantı adımları gerektirmediğinden, ayrı bir derleyiciden daha kullanışlıdır. Satır içi derleme kodu, kapsamda olan herhangi C++ bir C veya değişken ya da işlev adını kullanabilir, bu sayede programınızın C ve C++ kodu ile tümleştirilebilen kolay bir işlemdir. Derleme kodu C ve C++ deyimleri ile karışabileceğinden, c veya C++ tek başına bir veya imkansız olan görevleri yapabilir.

[__Asm](../../assembler/inline/asm.md) anahtar sözcüğü satır içi assembler çağırır ve bir C ya da C++ deyimin yasal olduğu her yerde görünebilir. Kendisi tarafından bulunamaz. Ardından, bir derleme yönergesi, küme ayracı içine alınmış bir dizi yönerge veya en azından boş bir küme ayracı olmalıdır. Burada "`__asm` Block" terimi, ayraç içinde olsun veya etmeksizin herhangi bir yönergeyi veya yönerge grubunu ifade eder.

Aşağıdaki kod, küme ayraçları içine alınmış basit bir `__asm` bloğudur. (Kod, bir özel işlev giriş sırasıdır.)

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

Alternatif olarak, her derleme yönergesinin önüne `__asm` koyabilirsiniz:

```cpp
__asm push ebp
__asm mov  ebp, esp
__asm sub  esp, __LOCAL_SIZE
```

`__asm` anahtar sözcüğü bir deyim ayırıcısı olduğundan, aynı satıra derleme yönergeleri de koyabilirsiniz:

```cpp
__asm push ebp   __asm mov  ebp, esp   __asm sub  esp, __LOCAL_SIZE
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır İçi Assembler](../../assembler/inline/inline-assembler.md)<br/>
