---
title: _emit Sözde Yönerge
ms.date: 08/30/2018
f1_keywords:
- _emit
helpviewer_keywords:
- byte defining (inline assembly)
- _emit pseudoinstruction
ms.assetid: 004c48f3-364c-4e82-9a51-e326f9cc7b2b
ms.openlocfilehash: 8be250aadf20dc4a7dee6a0b565ece21840339d7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169480"
---
# <a name="_emit-pseudoinstruction"></a>_emit Sözde Yönerge

**Microsoft 'a özgü**

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
> `_emit` kayıtları değiştiren yönergeler oluşturursa ve uygulamayı iyileştirmelere göre derlerseniz, derleyici hangi kayıtların etkilendiğini belirleyemez. Örneğin, `_emit`, **korx** kaydını değiştiren bir yönerge oluşturursa, bu, bu, **rampaın** değiştiğini bilmez. Derleyici daha sonra, satır içi assembler kodu yürütüldükten sonra o kayıttaki değer hakkında yanlış bir varsayımına sahip olabilirler. Sonuç olarak, uygulamanız çalıştırıldığında öngörülemeyen davranışları gösterebilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__asm Bloklarında Bütünleştirilmiş Kod Dili Kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
