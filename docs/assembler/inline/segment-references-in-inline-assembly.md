---
title: Segment başvuruları satır içi derlemede | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- references, inline assembly
- segment references in inline assembly
- inline assembly, segment references
- registers
- inline assembly, registers
- registers, inline assembly
ms.assetid: c63e6bb4-49d9-4fa1-bb22-eea21b5cbc0f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f7add95852f751ed29dad8e0ba9577abd55fabaf
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
ms.locfileid: "32051482"
---
# <a name="segment-references-in-inline-assembly"></a>Satır İçi Derlemede Segment Başvurusu
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 YAZMAÇ yerine ada göre segmentlere başvurmalıdır (kesim adı `_TEXT` örneği için geçersiz). Kesim geçersiz kılmaları kullanmalıdır kayıt açıkça olduğu gibi ES: [BX].  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__asm Bloklarında Bütünleştirilmiş Kod Dili Kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)