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
ms.openlocfilehash: 916dce0346bebfc5ff65ca558ae75317a187660a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169545"
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>Satır İçi Derlemede Veri Yönergeleri ve İşleçler

**Microsoft 'a özgü**

`__asm` bloğu C veya C++ veri türlerine ve nesnelerine başvurabilir, ancak MASM yönergeleri veya işleçleri ile veri nesneleri tanımlanamaz. Özellikle, **veritabanı**, `DW`, **dd**, `DQ`, `DT`ve `DF`ya da işleçlerini `DUP` veya **Bu**tanımlama yönergelerini kullanamazsınız. Masa yapıları ve kayıtları da kullanılamaz. Satır içi assembler yönergeleri `STRUC`, `RECORD`, **genişliği**veya **maskesini**kabul etmez.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__asm Bloklarında Bütünleştirilmiş Kod Dili Kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
