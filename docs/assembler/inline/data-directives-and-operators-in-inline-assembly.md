---
title: Satır İçi Derlemede Veri Yönergeleri ve İşleçler
ms.date: 08/30/2018
helpviewer_keywords:
- data directives [C++]
- __asm keyword [C++], referencing limitations
- MASM (Microsoft Macro Assembler), directives
- directives [C++], MASM
- MASM (Microsoft Macro Assembler), structures
- operators [MASM]
- inline assembly, operators
- inline assembly, data directives
- MASM (Microsoft Macro Assembler), operators
- structures [C++], MASM
ms.assetid: fb7410c7-156a-4131-bcfc-211aa70533e3
ms.openlocfilehash: 52e20c37f3066122a062e3fc9c64ced576b6c302
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577989"
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>Satır İçi Derlemede Veri Yönergeleri ve İşleçler

**Microsoft'a özgü**

Ancak bir `__asm` blok, C veya C++ veri türleri ve nesneleri başvurabilir, veri nesneleriyle MASM yönergeleri veya işleçleri tanımlanamaz. Özellikle, tanımı yönergeleri kullanamazsınız **DB**, `DW`, **GG**, `DQ`, `DT`, ve `DF`, ya da işleçler `DUP` veya  **Bu**. MASM yapıları ve kayıtları da kullanılamaz. Satır içi assembler yönergeleri kabul etmez `STRUC`, `RECORD`, **genişliği**, veya **maskesi**.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__asm Bloklarında Bütünleştirilmiş Kod Dili Kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>