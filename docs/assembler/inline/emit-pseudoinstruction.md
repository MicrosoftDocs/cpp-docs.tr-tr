---
title: _emit sözde yönerge | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
f1_keywords:
- _emit
dev_langs:
- C++
helpviewer_keywords:
- byte defining (inline assembly)
- _emit pseudoinstruction
ms.assetid: 004c48f3-364c-4e82-9a51-e326f9cc7b2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 569e3a078109e66df7dcf5cbf314817ce0786899
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50061932"
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