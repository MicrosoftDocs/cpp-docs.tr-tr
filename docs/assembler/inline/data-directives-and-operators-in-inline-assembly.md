---
description: 'Daha fazla bilgi edinin: satır Içi derlemede veri yönergeleri ve Işleçler'
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
ms.openlocfilehash: a2b11aa95723245fc977f97f42b1de2f6c7306ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117958"
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>Satır İçi Derlemede Veri Yönergeleri ve İşleçler

**Microsoft'a Özgü**

Bir **`__asm`** blok C veya C++ veri türlerine ve nesnelerine başvurabilir, ancak MASM yönergeleri veya işleçleri ile veri nesneleri tanımlanamaz. Özellikle, **veritabanı**, `DW` , **gg**, `DQ` , `DT` , ve veya `DF` işleçlerini `DUP` veya **Bu** tanım yönergelerini kullanamazsınız. Masa yapıları ve kayıtları da kullanılamaz. Satır içi derleyici yönergeleri `STRUC` , `RECORD` , **genişliği** veya **maskeyi** kabul etmez.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__Asm bloklarında derleme dili kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
