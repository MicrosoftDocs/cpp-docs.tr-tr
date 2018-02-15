---
title: . DOSSEG | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- .DOSSEG
dev_langs:
- C++
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 39f02937ed1613cbd759621b2a4e75f84db918cf
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
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