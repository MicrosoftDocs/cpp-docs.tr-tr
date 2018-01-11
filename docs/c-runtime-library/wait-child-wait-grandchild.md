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
ms.workload: cplusplus
ms.openlocfilehash: 1ac83e22e906a4e885860ec2254b2b732e31d38a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Global Sabitler](../c-runtime-library/global-constants.md)