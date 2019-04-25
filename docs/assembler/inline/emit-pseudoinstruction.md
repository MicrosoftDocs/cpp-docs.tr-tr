---
title: _emit Sözde Yönerge
ms.date: 08/30/2018
f1_keywords:
- _emit
helpviewer_keywords:
- byte defining (inline assembly)
- _emit pseudoinstruction
ms.assetid: 004c48f3-364c-4e82-9a51-e326f9cc7b2b
ms.openlocfilehash: f2a7c9c4dab97bc1aba3147b5d75f6abbdac951f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167172"
---
# <a name="emit-pseudoinstruction"></a>_emit Sözde Yönerge

**Microsoft'a özgü**

**_Emit** sözde yönerge geçerli metin segmentine geçerli konumda bir bayt tanımlar. **_Emit** sözde yönerge benzer [DB](../../assembler/masm/db.md) MASM, yönerge.

Aşağıdaki parçası 0x4A 0x43 ve 0x4B bayt kodun içine yerleştirir:

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
> Varsa `_emit` yönergeler oluşturur kayıtları, değiştirmek ve en iyi duruma getirme ile uygulama derleme, derleyici hangi kayıtları etkilenen belirlenemiyor. Örneğin, varsa `_emit` değiştiren bir yönerge oluşturur **RAX'daki** Kaydet, derleyici olmadığı bilinmiyorsa, **RAX'daki** değişti. Derleyici, satır içi derleme kodu yürütüldükten sonra kaydetme yanlış bir varsayım, değeri hakkında daha sonra yapabilirsiniz. Sonuç olarak, uygulamanızın çalıştığında öngörülemeyen davranışları ortaya çıkabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__asm Bloklarında Bütünleştirilmiş Kod Dili Kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>