---
description: 'Hakkında daha fazla bilgi edinin: _emit sözde yönerge'
title: _emit Sözde Yönerge
ms.date: 08/30/2018
f1_keywords:
- _emit
helpviewer_keywords:
- byte defining (inline assembly)
- _emit pseudoinstruction
ms.assetid: 004c48f3-364c-4e82-9a51-e326f9cc7b2b
ms.openlocfilehash: d3e2a39312c94ff0e4868bed9afa74011051a129
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117815"
---
# <a name="_emit-pseudoinstruction"></a>_emit Sözde Yönerge

**Microsoft'a Özgü**

**_Emit** sözde yönerge geçerli metin kesimindeki geçerli konumda bir bayt tanımlar. **_Emit** sözde yönerge, Masd 'nin [DB](../../assembler/masm/db.md) yönergesine benzer.

Aşağıdaki parça, 0x4A, 0x43 ve 0x4B baytlarını koda koyar:

```cpp
#define randasm __asm _emit 0x4A __asm _emit 0x43 __asm _emit 0x4B
.
.
.
__asm {
    randasm
    }
```

> [!CAUTION]
> `_emit`Kayıtları değiştiren yönergeler oluşturursa ve uygulamayı iyileştirmelere göre derlerseniz, derleyici hangi yazmaçların etkilendiğini belirleyemez. Örneğin, `_emit` bir **VAX** kaydını değiştiren bir yönerge oluşturursa, derleyici, bu, **korx** 'in değiştiğini bilmez. Derleyici daha sonra, satır içi assembler kodu yürütüldükten sonra o kayıttaki değer hakkında yanlış bir varsayımına sahip olabilirler. Sonuç olarak, uygulamanız çalıştırıldığında öngörülemeyen davranışları gösterebilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__Asm bloklarında derleme dili kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
