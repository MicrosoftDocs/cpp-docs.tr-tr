---
title: Satır İçi Derleyicisi (C)
ms.date: 11/04/2016
helpviewer_keywords:
- __asm keyword [C]
- inline assembler [C]
ms.assetid: 821acc77-60b1-434c-ba54-2ba930a25ab4
ms.openlocfilehash: 8fb2a1dd3e87ef452083935e23048d80b4cdc8c3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62233183"
---
# <a name="inline-assembler-c"></a>Satır İçi Derleyicisi (C)

**Microsoft'a Özgü**

Satır içi derleyici, fazladan derleme ve bağlantı adımları olmaksızın, doğrudan C kaynak programlarınıza derleme dili yönergeleri eklemenize olanak verir. Satır içi derleyici, derleyici içine eklenmiştir içinde yerleşik olarak bulunur, böylece Microsoft Macro Assembler (MASM) gibi ayrı bir derleyici gerekmez.

Satır içi derleyici ayrı derleme ve bağlantı adımları gerektirmediğinden, ayrı bir derleyiciden daha kullanışlıdır. Satır içi derleme kodu, kapsam içinde olan herhangi bir C değişkeni veya işlev adını kullanabilir; bu şekilde programınızın C kodu ile tümleştirmek de kolaydır. Ve derleme kodu C ifadeleri ile birleştirilebildiğinden, tek başına C'de zor ya da olanaksız olan görevleri yapabilir.

`__asm` anahtar sözcüğü satır içi derleyiciyi çağırır ve bir C deyiminin geçerli olduğu her durumda görünebilir. Kendisi tarafından bulunamaz. Ardından, bir derleme yönergesi, küme ayracı içine alınmış bir dizi yönerge veya en azından boş bir küme ayracı olmalıdır. Burada "`__asm` Block" terimi, ayraç içinde olsun ya da etmeksizin herhangi bir yönergeyi veya yönerge grubunu ifade eder.

Aşağıdaki kod ayraç içine alınmış basit bir `__asm` bloğudur. (Kod, bir özel işlev giriş sırasıdır.)

```
__asm
{
   push ebp
   mov  ebp, esp
   sub  esp, __LOCAL_SIZE
}
```

Alternatif olarak, her derleme `__asm` yönergesinin önüne koyabilirsiniz:

```
__asm push ebp
__asm mov  ebp, esp
__asm sub  esp, __LOCAL_SIZE
```

`__asm` anahtar sözcüğü bir deyim ayırıcısı olduğundan, aynı satıra derleme yönergeleri de koyabilirsiniz:

```
__asm push ebp   __asm mov  ebp, esp   __asm sub  esp, __LOCAL_SIZE
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[İşlev Öznitelikleri](../c-language/function-attributes.md)
