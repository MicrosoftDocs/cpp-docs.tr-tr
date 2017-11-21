---
title: _WAIT_CHILD, _WAIT_GRANDCHILD | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _WAIT_GRANDCHILD
- WAIT_CHILD
- WAIT_GRANDCHILD
- _WAIT_CHILD
dev_langs: C++
helpviewer_keywords:
- WAIT_CHILD constant
- WAIT_GRANDCHILD constant
- _WAIT_CHILD constant
- _WAIT_GRANDCHILD constant
ms.assetid: 7acd96fa-d118-4339-bb00-e5afaf286945
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1e5e3aa48f0184730a7860ea055d9b233b4ac708
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="waitchild-waitgrandchild"></a>_WAIT_CHILD, _WAIT_GRANDCHILD
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#include <process.h>  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `_cwait` İşlevi (işlem kimliği biliniyorsa) başka bir işlemin tamamlanmasını beklemek için herhangi bir işlem tarafından kullanılabilir. Eylem bağımsız değişkeni aşağıdaki değerlerden biri olabilir:  
  
|Sabit|Açıklama|  
|--------------|-------------|  
|`_WAIT_CHILD`|Arama işlemi, belirtilen yeni işlem sonlanana kadar bekler.|  
|`_WAIT_GRANDCHILD`|Belirtilen yeni işlem ve bu yeni bir işlem tarafından oluşturulan tüm işlemleri kadar işlem bekler çağrılırken, sonlanır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_cwait](../c-runtime-library/reference/cwait.md)   
 [Genel sabitler](../c-runtime-library/global-constants.md)