---
title: . DOSSEG | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .DOSSEG
dev_langs:
- C++
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3817cfe98758faf86ea87d74e02657598c3e806b
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
ms.locfileid: "32054893"
---
# <a name="dosseg"></a>.DOSSEG
MS-DOS segment kurala göre kesimleri siparişleri: kod ilk olarak, ardından kesim değil DGROUP ve ardından kesim içinde DGROUP.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
.DOSSEG  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sırada DGROUP segmentlerinde izleyin: kesimleri BSS veya YIĞINI, sonra BSS kesimleri ve son olarak YIĞINI kesimleri. MASM tek başına programlar CodeView desteği sağlamak için kullanılır. Aynı [DOSSEG](../../assembler/masm/dosseg.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)