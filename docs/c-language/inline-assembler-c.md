---
description: Daha fazla bilgi için bkz. satır Içi Assembler (C)
title: Satır İçi Derleyicisi (C)
ms.date: 11/04/2016
helpviewer_keywords:
- __asm keyword [C]
- inline assembler [C]
ms.assetid: 821acc77-60b1-434c-ba54-2ba930a25ab4
ms.openlocfilehash: 8c5dc8ecc713968786b05eca6ab38e4752ea48c4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181859"
---
# <a name="inline-assembler-c"></a>Satır İçi Derleyicisi (C)

**Microsoft'a Özgü**

Satır içi derleyici, fazladan derleme ve bağlantı adımları olmaksızın, doğrudan C kaynak programlarınıza derleme dili yönergeleri eklemenize olanak verir. Satır içi derleyici, derleyici içine eklenmiştir içinde yerleşik olarak bulunur, böylece Microsoft Macro Assembler (MASM) gibi ayrı bir derleyici gerekmez.

Satır içi derleyici ayrı derleme ve bağlantı adımları gerektirmediğinden, ayrı bir derleyiciden daha kullanışlıdır. Satır içi derleme kodu, kapsam içinde olan herhangi bir C değişkeni veya işlev adını kullanabilir; bu şekilde programınızın C kodu ile tümleştirmek de kolaydır. Ve derleme kodu C ifadeleri ile birleştirilebildiğinden, tek başına C'de zor ya da olanaksız olan görevleri yapabilir.

**`__asm`** Anahtar sözcüğü, satır içi assembler 'yi çağırır ve C ifadesinin yasal olduğu her yerde görünebilir. Kendisi tarafından bulunamaz. Ardından, bir derleme yönergesi, küme ayracı içine alınmış bir dizi yönerge veya en azından boş bir küme ayracı olmalıdır. **`__asm`** Burada "Block" terimi, ayraç içinde olsun ya da etmeksizin herhangi bir yönergeyi veya yönerge grubunu ifade eder.

Aşağıdaki kod, **`__asm`** küme ayraçları içine alınmış basit bir bloğudur. (Kod, bir özel işlev giriş sırasıdır.)

```
__asm
{
   push ebp
   mov  ebp, esp
   sub  esp, __LOCAL_SIZE
}
```

Alternatif olarak, **`__asm`** her derleme yönergesinin önüne koyabilirsiniz:

```
__asm push ebp
__asm mov  ebp, esp
__asm sub  esp, __LOCAL_SIZE
```

**`__asm`** Anahtar sözcüğü bir ifade ayırıcısı olduğundan, aynı satıra derleme yönergeleri de koyabilirsiniz:

```
__asm push ebp   __asm mov  ebp, esp   __asm sub  esp, __LOCAL_SIZE
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[İşlev öznitelikleri](../c-language/function-attributes.md)
