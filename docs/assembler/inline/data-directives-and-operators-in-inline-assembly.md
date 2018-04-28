---
title: Veri yönergeleri ve işleçler satır içi derlemede | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 0bd3bc686cc8cee1a02e9df936f80f542bec26bd
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>Satır İçi Derlemede Veri Yönergeleri ve İşleçler
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Ancak bir `__asm` bloğu başvuru C veya C++ veri türleri ve nesneleri, veri nesneleri MASM yönergeleri veya işleçleri ile tanımlayamazsınız. Özellikle, tanım yönergeleri kullanarak **DB**, `DW`, **GG**, `DQ`, `DT`, ve `DF`, veya işleçleri `DUP` veya  **Bu**. MASM yapılar ve kayıtları ayrıca kullanılamaz. Satır içi derleyici yönergeleri kabul etmez `STRUC`, `RECORD`, **genişliği**, veya **maskesi**.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__asm Bloklarında Bütünleştirilmiş Kod Dili Kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)