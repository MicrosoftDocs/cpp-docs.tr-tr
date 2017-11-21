---
title: "Segment başvuruları satır içi derlemede | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- references, inline assembly
- segment references in inline assembly
- inline assembly, segment references
- registers
- inline assembly, registers
- registers, inline assembly
ms.assetid: c63e6bb4-49d9-4fa1-bb22-eea21b5cbc0f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6e0781b4539836dbd68ae5d68ec41d2761c47e10
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="segment-references-in-inline-assembly"></a>Satır İçi Derlemede Segment Başvurusu
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 YAZMAÇ yerine ada göre segmentlere başvurmalıdır (kesim adı `_TEXT` örneği için geçersiz). Kesim geçersiz kılmaları kullanmalıdır kayıt açıkça olduğu gibi ES: [BX].  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__Asm bloklarında derleme dili kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)