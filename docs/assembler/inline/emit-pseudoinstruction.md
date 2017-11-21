---
title: "_emit sözde yönerge | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _emit
dev_langs: C++
helpviewer_keywords:
- byte defining (inline assembly)
- _emit pseudoinstruction
ms.assetid: 004c48f3-364c-4e82-9a51-e326f9cc7b2b
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 00cd8425b4c6a9f7333f77f8bab4dc210528a352
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="emit-pseudoinstruction"></a>_emit Sözde Yönerge
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 **_Emit** sözde yönerge geçerli metin kesiminde geçerli konumundaki bir bayt tanımlar. **_Emit** sözde yönerge benzer [DB](../../assembler/masm/db.md) yönergesini MASM.  
  
 Aşağıdaki parça 0x4A, 0x43 ve 0x4B bayt koda yerleştirir:  
  
```  
#define randasm __asm _emit 0x4A __asm _emit 0x43 __asm _emit 0x4B  
 .  
 .  
 .  
__asm {  
     randasm  
     }  
```  
  
> [!CAUTION]
>  Varsa `_emit` yönergeleri oluşturur kaydeder, değiştirmek ve en iyi duruma getirme ile uygulama derleme, derleyici hangi yazmaçlar etkilenen belirleyemiyor. Örneğin, varsa `_emit` değiştiren bir yönerge oluşturur **rax** Kaydet, derleyici bilmediğinden, **rax** değişti. Derleyici sonra satır içi derleyici kod yürütüldükten sonra kaydetmek yanlış varsayılır, değer hakkında yapabilir. Çalıştırıldığında, sonuç olarak, uygulamanızın beklenmeyen davranışlar.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__Asm bloklarında derleme dili kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)