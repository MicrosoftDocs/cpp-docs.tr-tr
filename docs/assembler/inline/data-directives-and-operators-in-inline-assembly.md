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
ms.openlocfilehash: bcacb0cdd26181da3cf80a582866c1e30567d043
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87192359"
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>Satır İçi Derlemede Veri Yönergeleri ve İşleçler

**Microsoft'a Özgü**

Bir **`__asm`** blok C veya C++ veri türlerine ve nesnelerine başvurabilir, ancak MASM yönergeleri veya işleçleri ile veri nesneleri tanımlanamaz. Özellikle, **veritabanı**, `DW` , **gg**, `DQ` , `DT` , ve veya `DF` işleçlerini `DUP` veya **Bu**tanım yönergelerini kullanamazsınız. Masa yapıları ve kayıtları da kullanılamaz. Satır içi derleyici yönergeleri `STRUC` , `RECORD` , **genişliği**veya **maskeyi**kabul etmez.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__Asm bloklarında derleme dili kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
