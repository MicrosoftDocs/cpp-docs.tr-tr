---
title: "Veri yönergeleri ve işleçler satır içi derlemede | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9875a6d4ee0b061db609f45d574a80a7ee5424ab
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>Satır İçi Derlemede Veri Yönergeleri ve İşleçler
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Ancak bir `__asm` bloğu başvuru C veya C++ veri türleri ve nesneleri, veri nesneleri MASM yönergeleri veya işleçleri ile tanımlayamazsınız. Özellikle, tanım yönergeleri kullanarak **DB**, `DW`, **GG**, `DQ`, `DT`, ve `DF`, veya işleçleri `DUP` veya  **Bu**. MASM yapılar ve kayıtları ayrıca kullanılamaz. Satır içi derleyici yönergeleri kabul etmez `STRUC`, `RECORD`, **genişliği**, veya **maskesi**.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__Asm bloklarında derleme dili kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)