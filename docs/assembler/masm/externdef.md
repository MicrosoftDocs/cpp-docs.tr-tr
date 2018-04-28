---
title: EXTERNDEF | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- EXTERNDEF
dev_langs:
- C++
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b010f52f91a04388f34052fcc5c374690cff13df
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
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