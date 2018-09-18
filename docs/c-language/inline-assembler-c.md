---
title: Inline assembler (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- __asm keyword [C]
- inline assembler [C]
ms.assetid: 821acc77-60b1-434c-ba54-2ba930a25ab4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fd380a9c10c2e1c8a5715a05b9a63cbd6c6df973
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051977"
---
# <a name="inline-assembler-c"></a>Satır İçi Derleyicisi (C)

**Microsoft'a özgü**

Satır içi derleyici, fazladan derleme ve bağlantı adımları olmaksızın, doğrudan C kaynak programlarınıza derleme dili yönergeleri eklemenize olanak verir. Satır içi derleyici, derleyici içine eklenmiştir içinde yerleşik olarak bulunur, böylece Microsoft Macro Assembler (MASM) gibi ayrı bir derleyici gerekmez.

Satır içi derleyici ayrı derleme ve bağlantı adımları gerektirmediğinden, ayrı bir derleyiciden daha kullanışlıdır. Satır içi derleme kodu, kapsam içinde olan herhangi bir C değişkeni veya işlev adını kullanabilir; bu şekilde programınızın C kodu ile tümleştirmek de kolaydır. Ve derleme kodu C ifadeleri ile birleştirilebildiğinden, tek başına C'de zor ya da olanaksız olan görevleri yapabilir.

`__asm` anahtar sözcüğü satır içi derleyiciyi çağırır ve bir C deyiminin geçerli olduğu her durumda görünebilir. Kendisi tarafından bulunamaz. Derleme yönergesinde, köşeli ayraçlar veya en azından içine yönergeler grubu tarafından gelmelidir bir çift boş tırnak işaretinin izlemesi. Terim "`__asm` blok" burada herhangi bir yönerge ya da küme ayraçları içinde olsun veya olmasın yönergeler grubu anlamına gelir.

Aşağıdaki kod ayraç içine alınmış basit bir `__asm` bloğudur. (Kod, bir özel işlev giriş sırasıdır.)

```
__asm
{
   push ebp
   mov  ebp, esp
   sub  esp, __LOCAL_SIZE
}
```

Alternatif olarak, koyabilirsiniz `__asm` her bir derleme yönergesinin önüne:

```
__asm push ebp
__asm mov  ebp, esp
__asm sub  esp, __LOCAL_SIZE
```

`__asm` anahtar sözcüğü bir deyim ayırıcısı olduğundan, aynı satıra derleme yönergeleri de koyabilirsiniz:

```
__asm push ebp   __asm mov  ebp, esp   __asm sub  esp, __LOCAL_SIZE
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[İşlev Öznitelikleri](../c-language/function-attributes.md)