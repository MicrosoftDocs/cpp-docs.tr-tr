---
title: EXTERNDEF | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- EXTERNDEF
dev_langs:
- C++
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a463f4f74f380c6d927419eb498ccd868587ac6d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="externdef"></a>EXTERNDEF
Bir veya daha fazla dış değişkenler, etiketler veya adlı simgelerini tanımlar *adı* türü olan `type`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
EXTERNDEF [[langtype]] name:type [[, [[langtype]] name:type]]...  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa *adı* tanımlanan modülünde onu olarak işlem görür [ortak](../../assembler/masm/public-masm.md). Varsa *adı* başvurulan modül, onu olarak işlem görür [EXTERN](../../assembler/masm/extern-masm.md). Varsa *adı* olan başvurulmayan, dikkate alınmaz. `type` Olabilir [ABS](../../assembler/masm/operator-abs.md), hangi içeri aktarmalar *adı* bir sabit olarak. Normal olarak kullanılan dosyaları dahil edin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)