---
title: EXTERNDEF | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: EXTERNDEF
dev_langs: C++
helpviewer_keywords: EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 64aa9cc69825ef1f932024bc45c051e16c99e2eb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Yönergeler başvurusu](../../assembler/masm/directives-reference.md)