---
title: . DOSSEG | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .DOSSEG
dev_langs: C++
helpviewer_keywords: .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a53159911c47d1c88df90c53f3302f813e5bd95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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