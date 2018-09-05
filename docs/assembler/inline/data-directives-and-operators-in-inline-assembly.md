---
title: Veri yönergeleri ve işleçler satır içi bütünleştirilmiş kodda | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6aff2f4c5ce5e7f5592aa9ec707d002c57f0eac0
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678743"
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>Satır İçi Derlemede Veri Yönergeleri ve İşleçler

**Microsoft'a özgü**

Ancak bir `__asm` blok, C veya C++ veri türleri ve nesneleri başvurabilir, veri nesneleriyle MASM yönergeleri veya işleçleri tanımlanamaz. Özellikle, tanımı yönergeleri kullanamazsınız **DB**, `DW`, **GG**, `DQ`, `DT`, ve `DF`, ya da işleçler `DUP` veya  **Bu**. MASM yapıları ve kayıtları da kullanılamaz. Satır içi assembler yönergeleri kabul etmez `STRUC`, `RECORD`, **genişliği**, veya **maskesi**.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__asm Bloklarında Bütünleştirilmiş Kod Dili Kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>